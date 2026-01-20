# Đặc tả thiết kế môi trường & hiệu ứng (Environment & VFX specs)

Tài liệu này mô tả các tài nguyên nghệ thuật môi trường (Backgrounds) và hiệu ứng hình ảnh (Visual Effects - VFX) để tạo không khí và trải nghiệm thị giác cho game.

---

## 1. Môi trường (Environments)

Mỗi chương (Chapter) sẽ có một bộ background riêng biệt. Background cần được chia lớp (Layered) để tạo hiệu ứng Parallax (Xa gần chuyển động khác nhau).

### Kích thước chung

- **Resolution:** 1080x1920 (Portrait), nhưng cần vẽ rộng hơn bề ngang (khoảng 1500-2000px) để có thể scroll loop liên tục không bị lặp vân quá rõ.
- **Layers:** Tối thiểu 3 lớp: Far (Xa), Mid (Giữa), Near (Gần/Sàn).

### 1.1. Chapter 1: Ngõ Phố Nhỏ

- **Cảm hứng:** Các con ngõ nhỏ ở Hà Nội/Sài Gòn.
- **Layer Far (Bầu trời/Xa):** Bầu trời xanh nhạt, nóc các ngôi nhà cao tầng xa xa, dây điện chằng chịt mờ ảo.
- **Layer Mid (Nhà cửa):** Những ngôi nhà ống sát nhau, tường vàng/xanh rêu phong, ban công phơi quần áo, lồng chim, cục nóng điều hòa.
- **Layer Near (Mặt đất):** Vỉa hè lát gạch con sâu hư hỏng, gốc cây xà cừ, cột điện dán đầy quảng cáo "Khoan cắt bê tông", "Hút hầm cầu".

### 1.2. Chapter 2: Khu Chợ Cóc

- **Cảm hứng:** Chợ dân sinh ồn ào, náo nhiệt.
- **Layer Far:** Mái che bạt xanh đỏ nhấp nhô, biển hiệu cửa hàng tạp hóa.
- **Layer Mid:** Sạp rau củ, xe đẩy trái cây, phản thịt heo, người bán hàng (NPC tĩnh).
- **Layer Near:** Mặt đường nhựa loang lổ vũng nước, rác chợ (lá rau, túi nilon).

### 1.3. Chapter 3: Công Viên Ghế Đá

- **Cảm hứng:** Công viên buổi sáng sớm/chiều tà.
- **Layer Far:** Hàng cây xanh rậm rạp, hồ nước xa xa.
- **Layer Mid:** Dụng cụ tập thể dục công cộng (xoay eo, xà đơn), ghế đá có đôi nam nữ ngồi (NPC), các cụ tập dưỡng sinh.
- **Layer Near:** Đường chạy bộ lát gạch, bồn hoa, cỏ xanh.

### 1.4. Chapter 4: Bến Xe Khách

- **Cảm hứng:** Bến xe Mỹ Đình/Miền Đông xô bồ.
- **Layer Far:** Tòa nhà điều hành bến xe, rào sắt.
- **Layer Mid:** Những chiếc xe khách 45 chỗ đang đậu (Vẽ kiểu Phương Trang/Thành Bưởi parody), hành khách đeo balo đứng chờ.
- **Layer Near:** Bến bãi bê tông nứt vỡ, vệt bánh xe, xe ôm vẫy khách.

---

## 2. Hiệu ứng kỹ xảo (VFX - Visual Effects)

Sử dụng Particle System hoặc Sprite Sheet Animation. Phong cách Cartoon, màu sắc rực rỡ, cường điệu hóa.

### 2.1. VFX Chiến đấu cơ bản

- **Hit Impact (Trúng đòn):** Tia lửa trắng/vàng tóe ra hình ngôi sao hoặc tia chớp khi vũ khí va chạm.
- **Crit Hit (Chí mạng):** Nổ to hơn, màu cam/đỏ, có chữ "BÙM" hoặc icon chấn động.
- **Máu chảy (Blood - Optional):** Hạn chế máu me, thay bằng hiệu ứng "vỡ vụn" hoặc ngôi sao bay ra khi quái chết.
- **Death (Quái chết):** Quái biến mất trong làn khói trắng (kiểu Ninja) hoặc vỡ tan thành tiền vàng.

### 2.2. VFX Kỹ năng (Skill Effects)

- **Dép lào bay:** Vệt gió xoáy (trail) màu trắng phía sau chiếc dép. Khi trúng đích nổ ra vòng tròn chấn động đất.
- **Mưa gạch:** Bóng đổ dưới đất trước khi gạch rơi. Gạch vỡ vụn + bụi bay mù mịt khi chạm đất.
- **Hồi máu:** Các dấu cộng (+) màu xanh lá và hình trái tim bay từ dưới chân nhân vật lên cao, mờ dần.
- **Buff tốc độ:** Các vệt gió (wind lines) bao quanh nhân vật, hoặc luồng khí (aura) màu vàng bốc lên (kiểu Super Saiyan).
- **Điện giật (Chain Lightning):** Tia sét màu xanh dương/tím nối zíc-zắc giữa các kẻ địch.

### 2.3. VFX UI & Hệ thống

- **Level Up:** Cột ánh sáng vàng chiếu từ trên xuống, confetti (pháo giấy) bung tỏa xung quanh nhân vật.
- **Nhặt tiền:** Đồng xu vàng bay theo đường cong Parabol từ vị trí quái chết về phía thanh tiền trên UI.
- **Nâng cấp thành công:** Icon búa đập xuống + tia sáng lóe lên trên nút bấm.
- **Gacha mở rương:** Ánh sáng (God ray) chiếu tỏa ra từ trong thùng khi nắp mở.

---

## 3. Âm thanh (Audio - Tham khảo)

Tuy tài liệu này tập trung vào Visual, nhưng ghi chú thêm về không khí âm thanh để Artist nắm bắt vibe.

- Background noise (Tiếng ồn nền): Tiếng còi xe máy, tiếng rao hàng ("Ai đồng nát sắt vụn bán đê..."), tiếng chó sủa xa xa.
- Nhạc nền: Nhạc cụ dân tộc (đàn bầu, sáo) mix với beat Hip-hop/Lo-fi hiện đại.
