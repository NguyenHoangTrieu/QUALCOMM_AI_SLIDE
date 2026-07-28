# DrowsyGuard — Script quay video thuyết trình 5 phút

Deck: `main.pdf` (31 slide). Trong 5 phút chỉ dùng **10 slide trụ cột**.

> **Khác biệt cốt lõi so với thuyết trình trực tiếp:** video là một chiều — giám khảo
> **không hỏi lại được**. Mọi nghi ngờ kỹ thuật mà họ có trong đầu, nếu không được trả
> lời ngay trong video, sẽ trở thành điểm trừ âm thầm. Vì vậy script này đã **gài sẵn
> hai câu phòng thủ quan trọng nhất** vào đúng mạch nói:
> - *"Chip không có NPU lớn, YOLO chạy nổi không?"* → đặt ở đoạn TRL (phút 3:20)
> - *"Báo động giả thì sao?"* → đặt ở đoạn thang cảnh báo (phút 2:20)

---

## 1. Bản đồ thời gian

| Thời gian | Slide | Thông điệp cần đọng lại |
|---|---|---|
| 0:00–0:30 | 1 → 4 | Buồn ngủ khi lái giết người: 3 giây = 100 mét không ai lái |
| 0:30–1:00 | 6 | Giải pháp hiện có: đắt, cần mạng, xâm phạm riêng tư |
| 1:00–1:35 | 8 → 10 | Sản phẩm là gì, chạy 4 bước hoàn toàn tại chỗ |
| 1:35–2:05 | 11 | Vì sao đúng Arduino UNO Q — kiến trúc hai não |
| 2:05–2:45 | 12 | Cảnh báo leo thang **+ phòng thủ báo động giả** |
| 2:45–3:40 | 16 → 17 | TRL 4, không bắt đầu từ số 0 **+ phòng thủ FPS** |
| 3:40–4:15 | 25 → 26 | Fleet trước, rồi mọi ngành cần tỉnh táo |
| 4:15–5:00 | 30 | Tóm tắt 4 tiêu chí + lời đề nghị + chốt |

**Nguyên tắc:** mỗi slide tối đa 2 câu. Không đọc chữ trên slide.

---

## 2. Script tiếng Việt (~730 từ ≈ 5 phút)

### [0:00] Slide 1 — Title
> Chúng em là đội **ML IoT**, với dự án **DrowsyGuard**. Xin bắt đầu bằng một con số.

*(Chuyển slide 4 ngay, không giới thiệu dài dòng)*

### [0:08] Slide 4 — Drowsy driving is a silent killer
> Một tài xế ngủ gật **ba giây** ở tốc độ 90 km/h nghĩa là chiếc xe đã đi **một trăm mét trong trạng thái không ai lái**.
>
> Ba giây đó là ranh giới giữa một chuyến hàng bình thường và một tai nạn thảm khốc. Rủi ro cao nhất rơi vào tài xế đường dài, xe khách và tài xế công nghệ — những người chạy đêm, chạy ca dài.

### [0:30] Slide 6 — Existing solutions leave a gap
> Vấn đề này đã có giải pháp — nhưng chỉ dành cho người giàu. Hệ thống cảnh báo tài xế chỉ có trên xe hạng sang. Camera hành trình đám mây thì cần Internet, có độ trễ, và gửi hình ảnh khuôn mặt tài xế lên server.
>
> Khoảng trống rất rõ: **chưa có thiết bị giá rẻ, gắn thêm được cho mọi xe, chạy hoàn toàn offline và không thu thập dữ liệu.**

### [1:00] Slide 8 — DrowsyGuard in one line
> Đó là **DrowsyGuard**. Một thiết bị nhỏ đặt trên taplo, camera hướng vào tài xế, phát hiện buồn ngủ **ngay trên thiết bị**, và đánh thức tài xế trước khi quá muộn.

### [1:15] Slide 10 — How it works
> Bốn bước: camera thu hình, AI phân tích, chấm điểm mức buồn ngủ từ 0 đến 3, rồi kích hoạt cảnh báo.
>
> **Cả bốn bước đều chạy cục bộ.** Không khung hình nào rời khỏi thiết bị — nên hệ thống phản ứng tức thì, và khuôn mặt tài xế không bị gửi đi đâu cả.

### [1:35] Slide 11 — Architecture
> Và đây là lý do chúng em chọn **Arduino UNO Q**. Board này có hai bộ não: **Linux trên Qualcomm QRB2210** chạy YOLO nhận diện mắt và khuôn mặt; **vi điều khiển STM32U585** lo phần điều khiển thời gian thực dưới một trăm mili-giây.
>
> Bài toán của chúng em cần đúng hai thứ đó, trong đúng một board. Đây không phải chọn phần cứng cho có — nó khớp với kiến trúc của bài toán.

### [2:05] Slide 12 — Escalating alert ladder *(+ phòng thủ báo động giả)*
> Cảnh báo được thiết kế **leo thang bốn mức**: bíp nhẹ, rồi rung ghế và quạt gió, cuối cùng là còi lớn, bật đèn khẩn cấp và gửi SOS kèm tọa độ.
>
> Thiết kế leo thang cũng chính là cách chúng em xử lý **báo động giả**. Quyết định không dựa vào một khung hình đơn lẻ, mà dựa trên **PERCLOS — tỷ lệ thời gian mắt nhắm tích lũy trên cửa sổ sáu mươi giây**. Mức một chỉ là một tiếng bíp nhẹ, nên nếu có sai cũng không gây hại. Và tài xế luôn có nút **"Tôi vẫn tỉnh"** để xác nhận, dữ liệu đó dùng để cá nhân hóa ngưỡng cho từng người.

### [2:45] Slide 16 — TRL ⭐
> Về mức độ sẵn sàng kỹ thuật: hiện chúng em ở **TRL 4 — đã kiểm chứng trong phòng lab**. Mục tiêu đến Hack-Day là **TRL 6 — chạy thật trong cabin xe**.

### [3:00] Slide 17 — What already works today *(+ phòng thủ hiệu năng)*
> Và chúng em **không bắt đầu từ con số không**. Bốn thứ đã có:
>
> Một — bài toán này **đã được chứng minh chạy được trên chính UNO Q**: Arduino App Lab có sẵn bộ nhận diện khuôn mặt on-camera trên board này.
> Hai — **dữ liệu đã có**, các bộ ảnh gán nhãn trạng thái mắt, sẵn sàng cho YOLO.
> Ba — **toolchain đã cài xong**: Arduino CLI, Flasher CLI và Qualcomm AI Hub.
> Bốn — **logic cảnh báo đã đặc tả xong**, gồm ngưỡng PERCLOS và bốn mức.
>
> Về hiệu năng, chúng em ý thức rõ QRB2210 không có NPU lớn, nên dùng **YOLO bản nano lượng tử hóa INT8**. Bài toán này cũng không đòi ba mươi khung hình mỗi giây — vì PERCLOS tính trên cửa sổ sáu mươi giây, nên **năm đến mười FPS là đủ**. Việc đầu tiên khi nhận board là đo FPS thật và báo cáo con số.
>
> Thứ chúng em còn thiếu chính xác là **phần cứng** — để đo hiệu năng thật, đấu dây cơ cấu chấp hành và đóng vòng lặp trong cabin.

### [3:40] Slide 25 → 26 — Application domains
> Thị trường đầu tiên là **đội xe thương mại**: logistics, xe khách, taxi công nghệ. Họ đã chi tiền cho an toàn và telematics, mua theo số lượng, và đo được hiệu quả bằng số vụ tai nạn tránh được.
>
> Nhưng lõi công nghệ đi xa hơn nhiều: vận hành máy công nghiệp, lái tàu, thủy thủ trực ca, xe tải mỏ. **Bất cứ đâu con người buộc phải tỉnh táo** — chỉ đổi cách gắn thiết bị và hành động ở mức ba.

### [4:15] Slide 30 — In summary
> Tóm lại. **Vấn đề** có thật và chết người. **Sản phẩm** phát hiện tại chỗ, cảnh báo dưới hai trăm mili-giây, không cần mạng, không đánh đổi riêng tư. **Mức độ sẵn sàng** là TRL 4 với các khối đã được chứng minh. **Lĩnh vực áp dụng** bắt đầu từ đội xe rồi lan sang mọi ngành cần sự tỉnh táo.
>
> Điều chúng em xin là **board Arduino UNO Q cho mượn, quyền truy cập SDK Qualcomm, và sự đồng hành của kỹ sư Qualcomm** — để biến một pipeline đã kiểm chứng thành nguyên mẫu chạy thật trong cabin trước ngày mười sáu tháng Tám.

### [4:45] Chốt
> Ba giây ngủ gật là một trăm mét không ai lái. Chúng em muốn giành lại ba giây đó.
>
> **Xin cảm ơn ban giám khảo đã lắng nghe.**

---

## 3. English version (~720 words)

**[0:00] Slide 1** — We are team **ML IoT**, and this is **DrowsyGuard**. Let me start with a number.

**[0:08] Slide 4** — A driver who micro-sleeps for **three seconds** at 90 km/h travels **one hundred metres with nobody driving**. Those three seconds separate a normal delivery from a fatal crash. The highest risk falls on long-haul, coach and ride-hailing drivers — the people who drive at night, on long shifts.

**[0:30] Slide 6** — This problem is already solved — but only for the wealthy. Driver monitoring exists on premium cars. Cloud dashcams need a network, add latency, and upload the driver's face to a server. The gap is clear: **there is no low-cost add-on that fits any vehicle, runs fully offline, and collects nothing.**

**[1:00] Slide 8** — That is **DrowsyGuard**: a small dashboard device with a camera facing the driver, detecting drowsiness **on the edge**, and waking the driver before it is too late.

**[1:15] Slide 10** — Four steps: capture, analyse, score the drowsiness level from 0 to 3, then act. **All four run locally.** No frame ever leaves the unit — so the system reacts instantly, and the driver's face is never uploaded.

**[1:35] Slide 11** — This is exactly why we chose the **Arduino UNO Q**. It has two brains: **Linux on the Qualcomm QRB2210** runs YOLO for eye and face detection; the **STM32U585 microcontroller** handles real-time control in under one hundred milliseconds. Our problem needs precisely those two things, on one board. The hardware is not decoration — it matches the architecture of the problem.

**[2:05] Slide 12** — The alert **escalates through four levels**: a soft beep, then seat vibration and cold air, then a loud alarm with hazard lights and an SOS with GPS.

That escalation is also how we handle **false alarms**. The decision never rests on a single frame — it is based on **PERCLOS, the accumulated eye-closure ratio over a sixty-second window**. Level one is only a soft beep, so an error costs nothing. And the driver always has the **"I am awake"** button to acknowledge, which we then use to personalise their threshold.

**[2:45] Slide 16** — On technical readiness: we are at **TRL 4 — validated in the lab**. Our target for Hack-Day is **TRL 6 — running in a real cabin**.

**[3:00] Slide 17** — And we are **not starting from zero**. Four things are already in place. One — this workload is **already proven on the UNO Q itself**: Arduino App Lab ships a working on-camera face detector on this board. Two — **the datasets are secured**, labelled eye-state images, YOLO-ready. Three — **the toolchain is installed**: Arduino CLI, Flasher CLI and Qualcomm AI Hub. Four — **the alert logic is specified**, with PERCLOS thresholds and the four levels.

On performance, we know the QRB2210 has no large NPU, so we use a **YOLO nano backbone quantized to INT8**. This problem also does not demand thirty frames per second — because PERCLOS runs on a sixty-second window, **five to ten FPS is enough**. Our first task with the board is to measure the real figure and report it.

What we are missing is exactly the **hardware** — to measure real performance, wire the actuators, and close the loop in a cabin.

**[3:40] Slides 25–26** — Our first market is **commercial fleets**: logistics, coaches, ride-hailing. They already pay for safety and telematics, they buy in volume, and they measure the return in incidents avoided. But the core travels much further — heavy machinery operators, train drivers, ship watchkeepers, mine haul trucks. **Anywhere a human must stay alert.** Only the mounting and the level-three action change.

**[4:15] Slide 30** — To summarise. The **problem** is real and lethal. The **product** detects on-device and alerts in under two hundred milliseconds, with no network and no privacy cost. Our **readiness** is TRL 4 with proven building blocks. The **domains** start with fleets and extend to every alertness-critical industry.

What we ask for is the **loaned Arduino UNO Q, Qualcomm SDK access and engineer mentorship** — to turn a validated pipeline into a working in-cabin prototype by the sixteenth of August.

**[4:45]** — Three seconds of micro-sleep is one hundred metres with nobody driving. We want to win those three seconds back. **Thank you for watching.**

---

## 4. Hướng dẫn quay video

### Kỹ thuật quay
- **Âm thanh quan trọng hơn hình.** Dùng mic cài áo hoặc tai nghe có mic, quay trong phòng kín, tắt quạt/điều hòa. Tiếng vọng và tiếng ồn làm hỏng video nhanh hơn bất cứ thứ gì.
- **Bố cục:** ghi màn hình slide toàn khung, chèn khung nhỏ webcam người nói ở góc (picture-in-picture). Giám khảo cần thấy mặt người thuyết trình — tạo niềm tin.
- **Ánh sáng:** nguồn sáng phía trước mặt, không ngồi ngược sáng cửa sổ.
- **Quay từng đoạn theo mục.** Đừng cố quay một mạch 5 phút. Quay 8 đoạn theo bảng thời gian, sai đoạn nào quay lại đoạn đó rồi ghép — nhanh hơn nhiều.

### Nhịp nói
- **Nói chậm hơn cảm giác tự nhiên khoảng 10%.** Video không có phản hồi khán giả nên người nói hay bị cuốn nói nhanh.
- **Dừng một nhịp sau câu "một trăm mét không ai lái"** — để con số ngấm.
- **Nhìn vào camera**, không nhìn slide. Dán script cạnh webcam nếu cần.

### Dựng
- Chuyển slide **đúng lúc nói tới**, không chuyển trước.
- Nếu có nguyên mẫu, chèn **5–10 giây B-roll** cảnh thiết bị/đèn LED đổi màu vào đoạn slide 12. Video có cảnh thật luôn thắng video chỉ có slide.
- Thêm **phụ đề** — giám khảo có thể xem không bật loa.
- Kiểm tra tổng thời lượng: **không vượt 5:00**. Nếu dư, cắt bớt đoạn Application domains (4:15) xuống 2 câu.

### Phân vai nếu quay nhóm
- **Ưu tiên một người dẫn toàn bộ** cho liền mạch.
- Nếu bắt buộc đủ 4 thành viên xuất hiện: chia theo **4 phần lớn** (Vấn đề / Sản phẩm / Sẵn sàng kỹ thuật / Lĩnh vực áp dụng), mỗi người một phần trọn vẹn — đừng chia nhỏ hơn.
- Người cuối cùng nói phần tóm tắt và lời đề nghị.
