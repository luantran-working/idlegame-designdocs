# Thiết kế môi trường

Tài liệu này quy định chi tiết về bối cảnh, các lớp nền (Background Layers) và không gian nghệ thuật cho từng khu vực trong game.

---

## 1. Quy chuẩn kỹ thuật

### 1.1. Hệ thống Parallax 5 lớp

Để tạo chiều sâu tối đa trên màn hình dọc, mỗi môi trường cần được chia tối thiểu thành 5 lớp:

1.  **Lớp Sky (Bầu trời):** Di chuyển chậm nhất (coeff: 0.05). Gồm mây, mặt trời/mặt trăng.
2.  **Lớp Far (Xa):** Di chuyển chậm (coeff: 0.1). Các tòa nhà chọc trời mờ ảo, núi.
3.  **Lớp Mid (Giữa):** Di chuyển trung bình (coeff: 0.3). Dãy nhà ống, cây cối lớn.
4.  **Lớp Near (Gần):** Di chuyển nhanh (coeff: 0.6). Cột điện, biển hiệu, sạp hàng.
5.  **Lớp Ground (Sàn):** Di chuyển nhanh nhất (coeff: 1.0). Mặt đường, vỉa hè, vết nứt.

### 1.2. Thông số hình ảnh

- **Tỷ lệ:** 9:16 (Mặc định).
- **Resolution:** 1080x1920 (Source).
- **Chiều ngang:** Thiết kế loop ngang (Seamless loop) với chiều ngang từ 2500px - 3000px để cuộn liên tục.
- **Lighting:** Mỗi chương có 3 biến thể màu: Sáng - Chiều - Tối.

---

## 2. Danh sách chương & Bối cảnh chi tiết

### Bảng tóm tắt môi trường

| Chương       | Chủ đề chính     | Đặc điểm nhận dạng                                                   | Animation môi trường                                      | Hình ảnh minh họa                  |
| :----------- | :--------------- | :------------------------------------------------------------------- | :-------------------------------------------------------- | :--------------------------------- |
| **Chương 1** | Ngõ nhỏ phố xưa  | Dây điện chằng chịt, tường vàng rêu, cột điện quảng cáo hút bể phốt. | Lá xà cừ rơi, quạt trần quay chậm, bồ câu cất cánh.       | ![Chương 1](./images/chuong_1.png) |
| **Chương 2** | Chợ cóc dân sinh | Bạt che xanh đỏ, sạp rau củ, bảng hiệu vẽ tay, vũng nước loang dầu.  | Bạt rung theo gió, khói nồi nước lèo, ruồi bay nhỏ.       | ![Chương 2](./images/chuong_2.png) |
| **Chương 3** | Công viên        | Ghế đá "tặng bởi...", hàng rào xanh gỉ, loa phường trên cây.         | Các cụ tập dưỡng sinh, gợn sóng mặt hồ, lá rơi phủ đường. | ![Chương 3](./images/chuong_3.png) |
| **Chương 4** | Bến xe liên tỉnh | Xe khách 45 chỗ, hành khách chờ, bến bãi nứt vỡ, xe ôm vẫy khách.    | Khói pô xe, hành khách đi lại, ánh đèn pha quét qua.      | ![Chương 4](./images/chuong_4.png) |

---

### Chương 1: Ngõ Nhỏ Phố Xưa

- **Chủ đề:** Sự giao thoa giữa Hà Nội cũ và nhịp sống hiện đại.
- **Bảng màu:** Vàng thư (tường cũ), Xanh rêu, Đỏ gạch.

| Hạng mục                 | Chi tiết                                                                                                                                                                                    |
| :----------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Chi tiết đặc trưng**   | - Dây điện chằng chịt như mạng nhện.<br/>- Cột điện dán kín quảng cáo "Khoan cắt bê tông", "Hút bể phốt".<br/>- Quán trà đá vỉa hè với ghế nhựa xanh đỏ.<br/>- Cục nóng điều hòa chảy nước. |
| **Animation môi trường** | - Quạt trần trong quán cũ quay chậm.<br/>- Chim bồ câu bay lên từ nóc nhà.<br/>- Lá cây xà cừ rơi lưa thưa.                                                                                 |

### Chương 2: Chợ Cóc Dân Sinh

- **Chủ đề:** Sự xô bồ, náo nhiệt của chợ Việt Nam.
- **Bảng màu:** Xanh bạt, Đỏ tươi (thịt), Cam/Vàng (trái cây).

| Hạng mục                 | Chi tiết                                                                                                                                                                            |
| :----------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chi tiết đặc trưng**   | - Dãy bạt che mưa nhấp nhô đủ màu.<br/>- Xe đẩy tự chế, mẹt hoa quả, thúng xôi.<br/>- Vũng nước đọng loang lổ vết dầu.<br/>- Bảng hiệu vẽ tay: "Tạp hóa Cô Lan", "Bún đậu mắm tôm". |
| **Animation môi trường** | - Bạt che rung nhẹ theo gió.<br/>- Ruồi bay quanh sạp hàng (nhỏ).<br/>- Khói bốc lên từ nồi nước lèo của hàng bún.                                                                  |

### Chương 3: Công Viên Thống Nhất

- **Chủ đề:** Không gian xanh, thư giãn và đời sống cộng đồng.
- **Bảng màu:** Xanh lá đậm, Xanh hồ thủy, Vàng nắng.

| Hạng mục                 | Chi tiết                                                                                                                                                              |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chi tiết đặc trưng**   | - Hàng rào sắt màu xanh lá cây mục gỉ.<br/>- Ghế đá phun sơn "tặng bởi...".<br/>- Dụng cụ tập thể dục ngoài trời màu vàng xanh.<br/>- Loa phường gắn trên cây cổ thụ. |
| **Animation môi trường** | - Mặt hồ có gợn sóng lăn tăn.<br/>- Các cụ tập dưỡng sinh (Lớp Mid).<br/>- Lá rơi phủ kín mặt đường lát gạch.                                                         |

---

## 3. Hiệu ứng môi trường (Environment VFX)

Để tăng tính sống động, mỗi màn chơi sẽ có các "Particle Layer" phủ lên:

| Loại hiệu ứng            | Mô tả                                                |
| :----------------------- | :--------------------------------------------------- |
| **Bụi mịn (Dust)**       | Các hạt bụi nhỏ bay lơ lửng trong nắng.              |
| **Vết nứt (Decals)**     | Các vết nứt, vết ố trên tường xuất hiện ngẫu nhiên.  |
| **Thời tiết (Mưa phùn)** | Vệt mưa mỏng, trắng mờ.                              |
| **Thời tiết (Nắng gắt)** | Hiệu ứng Bloom mạnh ở các vùng sáng, Lens flare nhẹ. |
