# DrowsyGuard — 5-Minute Video Pitch Script

**Team ML_IoT_Love50** · Qualcomm Future Makers: Hack The Challenge 2026
Deck: `main.pdf` (31 slides) — this script uses only the **10 core slides**.

> **Why this script is built the way it is.** A recorded video is one-way: the judges
> **cannot ask questions**. Any technical doubt left unanswered becomes a silent
> deduction. So the two objections most likely to form in a judge's mind are
> **answered inside the script itself**:
> - *"No large NPU on that chip — can YOLO really run?"* → answered at **3:00**
> - *"What about false alarms?"* → answered at **2:05**
>
> Raising and resolving your own weak points is stronger than waiting to be asked.

---

## 1. Timing map

| Time | Slide | The one thing that must land |
|---|---|---|
| 0:00–0:30 | 1 → 4 | Drowsy driving kills: 3 seconds = 100 metres with nobody driving |
| 0:30–0:55 | 6 | Existing solutions: expensive, need a network, invade privacy |
| 0:55–1:25 | 8 + 10 | What the product is; four steps, all running locally |
| 1:25–1:50 | 11 | Why the Arduino UNO Q specifically — the dual-brain fit |
| 1:50–2:25 | 12 | Escalating alert **+ false-alarm defence** |
| 2:25–3:40 | 16 → 17 | TRL 4, not starting from zero **+ performance defence** |
| 3:40–4:05 | 25 → 26 | Fleets first, then every alertness-critical industry |
| 4:05–4:55 | 30 | Summary + the ask + emotional close |

**Rule:** two sentences per slide, maximum. Never read the slide aloud.

> **Length:** 590 words. At a natural non-native pace of ~120 words per minute this
> lands at **4:55**. If your trial run still overshoots, cut in this order:
> (1) the second sentence of the Application-domains block, (2) the "Four —"
> bullet in slide 17, (3) the first sentence of the summary. Never cut the hook,
> the two defences, or the ask.

---

## 2. The script (590 words ≈ 4:55)

### [0:00] Slide 1 — Title
> We are team **ML_IoT_Love50**. This is **DrowsyGuard**.
> Let me start with a number.

*(Cut straight to slide 4 — no long introduction)*

### [0:08] Slide 4 — Drowsy driving is a silent killer
> A driver who micro-sleeps for **three seconds** at ninety kilometres an hour travels **one hundred metres with nobody driving**.
>
> *(pause one beat)*
>
> Those three seconds separate a normal delivery from a fatal crash. The risk is highest for long-haul, coach and ride-hailing drivers — the people who drive at night.

### [0:30] Slide 6 — Existing solutions leave a gap
> This problem is already solved — but only for the wealthy. Driver monitoring ships on premium cars. Cloud dashcams need a network, add latency, and upload the driver's face to a server.
>
> The gap: **no low-cost add-on that fits any vehicle, runs fully offline, and collects nothing.**

### [0:55] Slides 8 + 10 — The product and how it works
> That is **DrowsyGuard**: a small device on the dashboard, a camera facing the driver.
>
> Four steps — capture, analyse, score the drowsiness level from zero to three, then act. **All four run locally.** No frame ever leaves the unit, so the system reacts instantly and the driver's face is never uploaded.

### [1:25] Slide 11 — System architecture
> This is why we chose the **Arduino UNO Q**. It has two brains: a **Qualcomm processor running Linux** does the AI vision, and a **microcontroller** handles the alerts in real time, in under one hundred milliseconds.
>
> Our problem needs exactly those two things, on one board.

### [1:50] Slide 12 — Escalating alert ladder *(+ false-alarm defence)*
> The alert **escalates through four levels**: a soft beep, then seat vibration and cold air, then a loud alarm with hazard lights and an SOS with GPS.
>
> That escalation is also how we handle **false alarms**. The decision never rests on a single frame — it uses **PERCLOS, the eye-closure ratio over a sixty-second window**. Level one is only a beep, so an error costs nothing. And the driver can always press **"I am awake"**.

### [2:25] Slide 16 — Technology Readiness Level ⭐
> On technical readiness: today we are at **TRL 4, validated in the lab**. Our target for Hack-Day is **TRL 6 — running in a real cabin**.

### [2:40] Slide 17 — What already works today *(+ performance defence)*
> And we are **not starting from zero**. Four things are already in place.
>
> **One** — this workload is **already proven on the UNO Q itself**: Arduino App Lab ships a working on-camera face detector on this exact board.
> **Two** — the **datasets are secured**, labelled and YOLO-ready.
> **Three** — the **toolchain is installed**: Arduino CLI, Flasher CLI, and Qualcomm AI Hub.
> **Four** — the **alert logic is specified**: PERCLOS thresholds and the four levels.
>
> On performance, we know this chip has **no dedicated AI accelerator**, so we use a **small, quantized version of YOLO**. And this problem does not need thirty frames per second — PERCLOS runs on a sixty-second window, so **five to ten is enough**.
>
> What we are missing is exactly the **hardware**.

### [3:40] Slides 25 → 26 — Application domains
> Our first market is **commercial fleets** — logistics, coaches, ride-hailing. They already pay for safety, they buy in volume, and they measure the return in incidents avoided.
>
> But the core travels further: heavy machinery, train drivers, ship watchkeepers, mine haul trucks. **Anywhere a human must stay alert.**

### [4:05] Slide 30 — Summary and the ask
> To summarise: the **problem** is real and lethal. The **product** detects on-device and alerts in under two hundred milliseconds, with no network and no privacy cost. We are at **TRL 4** on proven blocks, starting with fleets.
>
> What we ask for is the **loaned Arduino UNO Q, access to Qualcomm's SDKs, and mentorship from Qualcomm engineers** — to reach a working in-cabin prototype by the sixteenth of August.

### [4:40] Close
> Three seconds of micro-sleep is one hundred metres with nobody driving. We want to win those three seconds back.
>
> **Thank you for watching.**

---

## 3. Speaking the numbers

Non-native delivery breaks most often on numbers. Say them exactly like this:

| Written | Say it as |
|---|---|
| 90 km/h | "ninety kilometres an hour" |
| 100 m | "one hundred metres" |
| 0–3 | "zero to three" |
| <100 ms | "under one hundred milliseconds" |
| <200 ms | "under two hundred milliseconds" |
| 60-second window | "sixty-second window" |
| 5–10 FPS | "five to ten frames per second" |
| TRL 4 / TRL 6 | "T-R-L four" / "T-R-L six" |
| PERCLOS | "PER-close" |
| 16 August | "the sixteenth of August" |
| ML_IoT_Love50 | "M-L I-o-T Love Fifty" |

**Part numbers are deliberately not spoken.** QRB2210, STM32U585, INT8 and YOLOv8
all stay **on the slides**, where the judges can read them — but saying them aloud
costs delivery fluency and buys no extra credit. Say "a Qualcomm processor running
Linux", "a microcontroller", "a small quantized model" instead. The slide carries
the rigour; your voice carries the story.

---

## 4. Recording guide

### OBS Studio setup (this machine)

Installed: **OBS Studio 32.1.0** on Ubuntu 26.04, Wayland + GNOME.
Detected hardware: webcam **Chicony USB2.0 Camera**, mics **AB17X USB Audio** (default) and built-in analog.

**Scene setup — do this once:**

1. **Sources → + Screen Capture (PipeWire)**
   Wayland requires this one; do *not* pick XSHM. GNOME will pop up a screen-share
   permission dialog — allow it, and tick "remember".
   Share the PDF viewer window running the slides in presentation mode.
2. **Sources → + Video Capture Device** → *Chicony USB2.0 Camera* → resize small,
   drag to the lower-right corner (picture-in-picture).
3. **Sources → + Audio Input Capture** → *AB17X USB Audio*.
4. **Settings → Output → Recording**: format **MP4**, quality "High", hardware
   encoder if offered.
5. **Settings → Video**: Base and Output resolution both **1920x1080**, FPS **30**.

**Microphone gain — already applied on this machine:**

Both microphones were verified to capture real audio. Current levels:
USB **150%**, built-in **130%**, ALSA capture 79% with +20 dB mic boost (saved across reboots).

```bash
# check what the current input device and level are
wpctl status | sed -n '/Sources:/,/Filters:/p'
wpctl get-volume @DEFAULT_AUDIO_SOURCE@

# raise / lower the default mic  (-l lifts the 100% ceiling)
wpctl set-volume -l 2.0 @DEFAULT_AUDIO_SOURCE@ 1.5    # 150%
wpctl set-volume -l 2.0 @DEFAULT_AUDIO_SOURCE@ 1.8    # louder, if still quiet
wpctl set-mute   @DEFAULT_AUDIO_SOURCE@ 0             # make sure it is unmuted

# hardware gain for the built-in mic (card 0)
amixer -c 0 sset 'Capture' 80%
amixer -c 0 sset 'Mic Boost' 2        # 0-3, each step ≈ +10 dB
sudo alsactl store                    # persist across reboot
```

> **Do not overdo it.** Past roughly 180% you amplify hiss more than voice. If your
> voice is still weak, move the mic closer — that always beats adding gain.
> Better still, fine-tune inside OBS: **right-click the audio source → Filters → + Gain**,
> and add **+ Noise Suppression (RNNoise)** on the same source to kill room hum.

**Test before the real take — do not skip:**

> Record twenty seconds, then play it back **through headphones**.
> The USB device is currently exposed as an IEC958 digital profile, so confirm it
> is actually picking up your voice. If the waveform stays flat, switch the Audio
> Input Capture source to the built-in analog mic, or change the USB device's
> profile in GNOME Settings → Sound → Input.

Watch the audio meter while speaking: peaks should sit in the **yellow**, never
touching red. Too quiet is fixable in editing; clipping is not.

**Recording the eight blocks:** keep one scene, and simply stop/start recording
between blocks. OBS writes a separate file per take, which is exactly what you
want for editing.

### Audio and video
- **Audio matters more than video.** Use a lavalier mic or headset mic, record in a closed room, switch off fans and air-conditioning. Echo and background noise ruin a pitch faster than anything else.
- **Layout:** full-screen slides with a small webcam window in a corner (picture-in-picture). Judges need to see a face — it builds trust.
- **Lighting:** light source in front of you, never sit with a window behind you.
- **Record in segments.** Do not attempt one continuous five-minute take. Record the eight blocks from the timing map separately, re-shoot only the block you fluff, then edit them together. Far faster.

### Delivery
- **Speak about ten percent slower than feels natural.** With no audience feedback, presenters always drift faster than they think.
- **Pause one full beat** after *"one hundred metres with nobody driving"* — let the number land.
- **Look into the camera lens**, not at the slides. Tape the script next to the webcam if needed.
- Emphasise the phrase **"we are not starting from zero"** — this is the single most persuasive line in the pitch. The judges are choosing ten teams to hand hardware to; they are looking for the teams who will actually ship.

### Editing
- Change slides **on the sentence that mentions them**, never before.
- If you have any prototype, cut in **five to ten seconds of B-roll** — the device, an LED changing colour — over the slide 12 section. A video with real footage beats a video of slides every time.
- Add **subtitles**. Judges may watch with the sound off.
- Check the total: **do not exceed 5:00**. If you run long, cut the Application-domains block at 3:40 down to two sentences.

### If all four members must appear
- **One narrator throughout is best** for a continuous thread.
- If every member must be on camera, split by the **four major sections** — Problem / Product / Technical Readiness / Application Domains — one member per complete section. Do not subdivide further.
- The last speaker delivers the summary and the ask.
