# Thiết kế hiệu ứng UI & Hệ thống

Tài liệu này quy định về các hiệu ứng hình ảnh dành cho giao diện người dùng và các tính năng ngoài thực địa.

---

## 1. Bảng tóm tắt VFX Hệ thống

| Tính năng    | Giai đoạn       | Hiệu ứng hình ảnh                                    | Mục tiêu            |
| :----------- | :-------------- | :--------------------------------------------------- | :------------------ |
| **Gacha**    | Rung lắc        | Thùng gỗ rung, ánh sáng God rays lọt qua kẽ.         | Tạo hồi hộp.        |
|              | Mở nắp          | Nắp văng ra, luồng sáng phẩm chất (Cam/Tím) cột cao. | Gây bất ngờ.        |
| **Nâng cấp** | Lên cấp (Hero)  | Cột sáng vàng, confetti bắn ra, chữ "Level Up".      | Chúc mừng.          |
|              | Ghép đồ (Merge) | Hai món hút nhau, nổ sáng tạo ra món mới cấp cao.    | Cảm giác thành quả. |
| **Tiền tệ**  | Thu hoạch       | Vàng/Kim cương bay parabol từ quái về phía UI.       | Kích thích nhặt đồ. |
|              | Thanh EXP       | Hạt tím bay vào thanh, thanh rung nhẹ khi tích lũy.  | Thấy sự thăng tiến. |

---

## 2. Hiệu ứng Gacha (Mở thùng)

Quy trình hiển thị niềm vui (Joy) khi người chơi nhận được vật phẩm mới.

| Giai đoạn       | Mô tả hiệu ứng                                                                                                                                                                                       |
| :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Chuẩn bị** | Thùng gỗ/Thùng sắt rung lắc mạnh, có ánh sáng (God rays) phát ra qua các kẽ nứt.                                                                                                                     |
| **2. Mở**       | Nắp thùng bật tung (văng ra khỏi màn hình).                                                                                                                                                          |
| **3. Công bố**  | **Đồ thường:** Ánh sáng trắng đơn giản.<br/>**Đồ hiếm:** Cột sáng tím/cam tùy phẩm chất.<br/>**Vật phẩm:** Bay từ trong thùng ra chính giữa màn hình kèm hiệu ứng xoay tròn và lấp lánh (Sparkling). |

---

## 3. Hiệu ứng Nâng cấp (Level Up / Upgrade)

### 3.1. Nhân vật lên cấp

| Thành phần    | Mô tả                                                      |
| :------------ | :--------------------------------------------------------- |
| **Cột sáng**  | Một cột sáng vàng rộng bao quanh nhân vật.                 |
| **Text**      | Chữ "LEVEL UP" bay lên với Animation lò xo (Spring).       |
| **Particles** | Pháo giấy (Confetti) màu sắc bắn ra từ 2 bên mép màn hình. |

### 3.2. Nâng cấp Trang bị / Đồng đội

| Loại nâng cấp   | Hiệu ứng                                                                                                         |
| :-------------- | :--------------------------------------------------------------------------------------------------------------- |
| **Success**     | Hiệu ứng búa đập "Keng" -> Một luồng sáng chạy dọc viền vật phẩm -> Các chỉ số mới bay lên màu xanh lá.          |
| **Merge (Gộp)** | Hai vật phẩm bay vào nhau, xoay tròn tạo thành một hố đen nhỏ -> Vụ nổ ánh sáng nhẹ -> Vật phẩm cấp cao hiện ra. |

---

## 4. Hiệu ứng luồng tiền (Currency Flow)

Cực kỳ quan trọng để kích thích người chơi thu thập tài nguyên.

| Loại tài nguyên       | Mô tả hiệu ứng                                                                                                                                 |
| :-------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **Vàng (Gold)**       | Các đồng xu vàng bay theo đường cong (Parabol) từ vị trí quái chết về phía túi tiền trên góc UI. Có tiếng "Keng" nhỏ khi đồng xu chạm vào túi. |
| **Kim cương (Gem)**   | Bay chậm hơn, có vệt sáng lấp lánh (Shiny trail) phía sau.                                                                                     |
| **Kinh nghiệm (EXP)** | Các hạt năng lượng màu tím bay vào thanh Level.                                                                                                |

---

## 5. Hiệu ứng chuyển cảnh (Transitions)

| Loại chuyển cảnh | hiệu ứng                                                                |
| :--------------- | :---------------------------------------------------------------------- |
| **Vào trận**     | Màn hình thu nhỏ lại vào giữa (Iris close) rồi mở rộng ra bối cảnh mới. |
| **Thất bại**     | Màn hình chuyển sang màu Grayscale (đen trắng) mờ ảo.                   |
| **Thắng trận**   | Một dải lụa đỏ/vàng chạy ngang qua màn hình kèm chữ "CHIẾN THẮNG".      |

---

## 6. Hiệu ứng tương tác UI (Interaction VFX)

| Trạng thái              | Hiệu ứng                                                                                  |
| :---------------------- | :---------------------------------------------------------------------------------------- |
| **Click/Tap**           | Một vòng tròn sóng nước (Ripple) lan tỏa từ vị trí chạm, màu sắc theo theme của nút.      |
| **Hover (PC/Emulator)** | Nút bấm hơi phóng to (Scale 1.05) và phát sáng nhẹ ở viền.                                |
| **Disabled**            | Nút bấm bị xám hóa (Grayscale) và có hiệu ứng rung nhẹ (Shake) nếu người chơi cố bấm vào. |

## 7. Hiệu ứng thành tựu & nhiệm vụ (Achievement VFX)

| Loại thành tựu              | Hiệu ứng                                                                                                             |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------- |
| **Hoàn thành nhiệm vụ**     | Một dải banner hiện ra chính giữa màn hình với icon [Huy hiệu], sau đó thu nhỏ và bay vào icon [Nhiệm vụ] trên menu. |
| **Kỷ lục mới (New Record)** | Hiệu ứng pháo hoa nhỏ nổ rải rác trên màn hình kèm chữ "KỶ LỤC MỚI" nhấp nháy 7 màu.                                 |

## 8. Hiệu ứng tài nguyên đặc biệt (Special Energy VFX)

| Loại hiệu ứng                   | Mô tả                                                                                                       |
| :------------------------------ | :---------------------------------------------------------------------------------------------------------- |
| **Hồi thể lực (Energy Refill)** | Một luồng khí màu xanh dương chảy ngược từ màn hình vào thanh thể lực, thanh thể lực sáng rực lên trong 1s. |
| **Nhận quà từ mail**            | Bao lì rơi từ trên xuống, mở ra có hiệu ứng ánh sáng tỏa tròn.                                              |
