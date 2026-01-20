# Đặc tả thiết kế vật phẩm & UI (Item & UI asset specs)

Tài liệu này liệt kê các tài nguyên hình ảnh (sprites/icons) cần thiết cho hệ thống tiền tệ, vật phẩm tiêu thụ và giao diện người dùng (GUI).

---

## 1. Tiền tệ & Tài nguyên (Currencies & Resources)

Icon cần thiết kế đơn giản, dễ đọc ở kích thước nhỏ (trên thanh header).

| Tên                     | Mô tả hình ảnh (Visual)                                                    | Kích thước | Ghi chú                             |
| :---------------------- | :------------------------------------------------------------------------- | :--------- | :---------------------------------- |
| **Vàng (Gold)**         | Đồng xu hình tròn, màu vàng kim loại, có ký hiệu '$' hoặc chữ 'V' dập nổi. | 64x64      | Cần bản stack: 1 xu, 3 xu, đống xu. |
| **Kim Cương (Gem)**     | Viên kim cương cắt giác (cut structure), màu xanh dương sáng hoặc ngũ sắc. | 64x64      | Cần bản stack: 1 viên, đống viên.   |
| **Cờ lê (Scrap)**       | Cờ lê kim loại màu xám, dính chút dầu mỡ.                                  | 64x64      | Dùng nâng cấp trang bị.             |
| **Bí kíp (Skill Book)** | Quyển sách bìa xanh dương, có hào quang tri thức.                          | 64x64      | Dùng nâng skill.                    |
| **Mảnh kỹ năng**        | Một trang giấy rách từ cuốn bí kíp, có ký tự cổ.                           | 64x64      |                                     |
| **Bánh mì (Bread)**     | Ổ bánh mì kẹp thịt (Bánh mì Việt Nam) ngon lành.                           | 64x64      | Dùng tăng Exp đồng đội.             |
| **Mảnh nhân vật**       | Mảnh ghép hình jigsaw (puzzle piece) có dấu '?' hoặc hình bóng người.      | 64x64      | Dùng tăng sao đồng đội.             |
| **Vé Gacha (Ticket)**   | Tấm vé giấy màu vàng/đỏ, phong cách vé số kiến thiết hoặc vé xem phim cũ.  | 64x64      |                                     |
| **Chìa khóa (Key)**     | Chìa khóa vàng cổ điển.                                                    | 64x64      |                                     |
| **Rương AFK**           | Rương gỗ bọc sắt, có vẻ nặng trịch.                                        | 128x128    |                                     |
| **Đá tẩy luyện**        | Viên đá ma thuật hình cầu, xoáy màu tím/hồng bên trong.                    | 64x64      |                                     |

---

## 2. Icon tính năng (Feature Icons)

Dùng cho 5 Tab điều hướng và các nút chức năng trên màn hình chính.
**Style:** Icon dạng Stroke (nét vẽ) hoặc Flat color đơn giản, có 2 trạng thái Active (Sáng) và Inactive (Xám).

### 2.1. Thanh điều hướng đáy (Bottom Bar)

| Tab       | Tên      | Icon mô tả                                            |
| :-------- | :------- | :---------------------------------------------------- |
| **Tab 1** | Chỉ số   | Hình người (body) hoặc cơ bắp tay.                    |
| **Tab 2** | Trang bị | Hình cái túi (inventory bag) hoặc thanh kiếm + khiên. |
| **Tab 3** | Kỹ năng  | Hình quyển sách phép hoặc tia sét.                    |
| **Tab 4** | Đồng đội | Hình 3 đầu người (icon group) hoặc cái bắt tay.       |
| **Tab 5** | Gacha    | Hình vòng quay may mắn hoặc hộp quà bí ẩn.            |

### 2.2. Nút màn hình chiến đấu (Battle HUD)

| Nút          | Icon mô tả                                          |
| :----------- | :-------------------------------------------------- |
| **Avatar**   | Khung tròn bao quanh mặt nhân vật.                  |
| **Settings** | Bánh răng cưa (Gear).                               |
| **Tốc độ**   | Nút Play (x1) và Fast Forward (x2).                 |
| **Auto**     | Vòng tròn tái chế (Recycle symbol) hoặc chữ "AUTO". |
| **Boss**     | Đầu lâu quỷ hoặc icon Boss cảnh báo nguy hiểm.      |
| **Nạp đầu**  | Hộp quà có ruy băng đỏ.                             |
| **Nhiệm vụ** | Cuộn giấy da có dấu tích xanh (Checkmark).          |
| **Mail**     | Phong bì thư.                                       |
| **Rank**     | Cái cúp vàng (Trophy).                              |

---

## 3. Các thành phần UI chung (Common UI Elements)

Cần thiết kế theo bộ (Atlas) để tái sử dụng. Style: Cartoon, nút bấm nổi 3D nhẹ.

### 3.1. Các loại nút bấm (Buttons)

- **Nút xanh lá (Primary):** Dùng cho hành động xác nhận, nâng cấp, nhận quà (cảm giác tích cực).
- **Nút vàng/cam (Important):** Dùng cho nút shop, nạp, hoặc hành động tốn tiền (kêu gọi hành động).
- **Nút đỏ (Danger/Close):** Dùng cho nút tắt, xóa, hủy bỏ.
- **Nút xanh dương (Info/Secondary):** Dùng cho các nút chức năng phụ.
- **Nút xám (Disabled):** Trạng thái không thể bấm.

### 3.2. Khung cửa sổ (Panels/Popups)

- **Khung nền (Popup BG):** Hình chữ nhật bo góc, màu giấy cũ (beige) hoặc trắng kem, viền nâu gỗ. Texture giấy nhẹ.
- **Header (Tiêu đề):** Dải băng (Ribbon) vắt ngang phía trên popup để ghi tên tiêu đề.
- **Nút tắt (Close btn):** Dấu X đỏ nằm góc trên phải popup.

### 3.3. Thanh tiến độ (Progress Bars)

- **Thanh HP:** Màu đỏ (Enemy) và Xanh lá (Player).
- **Thanh Exp:** Màu vàng hoặc xanh lơ.
- **Thanh Loading/Download:** Màu xanh dương.

---

## 4. Item Shop & Gacha Assets

### 4.1. Gói nạp (IAP Bundles)

- **Gói tay nải:** Túi vải nhỏ đựng ít kim cương.
- **Gói rương gỗ:** Rương gỗ chứa vừa vừa kim cương.
- **Gói rương vàng:** Rương vàng tràn ngập kim cương.
- **Gói xe tải:** Xe tải chở đầy kim cương (gói to nhất).

### 4.2. Thùng Gacha (Gacha Box)

- **Style:** Thùng carton dán băng dính (như thùng hàng ship online).
- **Trạng thái 1:** Đóng kín.
- **Trạng thái 2:** Rung lắc, phồng lên, ánh sáng lọt ra khe.
- **Trạng thái 3:** Bung nắp, ánh sáng tỏa ra (Vàng/Tím/Xanh).

---

## 5. Tổng hợp (Summary)

- **Icon tài nguyên:** ~12 icons.
- **Icon Tab Bar:** 10 icons (2 states).
- **Icon HUD:** ~10 icons.
- **UI Atlas:** Buttons, Panels, Frame, Bars.
