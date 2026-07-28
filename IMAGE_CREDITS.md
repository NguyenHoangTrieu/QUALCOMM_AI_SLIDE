# Image credits — DrowsyGuard slides

Photographs come from openly-licensed pools (Wikimedia Commons, Flickr via the
Openverse API). Board/UI renders are official Arduino product media. Logos are
trademarks used only to identify the competition and platform. Keep this
attribution if the deck is published publicly.

| File | Used on | Source | License |
|------|---------|--------|---------|
| `hero_night.jpg` / `night_drive.jpg` | Title hero | Flickr via Openverse — night highway light trails | CC BY |
| `problem_driver.jpg` | "Drowsy driving is a silent killer" | Flickr via Openverse — "Sleepy driver" | CC BY |
| `car_dashboard.jpg` | "What the product looks like" | Flickr via Openverse — Volvo C30 interior | CC BY |
| `face_landmark.jpg` | "AI model: retrained YOLO detector" | Wikimedia Commons — Dlib face landmark detection | CC BY-SA |
| `applab_detect.png` | "What already works today" | Arduino — App Lab on-camera detector UI (arduino.cc) | Arduino product media |
| `arduino_unoq.png` | "Hardware and cost" | Arduino — UNO Q product render (arduino.cc) | Arduino product media |
| `fleet_truck.jpg` | "Primary domain: road safety" | Flickr via Openverse — semi truck on highway | CC BY |
| `qualcomm_logo.png` / `qualcomm_white.png` | Header / dividers / title | Wikimedia Commons | Trademark of Qualcomm Inc. |
| `mliot_logo.png` / `mliot_banner.png` | Header / title / thank-you | Team asset | Team-owned |

Notes:
- For CC BY / BY-SA photos, retain the author credit from the source page before
  public distribution, or replace with a photo the team shot themselves.
- Arduino UNO Q renders and the App Lab UI are Arduino's official product media,
  used to show the exact hardware/software this project runs on.
- Qualcomm and Arduino names/logos belong to their owners; used only for
  identification in the Hack The Challenge 2026 entry.
- To swap any image, drop a new file into `assets/` with the same name and recompile.

## Rebuilding

```bash
cd /home/nguyenhoangtrieu/embedded/QUALCOMM_AI
xelatex main.tex && xelatex main.tex     # run twice for TikZ overlays
```
