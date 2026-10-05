# ASSET REQUIREMENTS

> **Purpose:** Danh mục asset cần săn/chuẩn bị cho production game mystery 3D hiện tại.
> **Rule:** ưu tiên asset tái sử dụng, tương tác được và phục vụ event-driven storytelling hơn asset chỉ để trang trí.
> **Engine target:** Godot 4.x.
> **Preferred format:** .glb/.gltf cho 3D; .wav/.ogg cho audio; .png/.webp cho UI/decal.
> **Production constraint:** solo-dev + AI; ưu tiên "cheap but effective".

---

# 1. PRIORITY ORDER

## P0 — cần sớm để dựng vertical slice / event prototype
1. Door set: cửa phòng, cửa sắt, tay nắm, khóa/chốt.
2. Window set: cửa sổ, khung, rèm.
3. Furniture nhà trọ: giường đơn, bàn, ghế, tủ, kệ.
4. Interactive hero props: notebook, drawer, phone, papers/folders, keys.
5. Utility props: quạt, ổ điện, dây nối, công tắc, bóng đèn, radio.
6. Office/logistics props: printer, scanner, clipboard, parcel, shelf, trolley.
7. Basic NPC animation pack: idle/walk/sit/turn/use-phone/read-paper/open-door.
8. Core SFX: door/latch, footsteps, phone vibration, printer, paper, light buzz/flicker.
9. Basic PBR materials: old paint, concrete, tile, metal, wood, glass, paper/cardboard.
10. One generic NPC base + simple clothes variations.

## P1 — cần cho full vertical slice
- xe máy/xe đạp background;
- laundry/dép/xô/chậu/bình nước/chậu cây;
- hospital-office props;
- police-office props;
- CCTV prop;
- desk phone;
- access card;
- wall clock/calendar;
- signage / room-number system;
- ambience packs for alley/boarding house/logistics/hospital/office;
- fluorescent/emergency lights;
- decals dirt/water stains/mold;
- UI asset kit for phone, notebook, document viewer.

## P2 — polish / later
- secondary clutter;
- more NPC clothing variants;
- rain/window effects;
- extra vehicles;
- background hospital equipment;
- higher-quality hero variants;
- scene-specific props discovered after P5/P6 lock.

---

# 2. HUB B — NHÀ TRỌ

## Architecture / modular
- cửa phòng cũ;
- cửa sắt/cổng;
- cửa sổ có song;
- lan can;
- cầu thang;
- mái tôn/mái che;
- đồng hồ điện / hộp điện;
- dây điện nổi;
- đèn hành lang/trần.

## Furniture
- giường đơn;
- bàn học;
- ghế nhựa/gỗ;
- tủ quần áo nhỏ;
- kệ sách;
- bàn trà nhỏ;
- ghế ngồi của Nam;
- tủ thấp / drawer cabinet.

## Everyday clutter
- dép;
- xô/chậu;
- bình/chai nước;
- mì gói;
- cốc/chén;
- móc áo;
- quần áo phơi;
- dây phơi;
- chậu cây;
- túi nilon;
- thùng carton;
- vali;
- rác đời thường;
- xe máy/xe đạp.

## Interactive / hero props
- notebook/sổ của Nam có thể mở;
- chìa khóa/keyring;
- radio cũ;
- điện thoại;
- quạt bàn/quạt đứng;
- ổ cắm/dây nối;
- tua vít/hộp dụng cụ;
- lịch treo tường;
- báo/tạp chí;
- old business card / old work object;
- envelope/folder;
- cabinet/drawer có pivot/animation.

---

# 3. TÂN LỘ — LOGISTICS

- dispatch desk;
- office desk/chair;
- PC monitor/keyboard/mouse;
- printer;
- barcode scanner;
- handheld scanner;
- clipboard;
- delivery forms;
- envelopes;
- sealed A4 pouch;
- label/sticker/routing tag;
- parcels/cartons;
- shelves/racks;
- pallet;
- trolley;
- waiting bench/chairs;
- water dispenser;
- notice board;
- access door;
- CCTV prop;
- room signs;
- generic logistics uniform;
- van/truck background;
- document variants: old/new classification;
- workstation screen assets.

---

# 4. MINH TRẠCH — HOSPITAL / COMPLIANCE

- reception counter;
- waiting chairs;
- office/compliance door;
- file folders;
- document trays;
- desk phone;
- printer;
- PC/monitor;
- filing cabinet;
- employee badge;
- room signage;
- corridor light;
- emergency light;
- visitor chair;
- trolley background;
- curtains;
- trash bin;
- versioned forms / review sheets.

Không cần ưu tiên phòng mổ hoặc thiết bị y tế phức tạp nếu player không đi vào đó.

---

# 5. POLICE MICRO-SET

- desk/chairs;
- PC;
- printer;
- desk phone;
- folders;
- notebook;
- pens/sticky notes;
- filing cabinet;
- desk lamp;
- whiteboard/corkboard;
- water cup/bottle;
- evidence/document trays.

---

# 6. EVENT-DRIVEN HERO ASSETS

Các asset này có giá trị cao vì trực tiếp "diễn" cùng event:

- door có pivot đúng;
- drawer/cabinet mở được;
- notebook mở/đổi trang;
- phone có màn hình;
- radio bật/tắt;
- fan quay/dừng;
- light có thể flicker;
- paper rơi / đổi trạng thái;
- folder/document inspect;
- keyring;
- access card;
- wall clock;
- computer monitor có thể swap screen;
- curtain/window state;
- prop có A/B state: vị trí cũ / vị trí mới;
- object có visible/hidden state;
- sign/room-number có thể swap.

---

# 7. NPC ANIMATION PACK

Ưu tiên animation trung tính, dễ reuse:

- idle standing;
- idle sitting;
- walk;
- turn left/right;
- look over shoulder;
- look at object;
- use phone;
- hold/read paper;
- take/place object;
- open/close door;
- sit down;
- stand up;
- type keyboard;
- talk subtle;
- knock on door;
- react/look back nhẹ;
- point nhẹ;
- lean/wait.

Không cần mocap cinematic phức tạp ở giai đoạn đầu.

---

# 8. AUDIO — AMBIENCE

## Boarding house / Hanoi alley
- distant motorbikes;
- light horn;
- neighborhood voices;
- broom/sweeping;
- metal gate;
- TV/radio next room;
- fan hum;
- running water;
- footsteps on corridor/stairs;
- distant dog;
- rain/gutter.

## Logistics
- printer;
- scanner beep;
- trolley wheels;
- cardboard handling;
- warehouse/office hum;
- low office chatter;
- door/access beep.

## Hospital
- HVAC;
- corridor footsteps;
- distant announcement;
- desk phone;
- trolley;
- printer;
- subdued room tone.

## Police office
- keyboard;
- paper;
- desk phone;
- fluorescent hum;
- distant office ambience.

---

# 9. AUDIO — EVENT SFX

- door slam;
- soft door close;
- latch click;
- locked handle;
- handle rattle;
- knock/bang on door;
- light buzz;
- fluorescent flicker;
- switch;
- power cut / power restore;
- radio static;
- phone vibration;
- phone notification;
- printer paper feed;
- paper drop;
- drawer slide;
- key jingle;
- chair scrape;
- footsteps near/far/upstairs;
- small object drop;
- room-tone drop / silence transition;
- subtle tension sting;
- heartbeat only when narratively justified, not default.

---

# 10. VFX / LIGHTING

- light flicker;
- emission screen;
- dust particles;
- rain on window;
- emergency light;
- subtle hallway haze;
- decals: damp, dirt, water stain, mold;
- small shadow/movement cue;
- blackout state.

---

# 11. UI / 2D

- Bắc phone shell;
- chat UI;
- notifications;
- Tân Lộ job-app UI;
- notebook / clue viewer;
- document viewer;
- photo viewer;
- simple map / fast travel;
- interact prompt;
- save/load/menu;
- fictional Tân Lộ forms;
- fictional Minh Trạch forms;
- employee/access cards;
- room signs / number labels.

---

# 12. MATERIAL LIBRARY

- aged painted plaster;
- concrete;
- old ceramic tile;
- painted metal;
- rust-light metal;
- corrugated metal;
- old wood;
- glass;
- cheap plastic;
- paper/cardboard;
- cloth;
- asphalt;
- courtyard concrete;
- dirt/damp/mold decals.

Target texture resolution:
- 1K default;
- 2K for hero/large visible surfaces;
- 4K only with clear reason.

---

# 13. ACQUISITION RULES

Khi tải một asset:
1. kiểm license;
2. lưu URL nguồn;
3. lưu author;
4. lưu license text/link;
5. ghi commercial-use status;
6. ghi attribution requirement;
7. lưu original file riêng;
8. không chỉnh đè original;
9. tạo game-ready copy;
10. kiểm scale/pivot/material trước khi đưa vào production.

Ưu tiên:
- CC0;
- commercial-use rõ ràng;
- source chính thức;
- asset modular;
- style gần nhau;
- không phụ thuộc Blender-heavy cleanup nếu máy dev không gánh nổi.

---

# 14. NAMING / FOLDER SUGGESTION

```text
assets/
  3d/
    architecture/
    furniture/
    props/
    characters/
    vehicles/
  materials/
  textures/
  audio/
    ambience/
    sfx/
    music/
  ui/
  docs/
```

Godot-side:
```text
res://assets/
res://scenes/props/
res://scenes/interactables/
res://scenes/npc/
res://systems/events/
res://systems/state/
```

---

# 15. DO NOT OVER-COLLECT

Không săn asset theo kiểu “thấy đẹp là tải”.

Chỉ ưu tiên asset nếu ít nhất một điều đúng:
- nằm trong hub đã khóa;
- phục vụ event;
- xuất hiện nhiều scene;
- là hero prop;
- thay thế được nhiều prop cùng loại;
- giúp visual identity rõ hơn.

Đồ đẹp nhưng không có use-case cụ thể để sau.
