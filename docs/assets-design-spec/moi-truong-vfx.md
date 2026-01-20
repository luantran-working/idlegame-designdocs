# Thiết kế môi trường

Tài liệu này mô tả các tài nguyên nghệ thuật môi trường (Backgrounds) và hiệu ứng hình ảnh (Visual Effects - VFX) để tạo không khí và trải nghiệm thị giác cho game.

---

## 1. Môi trường (Environments)

Mỗi chương (Chapter) sẽ có một bộ background riêng biệt, được chia thành tối thiểu 3 lớp (Layer) để tạo hiệu ứng Parallax.

### Quy cách chung
- **Resolution:** 1080x1920 (Portrait), chiều ngang mở rộng 1500-2000px để scroll loop.
- **Layers:** Far (Xa), Mid (Giữa), Near (Gần/Sàn).

### Danh sách môi trường chi tiết

| Chapter | Chủ đề | Layer Far (Xa) | Layer Mid (Giữa) | Layer Near (Gần) |
| :--- | :--- | :--- | :--- | :--- |
| **1. Ngõ Phố Nhỏ** | Hà Nội/Sài Gòn bình dân | Bầu trời xanh nhạt, nóc nhà cao tầng xa, dây điện chằng chịt mờ ảo | Nhà ống sát nhau, tường vàng/rêu, ban công phơi đồ, cục nóng điều hòa | Vỉa hè gạch con sâu hư, gốc cây xà cừ, cột điện dán quảng cáo |
| **2. Khu Chợ Cóc** | Chợ dân sinh ồn ào | Mái che bạt xanh đỏ nhấp nhô, biển hiệu tạp hóa | Sạp rau củ, xe đẩy trái cây, phản thịt heo, người bán hàng (NPC) | Mặt đường nhựa loang lổ, vũng nước, rác chợ (lá rau, túi nilon) |
| **3. Công Viên** | Sáng sớm/Chiều tà | Hàng cây xanh rậm rạp, hồ nước xa xa | Dụng cụ tập thể dục, ghế đá có đôi nam nữ, các cụ tập dưỡng sinh | Đường chạy bộ lát gạch, bồn hoa, thảm cỏ xanh |
| **4. Bến Xe** | Bến xe xô bồ | Tòa nhà điều hành bến xe, hàng rào sắt | Xe khách 45 chỗ đang đậu (parody Phương Trang), hành khách chờ đợi | Bến bãi bê tông nứt vỡ, vệt bánh xe, xe ôm vẫy khách |

---

## 2. Hiệu ứng kỹ xảo (VFX - Visual Effects)

Phong cách: Cartoon, màu sắc rực rỡ, cường điệu hóa.

### 2.1. VFX Chiến đấu (Combat)

| Tên hiệu ứng | Mô tả Visual | Ghi chú |
| :--- | :--- | :--- |
| **Hit Impact** | Tia lửa trắng/vàng tóe ra hình ngôi sao/tia chớp | Khi vũ khí trúng mục tiêu |
| **Crit Hit** | Nổ to màu cam/đỏ, kèm chữ "BÙM" hoặc icon chấn động | Khi ra đòn chí mạng |
| **Máu (Blood)** | Hiệu ứng "vỡ vụn" hoặc ngôi sao nhỏ bay ra | Hạn chế máu me bạo lực |
| **Death** | Quái biến mất trong làn khói trắng hoặc vỡ thành tiền vàng | Khi quái bị tiêu diệt |

### 2.2. VFX Kỹ năng (Skills)

| Kỹ năng | Mô tả Visual |
| :--- | :--- |
| **Dép lào bay** | Vệt gió xoáy (trail) trắng sau chiếc dép -> Nổ vòng tròn chấn động |
| **Mưa gạch** | Bóng đổ dưới đất -> Gạch rơi vỡ vụn + bụi bay mù mịt |
| **Hồi máu** | Dấu cộng (+) xanh lá và tim bay từ dưới chân lên, mờ dần |
| **Buff tốc độ** | Vệt gió (wind lines) bao quanh hoặc aura vàng bốc lên (Super Saiyan) |
| **Điện giật** | Tia sét zíc-zắc xanh dương/tím nối giữa các kẻ địch |

### 2.3. VFX UI & Hệ thống

| Sự kiện | Mô tả Visual |
| :--- | :--- |
| **Level Up** | Cột sáng vàng chiếu xuống + Confetti (pháo giấy) bung tỏa |
| **Nhặt tiền** | Đồng xu vàng bay đường Parabol từ quái về thanh UI |
| **Nâng cấp** | Icon búa đập xuống + Tia sáng lóe lên tại nút bấm |
| **Gacha** | Ánh sáng (God ray) chiếu tỏa ra từ khe thùng khi mở nắp |

---

## 3. Âm thanh (Audio Reference)

| Loại âm thanh | Mô tả / Vibe |
| :--- | :--- |
| **Background Noise** | Tiếng còi xe máy, tiếng rao hàng, tiếng chó sủa xa xa (tạo không khí đời thường) |
| **Music / BGM** | Nhạc cụ dân tộc (đàn bầu, sáo) mix với beat Hip-hop/Lo-fi hiện đại |
