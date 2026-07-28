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
| 0:30–1:00 | 6 | Existing solutions: expensive, need a network, invade privacy |
| 1:00–1:35 | 8 → 10 | What the product is; four steps, all running locally |
| 1:35–2:05 | 11 | Why the Arduino UNO Q specifically — the dual-brain fit |
| 2:05–2:45 | 12 | Escalating alert **+ false-alarm defence** |
| 2:45–3:40 | 16 → 17 | TRL 4, not starting from zero **+ performance defence** |
| 3:40–4:15 | 25 → 26 | Fleets first, then every alertness-critical industry |
| 4:15–5:00 | 30 | Four criteria summarised + the ask + emotional close |

**Rule:** two sentences per slide, maximum. Never read the slide aloud.

---

## 2. The script (~730 words ≈ 5:00)

### [0:00] Slide 1 — Title
> We are team **ML_IoT_Love50**, and this is **DrowsyGuard**.
> Let me start with a number.

*(Cut straight to slide 4 — no long introductions)*

### [0:08] Slide 4 — Drowsy driving is a silent killer
> A driver who micro-sleeps for **three seconds** at ninety kilometres an hour travels **one hundred metres with nobody driving**.
>
> *(pause one beat)*
>
> Those three seconds separate a normal delivery from a fatal crash. The risk is highest for long-haul, coach and ride-hailing drivers — the people who drive at night, on long shifts.

### [0:30] Slide 6 — Existing solutions leave a gap
> This problem is already solved — but only for the wealthy. Driver monitoring ships on premium cars. Cloud dashcams need a network, they add latency, and they upload the driver's face to a server.
>
> The gap is clear: **there is no low-cost add-on that fits any vehicle, runs fully offline, and collects nothing.**

### [1:00] Slide 8 — DrowsyGuard in one line
> That is **DrowsyGuard**. A small device on the dashboard, a camera facing the driver, detecting drowsiness **on the edge**, and waking the driver before it is too late.

### [1:15] Slide 10 — How it works
> Four steps: capture the face, analyse it, score the drowsiness level from zero to three, then act.
>
> **All four steps run locally.** No frame ever leaves the unit — so the system reacts instantly, and the driver's face is never uploaded anywhere.

### [1:35] Slide 11 — System architecture
> And this is exactly why we chose the **Arduino UNO Q**. The board has two brains. **Linux on the Qualcomm QRB2210** runs YOLO for eye and face detection. The **STM32U585 microcontroller** handles real-time control in under one hundred milliseconds.
>
> Our problem needs precisely those two things, on one board. This is not hardware chosen for decoration — it matches the architecture of the problem.

### [2:05] Slide 12 — Escalating alert ladder *(+ false-alarm defence)*
> The alert **escalates through four levels**: a soft beep, then seat vibration and cold air, and finally a loud alarm with hazard lights and an SOS with GPS coordinates.
>
> That escalation is also how we handle **false alarms**. The decision never rests on a single frame — it is based on **PERCLOS, the accumulated eye-closure ratio over a sixty-second window**. Level one is only a soft beep, so an error costs nothing. And the driver always has the **"I am awake"** button to acknowledge — which we then use to personalise their threshold.

### [2:45] Slide 16 — Technology Readiness Level ⭐
> On technical readiness: today we are at **TRL 4 — validated in the lab**. Our target for Hack-Day is **TRL 6 — running in a real vehicle cabin**.

### [3:00] Slide 17 — What already works today *(+ performance defence)*
> And we are **not starting from zero**. Four things are already in place.
>
> **One** — this workload is **already proven on the UNO Q itself**: Arduino App Lab ships a working on-camera face detector on this exact board.
> **Two** — **the datasets are secured**: labelled eye-state images, YOLO-ready.
> **Three** — **the toolchain is installed**: Arduino CLI, Flasher CLI, and the Qualcomm AI Hub client.
> **Four** — **the alert logic is specified**: PERCLOS thresholds and the four levels.
>
> On performance, we know the QRB2210 has no large NPU, so we use a **YOLO nano backbone quantized to INT8**. And this problem does not demand thirty frames per second — because PERCLOS runs on a sixty-second window, **five to ten frames per second is enough**. Our first task with the board is to measure the real figure and report it.
>
> What we are missing is exactly the **hardware** — to measure real performance, wire the actuators, and close the loop inside a cabin.

### [3:40] Slides 25 → 26 — Application domains
> Our first market is **commercial fleets**: logistics, coach operators, ride-hailing. They already pay for safety and telematics, they buy in volume, and they measure the return directly in incidents avoided.
>
> But the core technology travels much further — heavy machinery operators, train drivers, ship watchkeepers, mine haul trucks. **Anywhere a human being must stay alert.** Only the mounting and the level-three action change.

### [4:15] Slide 30 — In summary
> To summarise. The **problem** is real and lethal. The **product** detects on-device and alerts in under two hundred milliseconds, with no network and no privacy cost. Our **technical readiness** is TRL 4, built on blocks that are already proven. The **application domains** start with fleets and extend to every alertness-critical industry.
>
> What we ask for is the **loaned Arduino UNO Q, access to Qualcomm's SDKs, and mentorship from Qualcomm engineers** — to turn a validated pipeline into a working in-cabin prototype by the sixteenth of August.

### [4:45] Close
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
| INT8 | "int-eight" |
| TRL 4 / TRL 6 | "T-R-L four" / "T-R-L six" |
| QRB2210 | "Q-R-B twenty-two ten" |
| STM32U585 | "S-T-M thirty-two U five-eight-five" |
| 16 August | "the sixteenth of August" |
| ML_IoT_Love50 | "M-L I-o-T Love Fifty" |

---

## 4. Recording guide

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
