# Hệ thống đồng đội (Teammates)

Tài liệu này mô tả chi tiết về hệ thống nhân vật hỗ trợ, bao gồm phân loại phẩm chất, danh sách 30 nhân vật và mạng lưới duyên phận.

---

## 1. Cấu trúc hệ thống

### 1.1. Phẩm chất (Rarity) & Tỉ lệ

Hệ thống sử dụng 6 cấp độ phẩm chất tương tự trang bị để đồng bộ hóa trải nghiệm người chơi.

| Phẩm chất     | Màu sắc           | Tên gọi       | Base Stat Multiplier | Max Level | Số lượng khởi điểm |
| :------------ | :---------------- | :------------ | :------------------- | :-------- | :----------------- |
| **Common**    | Trắng (White)     | Bình dân      | 1.0x                 | 20        | 5                  |
| **Uncommon**  | Xanh lá (Green)   | Tập sự        | 1.2x                 | 40        | 6                  |
| **Rare**      | Xanh dương (Blue) | Chuyên nghiệp | 1.5x                 | 60        | 8                  |
| **Epic**      | Tím (Purple)      | Tinh anh      | 2.0x                 | 80        | 7                  |
| **Legendary** | Cam (Orange)      | Huyền thoại   | 3.0x                 | 100       | 4                  |
| **Mythic**    | Đỏ (Red)          | Thần thoại    | 5.0x                 | 120       | (Coming Soon)      |

### 1.2. Vai trò (Class)

- **Tanker (Đỡ đòn):** HP cao, Def cao, thu hút sát thương.
- **Warrior (Đấu sĩ):** Cân bằng công thủ, đánh cận chiến.
- **Ranger (Xạ thủ):** DPS tầm xa, tốc độ đánh nhanh.
- **Mage (Pháp sư):** DPS phép thuật, AOE (diện rộng), dồn dame.
- **Support (Hỗ trợ):** Hồi máu, Buff team, Debuff địch.

---

## 2. Danh sách Đồng đội (Roster)

### 2.1. Nhóm Bình Dân (Common) - 5 Nhân vật

| Tên                 | Class   | Kỹ năng chính (Active Skill)                                           |
| :------------------ | :------ | :--------------------------------------------------------------------- |
| **Bé Tí bắn bi**    | Ranger  | **Bắn Bi:** Bắn viên bi ve gây 120% sát thương chuẩn.                  |
| **Chú Tư xe thồ**   | Tanker  | **Chặn Đầu:** Lao xe đạp thồ ra chặn 1 đòn đánh cho chủ nhân.          |
| **Cô Bảy quét rác** | Support | **Quét Sạch:** Xóa bỏ 1 hiệu ứng xấu (debuff) cho đồng đội ngẫu nhiên. |
| **Cậu Vàng (Chó)**  | Warrior | **Cắn Trộm:** Gây 150% sát thương và làm chậm địch 30%.                |
| **Bác Bảo vệ**      | Tanker  | **Đèn Pin:** Chiếu đèn làm giảm chính xác của địch trong 3s.           |

### 2.2. Nhóm Tập Sự (Uncommon) - 6 Nhân vật

| Tên                | Class   | Kỹ năng chính (Active Skill)                                                |
| :----------------- | :------ | :-------------------------------------------------------------------------- |
| **Chị Tạp vụ**     | Warrior | **Lau Sàn:** Lướt tới làm ngã (Stun) kẻ địch trong 1.5s.                    |
| **Anh Grab Food**  | Ranger  | **Giao Tốc Hành:** Ném hộp cơm gây dame diện rộng (AOE).                    |
| **Thằng Tèo net**  | Mage    | **Lag Spike:** Làm địch đứng im (Freeze) trong 2s vì "rớt mạng".            |
| **Cô Hàng xóm**    | Support | **Buôn Dưa Lê:** Giảm 20% giáp của toàn bộ địch (nghe nói xấu nên suy sụp). |
| **Ông Chú câu cá** | Ranger  | **Quăng Cần:** Kéo 1 kẻ địch yếu nhất về phía mình.                         |
| **Bà Bán xôi**     | Support | **Xôi Gà:** Hồi 15% HP cho đồng đội thấp máu nhất.                          |

### 2.3. Nhóm Chuyên Nghiệp (Rare) - 8 Nhân vật

| Tên                  | Class   | Kỹ năng chính (Active Skill)                                                        |
| :------------------- | :------ | :---------------------------------------------------------------------------------- |
| **Chú Ba xe ôm**     | Tanker  | **Đón Khách:** Lao xe Dream gây choáng diện rộng 2s và Taunt địch.                  |
| **Cô Tư bán nước**   | Support | **Trà Đá:** Hồi năng lượng cho toàn team và tăng tốc đánh.                          |
| **Anh Bảy thợ điện** | Mage    | **Đấu Tắt:** Phóng sét dây chuyền (Chain Lightning) giật 3 mục tiêu.                |
| **Chị Mười bán cá**  | Warrior | **Cá Đông Lạnh:** Quất cá gây 300% sát thương, chắc chắn chí mạng.                  |
| **Ninja Lead**       | Tanker  | **Xi Nhan Trái:** Tăng 50% né tránh trong 5s. Phản sát thương khi né.               |
| **Thầy Bói mù**      | Mage    | **Phán Xét:** Ngẫu nhiên gây sát thương cực lớn hoặc hồi máu cho địch (80/20).      |
| **Anh Shipper**      | Ranger  | **Mưa Đơn Hàng:** Ném hàng loạt gói hàng gây sát thương liên tục lên vùng chỉ định. |
| **Chị Đại Gym**      | Warrior | **Squat Thần Thánh:** Dậm đất gây slow và giảm tốc đánh của địch xung quanh.        |

### 2.4. Nhóm Tinh Anh (Epic) - 7 Nhân vật

| Tên                     | Class   | Kỹ năng chính (Active Skill)                                                    |
| :---------------------- | :------ | :------------------------------------------------------------------------------ |
| **Tổ Trưởng Dân Phố**   | Support | **Loa Phường:** Hét vào loa tăng 30% ATK cho toàn đội trong 10s.                |
| **Thợ Cắt Tóc**         | Warrior | **Múa Kéo:** Tấn công liên hoàn 5 nhát, gây chảy máu (Bleed).                   |
| **Bà Chủ Trọ**          | Tanker  | **Đòi Tiền:** Hút 10% HP của địch chuyển thành khiên cho bản thân.              |
| **Youtuber Ẩm Thực**    | Tanker  | **Mukbang:** Ăn 1 cái đùi gà to, hồi 50% HP và tăng giáp.                       |
| **Rapper Xóm**          | Mage    | **Diss Track:** Gây sát thương âm thanh và câm lặng (Silence) địch 3s.          |
| **Hot Girl Livestream** | Support | **Thả Tim:** Buff bất tử 2s cho đồng đội sắp chết.                              |
| **Thầy Giáo Thể Dục**   | Warrior | **Hít Đất:** Tăng vĩnh viễn ATK mỗi khi hạ gục một kẻ địch (Stack max 10 tầng). |

### 2.5. Nhóm Huyền Thoại (Legendary) - 4 Nhân vật

| Tên                | Class   | Kỹ năng chính (Active Skill)                                                            |
| :----------------- | :------ | :-------------------------------------------------------------------------------------- |
| **Vua Cờ Bạc**     | Ranger  | **Thần Bài:** Ném 3 lá bài (Xanh, Đỏ, Vàng). Xanh hồi mana, Đỏ gây nổ, Vàng làm choáng. |
| **Đại Ca Khu Phố** | Warrior | **Triệu Hồi Đàn Em:** Gọi ra 2 tên đệ tử (quái thường) chiến đấu cùng.                  |
| **Bà Trùm Đề**     | Mage    | **Sổ Sinh Tử:** Chọn 1 kẻ địch, sau 5s gây sát thương bằng 50% máu đã mất của nó.       |
| **Tiến Sĩ Giấy**   | Support | **Hack Game:** Reset toàn bộ thời gian hồi chiêu của cả đội (Cooldown: 60s).            |

---

## 3. Hệ thống Duyên phận (Bond System)

Kích hoạt chỉ số ẩn khi sở hữu (hoặc ra trận) các nhân vật cùng bộ.

### 3.1. Các bộ duyên chính

**1. Bộ "Giao Thông Vận Tải"**

- **Thành viên:** Chú Ba xe ôm (Rare), Ninja Lead (Rare), Chú Tư xe thồ (Common), Anh Grab Food (Uncommon).
- **Hiệu ứng:**
  - 2 tướng: Tăng 10% Tốc chạy.
  - 3 tướng: Tăng 15% Né tránh.
  - 4 tướng: Khi né thành công, hồi 5% HP.

**2. Bộ "Chợ Tin Đồn"**

- **Thành viên:** Cô Hàng xóm (Uncommon), Bà Bán xôi (Uncommon), Cô Tư bán nước (Rare), Chị Mười bán cá (Rare).
- **Hiệu ứng:**
  - 2 tướng: Tăng 20% Kháng hiệu ứng.
  - 4 tướng: Kẻ địch xung quanh bị giảm 15% phòng thủ (Aura).

**3. Bộ "Ban Quản Lý Khu Phố"**

- **Thành viên:** Bác Bảo vệ (Common), Tổ Trưởng Dân Phố (Epic), Bà Chủ Trọ (Epic).
- **Hiệu ứng:**
  - 2 tướng: Tăng 20% HP toàn đội.
  - 3 tướng: Tăng 20% Gold nhận được từ quái.

**4. Bộ "Gen Z Năng Động"**

- **Thành viên:** Thằng Tèo net (Uncommon), Hot Girl Livestream (Epic), Rapper Xóm (Epic), Youtuber Ẩm Thực (Epic).
- **Hiệu ứng:**
  - 2 tướng: Tăng 10% Crit Rate.
  - 4 tướng: Khi Crit, tăng 20% Tốc đánh trong 3s.

**5. Bộ "Thế Giới Ngầm"**

- **Thành viên:** Đại Ca Khu Phố (Legend), Bà Trùm Đề (Legend), Vua Cờ Bạc (Legend).
- **Hiệu ứng:**
  - 2 tướng: Tăng 30% ATK.
  - 3 tướng: Kỹ năng gây thêm 50% sát thương chuẩn.

### 3.2. Cơ chế kích hoạt

- Chỉ cần **SỞ HỮU** nhân vật trong kho để kích hoạt mốc 1.
- Cần **NÂNG CẤP SAO** (tổng số sao của bộ) để kích hoạt các mốc nâng cao (nếu có update sau này).
- Buff được cộng dồn (Additive) vào chỉ số tổng của nhân vật chính và đồng đội.

---

## 4. Cơ chế AI & Hành vi

Để tối ưu hóa chiến thuật, mỗi Class có AI riêng:

- **Tanker:** Luôn đứng hàng đầu, ưu tiên tấn công kẻ địch đang target nhân vật chính hoặc Support.
- **Warrior:** Đứng hàng đầu/giữa, tấn công kẻ địch gần nhất.
- **Ranger/Mage:** Đứng hàng sau cùng, giữ khoảng cách tối đa, ưu tiên target Boss hoặc kẻ địch ít máu nhất.
- **Support:** Đứng cạnh Ranger/Mage. Khi dùng skill hồi máu, tự động target đồng minh thấp máu nhất.

## 5. Chiến thuật đội hình (Meta Teambuilding)

Gợi ý các đội hình mẫu cho người chơi:

1.  **Đội hình "Trâu Bò" (Survive):** 2 Tanker + 2 Healer (Ví dụ: Chú Ba, Ninja Lead, Cô Tư, Bà Bán Xôi). Dùng để leo tháp hoặc đánh Boss sát thương cao.
2.  **Đội hình "Dồn Dame" (Burst):** 1 Tanker + 3 Mage/Ranger (Ví dụ: Đại Ca, Rapper, Thầy Bói, Anh Bảy). Dùng để farm quái nhanh.
3.  **Đội hình "Khống chế" (Control):** Các tướng có Stun/Freeze (Thằng Tèo net, Chú Ba, Vua Cờ Bạc). Dùng trong PvP (nếu có) hoặc Boss khó chịu.
