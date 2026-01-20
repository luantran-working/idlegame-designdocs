# Thiết kế nhân vật

Tài liệu này cung cấp yêu cầu chi tiết cho việc thiết kế nhân vật (Character Art), bao gồm phong cách, kích thước, và danh sách animation cần thiết.

---

## 1. Phong cách nghệ thuật (Art style)

| Thuộc tính     | Yêu cầu                                                                         |
| :------------- | :------------------------------------------------------------------------------ |
| **Phong cách** | Cartoon 2D, hơi hướng Chibi nhưng tỉ lệ cơ thể 1:2.5 hoặc 1:3 (đầu to vừa phải) |
| **Vibe**       | Hài hước, bình dân, đậm chất đường phố Việt Nam                                 |
| **Đường nét**  | Bold outline (viền đậm) màu nâu đen hoặc đen #212121, độ dày 2-3px              |
| **Đổ bóng**    | Cel-shading đơn giản (1 lớp bóng cứng), không dùng gradient quá nhiều           |
| **Góc nhìn**   | 3/4 nhìn sang phải (cho phe ta) hoặc nhìn trực diện hơi nghiêng                 |

### Kích thước xuất file (Export settings)

- **Source file:** PSD hoặc AI (Vector)
- **Sprite sheet:** PNG nền trong suốt
- **Kích thước nhân vật:**
  - Trong game: Cao khoảng 120-150px
  - Source vẽ: 512x512px hoặc 1024x1024px (để dùng cho banner marketing)

---

## 2. Nhân vật chính (Player character)

Đây là nhân vật xuất hiện 100% thời gian, cần thiết kế trung tính nhưng dễ nhận diện.

### 2.1. Concept ngoại hình

| Chi tiết            | Mô tả                                                                                         |
| :------------------ | :-------------------------------------------------------------------------------------------- |
| **Giới tính**       | Nam                                                                                           |
| **Độ tuổi**         | 20-25 tuổi (thanh niên)                                                                       |
| **Khuôn mặt**       | Biểu cảm hơi "ngơ" hoặc nghiêm túc thái quá (tạo sự hài hước)                                 |
| **Trang phục**      | - Áo ba lỗ trắng (hơi ố vàng)<br />- Quần đùi hoa hoặc quần đùi thể dục<br />- Chân đi dép tổ ong |
| **Vũ khí mặc định** | Cầm một cây gậy gỗ hoặc cục gạch                                                              |

### 2.2. Danh sách animation

| Tên          | Số frames | Mô tả hành động                                               |
| :----------- | :-------- | :------------------------------------------------------------ |
| **Idle**     | 4-8       | Đứng thở, nhún nhảy nhẹ, tay đung đưa, mắt chớp               |
| **Walk/Run** | 8-12      | Dáng chạy lon ton hoặc chạy hối hả (dùng chung cho di chuyển) |
| **Attack 1** | 6-8       | Vung tay đánh mạnh (dùng cho vũ khí cận chiến)                |
| **Attack 2** | 6-8       | Giơ tay ném hoặc bắn (dùng cho vũ khí tầm xa/skill)           |
| **Hit**      | 2-4       | Giật mình lùi lại, mặt nhăn nhó, flash trắng                  |
| **Die**      | 8-10      | Ngã ngửa ra sau, hoặc biến thành bia mộ/hồn ma bay lên        |
| **Win**      | 6-8       | Giơ 2 tay chữ V, cười toe toét                                |

---

## 3. Đồng đội (Teammates)

Các nhân vật hỗ trợ, mỗi người có đặc điểm nhận dạng riêng (Silhouette distinct).

### Bảng tóm tắt Character Concept

| Nhân vật | Vai trò | Key Visual (Ngoại hình) | Vũ khí / Phụ kiện |
| :--- | :--- | :--- | :--- |
| **Chú Ba xe ôm** | Tanker | Trung niên, bụng bia, mũ cối, áo sơ mi sờn | Xe máy Dream cũ, cái bơm xe |
| **Cô Tư bán nước** | Support | Phốp pháp, đồ bộ hoa, nón lá | Ghế nhựa, quạt nan, ca nước đá |
| **Anh Bảy thợ điện** | Mage | Gầy gò, cao lêu nghêu, áo cam bảo hộ, đai đồ nghề | Cuộn dây điện, kìm, sào gỡ điện |
| **Chị Mười bán cá** | Warrior | Khỏe mạnh, bắp tay to, tạp dề cao su, ủng | Cá ngừ đông lạnh nguyên con |
| **Ninja Lead** | Tanker | Kín mít, áo chống nắng hoa văn, kính râm | Xe tay ga, đèn xi nhan |

### 3.1. Chú Ba xe ôm (Tanker)

| Chi tiết | Mô tả | Minh họa (Concept) |
| :--- | :--- | :--- |
| **Ngoại hình** | - Đàn ông trung niên, bụng hơi bia<br />- Da ngăm đen vì nắng gió<br />- Đội mũ cối xanh<br />- Mặc áo sơ mi xanh công nhân/xe ôm sờn vai | ![Chú Ba Xe Ôm](./images/chu_ba_xe_om.png) |
| **Phương tiện** | Luôn ngồi trên hoặc đứng cạnh chiếc xe máy "Dream tàu" cũ kỹ | |
| **Vũ khí** | Cái bơm xe đạp hoặc cái mũ bảo hiểm cầm tay | |
| **Animation Key** | **Skill:** Rồ ga bốc đầu xe lao tới trước | |

### 3.2. Cô Tư bán nước (Support)

| Chi tiết | Mô tả | Minh họa (Concept) |
| :--- | :--- | :--- |
| **Ngoại hình** | - Phụ nữ trung niên, phốp pháp<br />- Mặc bộ đồ bộ (pijama) họa tiết hoa lá cành rực rỡ<br />- Đội nón lá | ![Cô Tư Bán Nước](./images/co_tu_ban_nuoc.png) |
| **Phụ kiện** | Ghế nhựa xanh/đỏ (có thể ngồi lên khi idle), cái quạt nan | |
| **Vũ khí** | Cái quạt nan hoặc ca nước đá | |
| **Animation Key** | **Idle:** Ngồi phe phẩy quạt<br />**Skill:** Hất ca nước trà đá ra phía trước | |

### 3.3. Anh Bảy thợ điện (Mage/DPS)

| Chi tiết | Mô tả | Minh họa (Concept) |
| :--- | :--- | :--- |
| **Ngoại hình** | - Dáng người gầy gò, cao lêu nghêu<br />- Mặc áo cam bảo hộ lao động<br />- Đeo đai lưng lỉnh kỉnh kìm, búa, dây điện | ![Anh Bảy Thợ Điện](./images/anh_bay_tho_dien.png) |
| **Vũ khí** | Một cuộn dây điện lớn hoặc cây sào gỡ điện | |
| **Animation Key** | **Attack:** Quăng dây điện ra xa (như roi)<br />**Skill:** Giơ sào lên trời, điện xẹt xẹt | |

### 3.4. Chị Mười bán cá (Warrior)

| Chi tiết | Mô tả | Minh họa (Concept) |
| :--- | :--- | :--- |
| **Ngoại hình** | - Phụ nữ khỏe mạnh, bắp tay to<br />- Đeo tạp dề cao su chống nước (màu xanh hoặc vàng)<br />- Đi ủng cao su | ![Chị Mười Bán Cá](./images/chi_muoi_ban_ca.png) |
| **Vũ khí** | Một con cá ngừ (hoặc cá tra) đông lạnh siêu to cứng như đá | |
| **Animation Key** | **Attack:** Cầm đuôi cá quất mạnh (như cầm chày)<br />**Skill:** Xoay vòng tròn với con cá (spin attack) | |

### 3.5. Ninja Lead (Special Tanker)

| Chi tiết | Mô tả | Minh họa (Concept) |
| :--- | :--- | :--- |
| **Ngoại hình** | - Kín mít từ đầu đến chân<br />- Áo chống nắng hoa văn sặc sỡ, khẩu trang vải to, kính râm<br />- Ngồi trên xe tay ga dáng giống Honda Lead | ![Ninja Lead](./images/ninja_lead.png) |
| **Vũ khí** | Đèn xi nhan hoặc gương chiếu hậu | |
| **Animation Key** | **Move:** Lạng lách đánh võng<br />**Skill:** Bật đèn pha sáng lòa (Blind) | |

---

## 4. Kẻ địch (Enemies)

Thiết kế đơn giản hơn nhân vật chính, ít chi tiết hơn (low detail) để tối ưu hiệu năng khi xuất hiện số lượng lớn.

### 4.1. Quái thường (Mobs)

| Tên | Mô tả ngắn |
| :--- | :--- |
| **Chó cỏ** | Chó vàng/đen gầy gò, sủa "gâu gâu" text bay lên |
| **Gián khổng lồ** | Con gián to bằng con chó, ghê rợn nhưng hài hước |
| **Chuột cống** | Chuột đứng 2 chân, cầm tăm xỉa răng |
| **Túi rác biết đi** | Túi nilon đen có chân tay, bốc mùi xanh lục |

### 4.2. Boss

Kích thước lớn gấp 2-3 lần nhân vật thường.

| Tên | Mô tả ngắn |
| :--- | :--- |
| **Đại ca khu phố** | Cởi trần, xăm trổ đầy mình, đeo dây chuyền vàng to, bụng phệ |
| **Tổ trưởng khó tính** | Ông già đeo kính lão trễ xuống mũi, tay cầm sổ ghi chép, mặt cau có |
| **Loa phường ma quái** | Cụm loa phường mọc tay chân, bắn ra sóng âm (nốt nhạc) |

---

## 5. Tổng hợp yêu cầu Asset (Asset Checklist)

Bảng chi tiết số lượng frame và kích thước cho Artist.

| Loại Asset | State / Hành động | Kích thước (Px) | Số Frames | Ghi chú |
| :--- | :--- | :--- | :--- | :--- |
| **Nhân vật (Chính & Đồng đội)** | Idle (Đứng yên) | 128x128 | 4-6 | Loop mượt |
| | Walk (Di chuyển) | 128x128 | 6-8 | - |
| | Attack (Đánh thường) | 128x128 | 4-6 | Dứt khoát, có smear frame |
| | Skill (Kỹ năng) | 128x128 | 8-12 | Hiệu ứng đặc biệt kèm theo |
| | Die (Chết) | 128x128 | 8-10 | - |
| **Quái thường (Mobs)** | Walk & Attack | 64x64 / 96x96 | 4-6 | Ít frame hơn nhân vật |
| **Boss** | Idle, Walk, Attack, Skill | 256x256 | 8-12 | Chi tiết cao |
| **Minh họa (Illustration)** | Portrait (Chân dung) | 256x256 | 1 | Dùng cho UI / Hội thoại |
| | Full Body (Toàn thân) | 512x512 | 1 | Dùng cho màn hình Gacha / Info |
