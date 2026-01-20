# Thiết kế trang bị

Tài liệu này mô tả yêu cầu hình ảnh cho hệ thống trang bị, bao gồm icon trong túi đồ và hình ảnh hiển thị trên nhân vật (nếu có).

---

## 1. Quy cách chung (General specs)

### 1.1. Icon trong túi đồ (Inventory Icon)

- **Kích thước:** 128x128 px (cho hiển thị UI thông thường) và 256x256 px (cho hiển thị Popup chi tiết).
- **Background:** Trong suốt (UI sẽ tự fill màu nền theo phẩm chất).
- **Góc nhìn:** Nhìn nghiêng 45 độ hoặc nhìn thẳng, tùy loại vật phẩm sao cho dễ nhận diện hình dáng nhất.
- **Style:** Cartoon, viền đậm, màu sắc tươi sáng.

### 1.2. Khung viền phẩm chất (Rarity Borders)

Cần thiết kế bộ khung (frame) dùng chung cho tất cả icon.

| Phẩm chất              | Mã màu (Hex) | Hiệu ứng viền                                     |
| :--------------------- | :----------- | :------------------------------------------------ |
| **Common (Trắng)**     | #BDBDBD      | Viền xám bạc đơn giản                             |
| **Uncommon (Xanh lá)** | #4CAF50      | Viền xanh lá, có họa tiết lá cây nhẹ              |
| **Rare (Xanh dương)**  | #2196F3      | Viền xanh dương, họa tiết kim loại                |
| **Epic (Tím)**         | #9C27B0      | Viền tím, có hào quang nhẹ, góc cạnh sắc bén      |
| **Legendary (Cam)**    | #FF9800      | Viền vàng cam, hiệu ứng cháy/phát sáng, đính ngọc |
| **Mythic (Đỏ)**        | #F44336      | Viền đỏ rực, hiệu ứng điện/ma thuật mạnh          |

---

## 2. Chi tiết theo loại trang bị (Slot types)

Mỗi loại trang bị cần có các tier hình ảnh khác nhau thể hiện sự tiến hóa sức mạnh.

### 2.1. Vũ khí (Weapon)

_Đại diện cho sức mạnh tấn công._

| Tier        | Tên gợi ý       | Mô tả hình ảnh (Visual description)                                            |
| :---------- | :-------------- | :----------------------------------------------------------------------------- |
| **Tier 1**  | Cây gậy gỗ      | Một cành cây khô, hoặc thanh gỗ vuông đơn giản, có dằm.                        |
| **Tier 2**  | Cục gạch        | Viên gạch ống màu đỏ cam, bị mẻ một góc.                                       |
| **Tier 3**  | Dép lào         | Chiếc dép xốp cao su màu xanh/vàng quen thuộc.                                 |
| **Tier 4**  | Cờ lê rỉ sét    | Cây cờ lê kim loại cũ kỹ, có vết rỉ sét màu nâu.                               |
| **Tier 5**  | Gậy bóng chày   | Gậy gỗ bóng chày, có đóng vài cái đinh ở đầu.                                  |
| **Tier 6**  | Tuýp sắt        | Ống tuýp nước bằng kim loại sáng bóng, dài.                                    |
| **Tier 7**  | Phóng lợn (Toy) | Một con dao bầu gắn trên ống tuýp dài (vẽ kiểu đồ chơi 7 màu cho bớt bạo lực). |
| **Tier 8**  | Kiếm LED        | Kiếm nhựa đồ chơi nhưng phát sáng đèn LED neon (Cyberpunk style).              |
| **Tier 9**  | Điếu cày thần   | Điếu cày bọc vàng, chạm trổ rồng phượng, tỏa khói trắng.                       |
| **Tier 10** | Găng tay vô cực | Găng tay sắt có gắn đủ loại đá quý màu mè.                                     |

### 2.2. Áo (Armor)

_Đại diện cho sức chịu đựng._

| Tier        | Tên gợi ý          | Mô tả hình ảnh                                             |
| :---------- | :----------------- | :--------------------------------------------------------- |
| **Tier 1**  | Áo ba lỗ cháo lòng | Áo thun ba lỗ màu trắng ngà, có vết ố, rách lỗ nhỏ.        |
| **Tier 2**  | Áo mưa nilon       | Áo mưa giấy mỏng manh nhiều màu (xanh/đỏ/tím).             |
| **Tier 3**  | Tấm bìa carton     | Hai tấm bìa carton trước sau nối bằng dây thừng.           |
| **Tier 4**  | Áo phao            | Áo phao cứu sinh màu cam nổi bật.                          |
| **Tier 5**  | Áo jean            | Áo khoác bò bụi bặm, có huy hiệu/patch.                    |
| **Tier 6**  | Giáp nồi niêu      | Lấy mấy cái nắp vung nồi nhôm buộc lại thành giáp ngực.    |
| **Tier 7**  | Áo giáp cơ động    | Áo giáp của cảnh sát đặc nhiệm (swat vest).                |
| **Tier 8**  | Bộ đồ phi hành gia | Bộ đồ màu trắng kín mít, cồng kềnh.                        |
| **Tier 9**  | Giáp Iron-Fake     | Giáp kim loại đỏ vàng nhái Iron Man nhưng nhìn hơi "nhựa". |
| **Tier 10** | Áo choàng hoàng đế | Áo choàng lông thú, nạm vàng lấp lánh.                     |

### 2.3. Giày (Boots)

_Đại diện cho tốc độ._

| Tier        | Tên gợi ý            | Mô tả hình ảnh                                           |
| :---------- | :------------------- | :------------------------------------------------------- |
| **Tier 1**  | Chân đất             | Không có icon giày, chỉ vẽ bàn chân bẩn.                 |
| **Tier 2**  | Dép tổ ong           | Huyền thoại dép tổ ong màu trắng ngà hoặc vàng.          |
| **Tier 3**  | Dép xỏ ngón          | Dép lào xỏ ngón đi biển.                                 |
| **Tier 4**  | Giày vải thượng đình | Giày vải bata trắng sọc xanh quốc dân.                   |
| **Tier 5**  | Ủng cao su           | Ủng đi mưa màu đen hoặc xanh.                            |
| **Tier 6**  | Giày da tây          | Giày da đen bóng lộn nhưng hơi cũ.                       |
| **Tier 7**  | Sneaker Fake         | Giày thể thao nhái thương hiệu nổi tiếng (Abidas/Nikee). |
| **Tier 8**  | Giày Patin           | Giày trượt có bánh xe.                                   |
| **Tier 9**  | Giày tên lửa         | Giày có gắn ống phản lực nhỏ phía sau.                   |
| **Tier 10** | Giày Hermes (Cánh)   | Giày mạ vàng có đôi cánh nhỏ 2 bên.                      |

### 2.4. Dây chuyền (Accessory)

_Đại diện cho sự may mắn/sang chảnh._

| Tier        | Tên gợi ý           | Mô tả hình ảnh                         |
| :---------- | :------------------ | :------------------------------------- |
| **Tier 1**  | Dây thừng           | Một sợi dây thừng buộc cổ.             |
| **Tier 2**  | Khăn quàng đỏ       | Khăn quàng học sinh tiểu học.          |
| **Tier 3**  | Huy chương bé ngoan | Huy chương nhựa mẫu giáo.              |
| **Tier 4**  | Còi trọng tài       | Cái còi nhựa đeo cổ.                   |
| **Tier 5**  | Dây xích chó        | Dây xích inox mắt to (style punk).     |
| **Tier 6**  | Nanh heo rừng       | Dây đeo mặt nanh (giả).                |
| **Tier 7**  | Chuỗi hạt gỗ        | Chuỗi hạt to đùng như của Thiếu Lâm.   |
| **Tier 8**  | Xích vàng (Fake)    | Dây xích mạ vàng to như xích xích lô.  |
| **Tier 9**  | Mặt phật ngọc       | Dây chuyền ngọc bích tỏa sáng.         |
| **Tier 10** | Trái tim rồng       | Mặt dây chuyền đá quý đỏ rực hình tim. |

---

## 3. Quy tắc Visual Progression

Khi nâng cấp trang bị (Tier up), hình ảnh cần thay đổi để người chơi cảm thấy mạnh lên:

1.  **Chất liệu:** Gỗ/Giấy -> Nhựa/Cao su -> Kim loại rỉ -> Kim loại sáng -> Vàng/Ngọc/Ánh sáng.
2.  **Độ phức tạp:** Đơn giản ít chi tiết -> Nhiều phụ kiện, gai góc, hầm hố hơn.
3.  **Hiệu ứng:**
    - Tier thấp: Tĩnh.
    - Tier trung: Có độ bóng (shine).
    - Tier cao: Có hào quang (glow) hoặc particle bay quanh icon.

## 4. Tổng hợp số lượng Asset (Giai đoạn 1)

- **Vũ khí:** 10 icons.
- **Áo:** 10 icons.
- **Giày:** 10 icons.
- **Dây chuyền:** 10 icons.
- **Khung viền:** 6 icons (Common -> Mythic).
- **Tổng cộng:** ~46 icons.
