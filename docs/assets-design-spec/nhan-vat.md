# Thiết kế nhân vật (Character Design & Audio)

Tài liệu quy định chi tiết về Visual Art (Ngoại hình, Animation) và Audio (Voice, SFX) cho toàn bộ nhân vật trong game.

---

## 1. Quy chuẩn chung (General Specs)

### 1.1. Art Style

- **Phong cách:** Cartoon 2D, tỷ lệ cơ thể 1:2.5 (đầu to thân nhỏ, cute nhưng bựa).
- **Line:** Nét viền đậm, màu nâu đen (#2E2E2E).
- **Màu sắc:** Tươi sáng (High saturation), đổ bóng Cel-shading đơn giản.
- **Góc nhìn:** 3/4 Side-view.

### 1.2. Kỹ thuật (Technical)

- **Kích thước Sprite:**
  - Ingame: ~150px chiều cao.
  - Source: 512x512px.
- **Animation FPS:** 30fps (xuất ra sprite sheet có thể giảm xuống 12-15fps cho style giật giật nếu muốn).
- **Các trạng thái:** Idle, Move, Attack, Skill, Hit, Die, Win.

---

## 2. Nhân vật chính (Player)

- **Tên:** Thanh niên nghiêm túc (Mặc định).
- **Ngoại hình:** Nam thanh niên 20 tuổi, mặc quần đùi hoa, áo ba lỗ trắng cháo lòng, đi dép tổ ong.
- **Vũ khí:** Thay đổi theo trang bị (Gậy, Gạch, Dép...).
- **Tính cách:** Ngáo ngơ nhưng hay tỏ ra nguy hiểm.
- **Audio:**
  - _Attack:_ "Hây a!", "Đỡ này".
  - _Hit:_ "Á đù!", "Đau!".
  - _Die:_ "Thôi xong...", "Làm lại cuộc đời".

---

## 3. Thiết kế Đồng đội - Nhóm Huyền Thoại (Legendary)

Nhóm nhân vật "trùm cuối", thiết kế cầu kỳ, nhiều hiệu ứng.

### 3.1. Đại Ca Khu Phố (Warrior)

- **Visual:**
  - Đàn ông 40 tuổi, to béo, bụng phệ, cởi trần khoe hình xăm "Nhẫn" trước ngực và rồng phượng sau lưng.
  - Đeo dây chuyền vàng to như xích xe tăng, kính râm đen.
  - Vũ khí: Cầm một cây phóng lợn (mã tấu) dài.
- **Animation:** Dáng đi khệnh khạng, ưỡn ngực. Skill gọi đệ tử từ 2 bên màn hình chạy ra.
- **Audio:**
  - _Summon:_ "Anh em đâu!", "Xử nó cho tao!".
  - _Skill:_ Tiếng huýt sáo chói tai.

### 3.2. Vua Cờ Bạc (Ranger)

- **Visual:**
  - Nam, mặc Vest trắng nhưng nhàu nát, tóc vuốt keo bóng lộn.
  - Tay luôn cầm bộ bài xòe ra.
  - Mắt thâm quầng như gấu trúc (thức đêm đánh bài).
- **Animation:** Tấn công bằng cách phi lá bài (giống Gambit). Skill tung cả bộ bài lên trời rơi xuống như mưa.
- **Audio:**
  - _Attack:_ Tiếng bài bay "Vút vút".
  - _Skill:_ "Tất tay nhé!", "Khô máu luôn!".

### 3.3. Bà Trùm Đề (Mage)

- **Visual:**
  - Phụ nữ trung niên sang trọng (quý bà), đeo đầy vàng ngọc.
  - Tay cầm quyển "Sổ ghi đề" dày cộp và cái bút bi thiên long.
  - Ngồi trên ghế sofa nhung đỏ (kể cả khi di chuyển - sofa biết bay hoặc trượt).
- **Animation:** Viết vào sổ -> Chữ bay ra tấn công địch.
- **Audio:**
  - _Skill:_ "Hôm nay về con gì?", "Ghi nợ nhé!".
  - _SFX:_ Tiếng sấm sét khi chốt số.

### 3.4. Tiến Sĩ Giấy (Support)

- **Visual:**
  - Ông già gầy gò, mặc áo cử nhân thùng thình, đội mũ tốt nghiệp.
  - Kính cận dày cộp, tay ôm chồng sách cao quá đầu.
- **Animation:** Vấp ngã làm rơi sách -> Sách tỏa sáng buff cho đồng đội.
- **Audio:**
  - _Skill:_ "Học, học nữa, học mãi!", "Kiến thức là sức mạnh".

---

## 4. Thiết kế Đồng đội - Nhóm Tinh Anh (Epic)

### 4.1. Tổ Trưởng Dân Phố (Support)

- **Visual:** Ông già nghiêm túc, đeo băng đỏ "Tổ Trưởng" ở tay trái, tay phải cầm loa phường mini. Mặc áo sơ mi trắng đóng thùng.
- **Audio:** "Đề nghị bà con giữ trật tự!", "Alo alo 1 2 3 4".

### 4.2. Hot Girl Livestream (Support)

- **Visual:** Nữ trẻ đẹp, trang điểm đậm, mặc váy ngắn, tai đeo headphone mèo có đèn RGB. Trước mặt luôn có cái điện thoại đang kẹp trên ring light di động.
- **Audio:** "Mọi người thả tim cho em đi!", "Cảm ơn anh giai đã donate nha!".

### 4.3. Rapper Xóm (Mage)

- **Visual:** Mặc áo Hoodie rộng, quần tụt, mũ Snapback đội ngược, đeo dây chuyền Dollar $.
- **Audio:** Bắn rap xàm xí "Yo yo check it out", "Khu phố này là của tao".

### 4.4. Youtuber Ẩm Thực (Tanker)

- **Visual:** Béo tròn, mặc áo thun có hình đồ ăn. Tay cầm đùi gà rán to đùng (vừa là vũ khí vừa là đồ ăn).
- **Audio:** Tiếng nhai nhồm nhoàm "Rộp rộp", "Mời các bạn ăn cùng mình nhé".

---

## 5. Thiết kế Đồng đội - Nhóm Chuyên Nghiệp (Rare)

(Các nhân vật đã có concept từ trước, bổ sung Audio)

| Nhân vật             | Đặc điểm Visual chính                      | Audio Concept (Voice lines)                        |
| :------------------- | :----------------------------------------- | :------------------------------------------------- |
| **Chú Ba xe ôm**     | Mũ cối, xe Dream, áo sờn vai               | "Đi đâu đấy em?", "Có tiền lẻ không?"              |
| **Cô Tư bán nước**   | Đồ bộ hoa, ghế nhựa, quạt nan              | "Uống gì con ơi?", "Trà đá miễn phí đây"           |
| **Anh Bảy thợ điện** | Áo cam, đai đồ nghề, kìm                   | "Cẩn thận điện giật!", "Tránh ra cho anh làm việc" |
| **Chị Mười bán cá**  | Tạp dề cao su, ủng, dao phay               | "Cá tươi đây!", "Chém cho bây giờ!"                |
| **Ninja Lead**       | Kín mít, áo chống nắng, xe Lead            | "Xi nhan trái rẽ phải nhé", "Đường này của chị"    |
| **Thầy Bói mù**      | Kính đen tròn, gậy dò đường, áo dài        | "Gia chủ năm nay xui lắm", "Quẻ này đẹp"           |
| **Anh Shipper**      | Áo cam/xanh đồng phục, thùng hàng sau lưng | "Alo xuống nhận hàng em ơi", "Đang kẹt xe quá"     |
| **Chị Đại Gym**      | Đồ tập gym bó sát, tạ tay                  | "No pain no gain!", "Lên cơ nào!"                  |

---

## 6. Thiết kế Đồng đội - Nhóm Phổ thông (Common/Uncommon)

Thiết kế đơn giản, ít chi tiết, dùng làm nền cho khu phố đông đúc.

| Tên                 | Class   | Visual Concept                                          | Audio/SFX                          |
| :------------------ | :------ | :------------------------------------------------------ | :--------------------------------- |
| **Bé Tí bắn bi**    | Ranger  | Cậu bé đeo khăn quàng đỏ, quần đùi xanh, tay cầm bi ve. | Tiếng bi va vào nhau "Cạch cạch"   |
| **Chú Tư xe thồ**   | Tanker  | Xe đạp thồ chất đầy bao tải lúa/ngô.                    | Tiếng chuông xe đạp "Kính coong"   |
| **Cô Bảy quét rác** | Support | Áo công nhân vệ sinh phản quang, cầm chổi tre dài.      | Tiếng chổi "Ssoạt soạt"            |
| **Cậu Vàng**        | Warrior | Chó cỏ vàng, đeo xích cổ, đuôi vẫy tít mù.              | "Gâu gâu!", "Ẳng ẳng"              |
| **Bác Bảo vệ**      | Tanker  | Đồng phục bảo vệ xanh dương, dùi cui cao su.            | "Đứng lại!", Tiếng còi "Tuýt tuýt" |
| **Chị Tạp vụ**      | Warrior | Khăn trùm đầu, xô nước và cây lau nhà.                  | "Dơ quá đi mất"                    |
| **Anh Grab Food**   | Ranger  | Áo xanh lá cây, mũ bảo hiểm 3/4.                        | "Đơn hàng tới rồi"                 |
| **Thằng Tèo net**   | Mage    | Mắt cận lòi, đầu bù tóc rối, tay cầm bàn phím hỏng.     | "Lag quá!", "Đập bàn phím"         |
| **Cô Hàng xóm**     | Support | Đứng lấp ló sau tường, tay chỉ trỏ.                     | Tiếng xì xầm bàn tán               |
| **Ông Chú câu cá**  | Ranger  | Mũ tai bèo, bộ đồ rằn ri, cần câu tre.                  | "Suỵt! Cá đang cắn câu"            |
| **Bà Bán xôi**      | Support | Đội thúng xôi trên đầu, lá chuối gói xôi.               | Tiếng rao "Xôi lạc bánh khúc đây"  |

---

## 7. Yêu cầu định dạng File Asset

### 7.1. Image

- **Naming:** `Char_[Rarity]_[Name]_[State].png`
  - Ví dụ: `Char_Legend_VuaCoBac_Attack.png`
- **Folder Structure:** Chia folder theo Rarity `Assets/Characters/Legendary/...`

### 7.2. Audio

- **Format:** .WAV (gốc) và .OGG (ingame).
- **Naming:** `VO_[Name]_[Action].ogg`
  - Ví dụ: `VO_NinjaLead_Skill.ogg`
