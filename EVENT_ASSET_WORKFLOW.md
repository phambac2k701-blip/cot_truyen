# EVENT + ASSET WORKFLOW — GODOT HANDOFF

> **Purpose:** Cầu nối thực tế từ asset tải về → object trong Godot → interactable → authored event → persistent state.
> **Audience:** solo dev / AI coding agent.
> **Principle:** asset chỉ là "đạo cụ"; event system mới làm nó trở thành gameplay.

---

# 1. MENTAL MODEL

Một event trong game thường có 5 lớp:

1. **Asset** — model/sound/UI thật sự xuất hiện.
2. **Scene object** — node Godot có collision, animation, audio, interaction.
3. **Trigger** — player bước vào, nhìn, bấm E, đọc xong, hoặc state đổi.
4. **Action** — cửa đóng, đèn tắt, NPC đi, document mở, sound chạy.
5. **State** — game nhớ chuyện gì đã xảy ra để branch/save-load đúng.

Ví dụ:

```text
Notebook_Nam.glb
→ NamNotebook.tscn
→ player presses E
→ Document UI opens
→ player reaches last page
→ EVENT_S17_NOTEBOOK_FINISHED
→ sound outside + door state/NPC route changes
→ GameState writes NAM_NOTEBOOK_READ=true
```

---

# 2. ASSET IMPORT PIPELINE

## 2.1 3D
Preferred: `.glb` / `.gltf`.

Flow:
```text
download original
→ verify license
→ copy to game asset folder
→ import into Godot
→ inspect scale/material/pivot
→ create reusable .tscn wrapper
→ add collision only where needed
→ add interaction points
→ test in isolated test scene
→ use in hub
```

Không sửa imported GLB trực tiếp cho gameplay logic. Tạo wrapper scene.

Ví dụ:

```text
res://assets/3d/props/notebook_nam.glb

res://scenes/interactables/nam_notebook.tscn
  NamNotebook (Node3D)
  ├── Visual (imported GLB)
  ├── StaticBody3D
  │   └── CollisionShape3D
  ├── InteractionArea (Area3D)
  │   └── CollisionShape3D
  └── AudioStreamPlayer3D
```

---

# 3. STATIC VS INTERACTIVE

## Static prop
Không cần state.
Ví dụ: ghế, chậu cây, thùng carton nền.

Chỉ cần:
- visual;
- collision nếu player có thể đụng.

## Interactive prop
Player có thể bấm/inspect hoặc event thay đổi nó.

Cần:
- visual;
- collision;
- InteractionArea hoặc raycast target;
- script/component;
- optional AnimationPlayer;
- optional audio;
- event/state ID.

Ví dụ:
- cửa;
- drawer;
- notebook;
- phone;
- printer;
- radio;
- lamp;
- document.

---

# 4. BASIC GODOT EVENT ARCHITECTURE

Khuyến nghị tối thiểu:

```text
GameState
EventManager
InteractionManager
DialogueManager
ClueManager
SaveManager
```

Không cần làm hệ thống khổng lồ ngay.

## GameState
Giữ persistent flags/value.

Ví dụ:
```gdscript
GameState.set_flag("S17_NAM_NOTEBOOK_READ", true)
GameState.has_flag("S17_NAM_NOTEBOOK_READ")
```

## EventManager
Nhận event ID và chạy sequence/hook tương ứng.

Ví dụ:
```gdscript
EventManager.trigger("S17_NOTEBOOK_FINISHED")
```

## InteractionManager
Raycast từ camera; khi player bấm E thì gọi object interact.

## SaveManager
Lưu:
- flags;
- objective time;
- clue states;
- one-shot events;
- door/object states;
- relevant NPC state.

---

# 5. STANDARD INTERACTION FLOW

Player nhìn object
→ raycast hit Interactable
→ UI hiện `[E] Inspect`
→ player bấm E
→ object kiểm preconditions
→ interaction chạy
→ event/state update.

Pseudo:

```gdscript
func interact():
    if GameState.has_flag("NOTEBOOK_DISABLED"):
        return

    DocumentUI.open(notebook_data)
```

Khi đọc đến cuối:

```gdscript
func on_last_page_closed():
    if GameState.has_flag("S17_NAM_NOTEBOOK_READ"):
        return

    GameState.set_flag("S17_NAM_NOTEBOOK_READ", true)
    EventManager.trigger("S17_NOTEBOOK_FINISHED")
```

---

# 6. STANDARD AREA TRIGGER

Dùng `Area3D` khi event dựa vào vị trí.

Ví dụ:
- bước vào phòng;
- đi qua hành lang;
- tới gần cửa sổ;
- rời khỏi khu vực.

```text
EventTrigger (Area3D)
└── CollisionShape3D
```

Pseudo:

```gdscript
@export var event_id := ""
@export var one_shot := true

func _on_body_entered(body):
    if not body.is_in_group("player"):
        return

    if one_shot and GameState.has_flag(event_id + "_DONE"):
        return

    EventManager.trigger(event_id)
```

---

# 7. DOOR AS AN EVENT PROP

Reusable scene:

```text
Door
├── Visual
├── StaticBody3D
│   └── CollisionShape3D
├── InteractionArea
├── AnimationPlayer
└── AudioStreamPlayer3D
```

State:
- OPEN
- CLOSED
- LOCKED
- JAMMED

Event không nên teleport door state vô lý.

Ví dụ:
```text
S17_ENTER_NAM_ROOM
→ door state CLOSED/JAMMED
→ animation close
→ slam SFX
→ player control remains
→ handle interaction changes to locked/jammed response
```

Khi mở lại phải có authored cause:
- latch reset;
- power restore;
- NPC opens from outside;
- lock state changes by event.

---

# 8. LIGHT AS AN EVENT PROP

Reusable LightController:

States:
- NORMAL
- FLICKER
- OFF
- EMERGENCY

Event:
```text
EventManager.trigger("ROOM_TENSION_STAGE_2")
→ LightController.set_state(FLICKER)
```

Không hard-code story vào mỗi light script.

---

# 9. SOUND AS EVENT

Ambient sound:
- chạy theo area/hub.

Event sound:
- chạy khi sequence cần.

Ví dụ:
```text
notebook last page closes
→ 0.5s silence
→ footsteps outside
→ latch sound
→ NPC route begins
```

Audio là một action của event, không phải tự nó quyết định plot state.

---

# 10. NPC EVENT ROUTE

NPC không cần AI phức tạp cho authored moments.

Có thể dùng:
- NavigationAgent3D;
- predefined markers;
- AnimationTree;
- simple state machine.

Ví dụ:

```text
NamMarker_Stairs
NamMarker_Door
NamMarker_CommonArea
```

Event:
```text
S17_NOTEBOOK_FINISHED
→ Nam visible=true
→ spawn/enable at Stairs marker
→ walk to Door marker
→ line trigger when player exits
```

Nếu Nam không được phép biết player đọc sổ:
NPC state KHÔNG được set knowledge chỉ vì event fired.

Chỉ set knowledge nếu:
- Nam trực tiếp thấy;
- player nói;
- object disturbance là observable và authored;
- source report thật sự tới ông.

---

# 11. DOCUMENT / NOTEBOOK

Không cần 3D page-turn system phức tạp ban đầu.

Cheap implementation:
- 3D book prop;
- E to inspect;
- open 2D document UI;
- page next/back;
- close;
- event callback based on pages actually seen.

Track separately:
- opened;
- page_seen_x;
- last_page_seen;
- closed_after_last_page.

Không auto "understood" chỉ vì opened.

---

# 12. PROP STATE CHANGE

Dùng cho:
- object moved;
- cup disappears;
- door changes;
- sign replaced;
- paper appears.

Cheap ways:
- transform swap;
- visibility toggle;
- child variant A/B;
- material swap;
- texture swap.

State must persist if story-relevant.

Example:
```text
if GameState.has_flag("S05_POWER_STRIP_MOVED"):
    VariantA.visible = false
    VariantB.visible = true
```

---

# 13. EXAMPLE — LOCKED ROOM SET-PIECE

## Setup
Player enters Nam room for an authored legitimate reason.

## Nodes
```text
NamRoom
├── Door_Nam
├── LightController
├── Radio
├── Notebook
├── Drawer
├── EventTrigger_Enter
├── EventTrigger_Exit
└── NamRouteMarkers
```

## Flow
```text
ENTER_ROOM
→ close/jam door
→ slam SFX
→ player tests handle
→ room remains playable
→ light stage 1
→ curiosity props available
→ notebook/document interactions
→ world reactions based on actual discoveries
→ authored release cause
→ door available
→ optional Nam route outside
→ exit reaction
```

## Important
Không dùng:
`3 clues found = door magically unlocks`.

Có thể dùng clue progress để chọn timing/beat, nhưng world cause phải riêng.

Example:
```text
min_scene_progress reached
AND authored latch-reset beat fired
→ door state CLOSED
→ interact opens normally
```

---

# 14. SAVE / LOAD RULE

Mọi event quan trọng cần xác định:

- one-shot đã chạy chưa;
- object state;
- door state;
- clue observed;
- document pages seen nếu cần;
- NPC location/state nếu story-critical;
- objective time;
- event stage nếu save giữa set-piece.

Prototype đơn giản có thể cấm manual save giữa 20–60s cinematic micro-sequence, nhưng full design phải quyết định rõ.

Không được:
load → duplicate clue;
load → NPC spawn hai lần;
load → cửa trở về state cũ nhưng clue vẫn future-state.

---

# 15. DEVELOPMENT ORDER

Đừng bắt đầu bằng full event manager.

Làm prototype theo thứ tự:

## Prototype 1
Player + collision + E raycast.

## Prototype 2
Một door mở/đóng.

## Prototype 3
Một Area3D one-shot trigger.

## Prototype 4
GameState flag.

## Prototype 5
Một notebook/document UI.

## Prototype 6
Notebook close → EventManager → sound + light + door state.

## Prototype 7
NPC simple route.

## Prototype 8
Save/load flags + door/object state.

Nếu prototype 8 chạy ổn, đã có nền cho phần lớn event-driven narrative của game.

---

# 16. FIRST PRACTICAL TEST SCENE

Dùng HUB B / phòng Nam hoặc một test room riêng.

Mục tiêu:
1. Player đi vào.
2. Trigger đóng cửa.
3. Door chuyển JAMMED.
4. Player vẫn đi/nhìn tự do.
5. Light flicker sau authored event.
6. Player inspect notebook.
7. Close notebook.
8. SFX ngoài cửa.
9. Door được release vì authored cause.
10. Một NPC dummy đi qua hành lang.
11. Flag persist khi reload.

Nếu làm được sequence này, pipeline asset→interaction→event→state→save đã hoạt động.
