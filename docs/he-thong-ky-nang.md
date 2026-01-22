# Hệ thống kỹ năng

Tài liệu này mô tả chi tiết về hệ thống kỹ năng trong game, được chia thành hai phân loại chính: Kỹ năng nhân vật chính và Kỹ năng đồng đội.

---

## 1. Phân loại kỹ năng

Hệ thống kỹ năng chia làm 2 loại riêng biệt:

1.  **Kỹ năng nhân vật chính (Player Skills):** Bộ 20 kỹ năng có thể thu thập, nâng cấp và lựa chọn để trang bị vào 6 ô kỹ năng (Skill slots).
2.  **Kỹ năng đồng đội (Teammate Skills):** Mỗi đồng đội sở hữu bộ kỹ năng cố định (1 Chủ động + 1 Bị động) không thể thay đổi, tự động kích hoạt theo AI.

---

## 2. Kỹ năng nhân vật chính (Player Skills)

Người chơi có thể thu thập tối đa 20 kỹ năng nhưng chỉ được mang **6 kỹ năng** vào trận chiến. Việc lựa chọn kỹ năng (Deck building) là yếu tố chiến thuật cốt lõi.

### 2.1. Cơ chế

- **Slots:** Mở khóa theo cấp độ (Lv 1, 5, 10, 20, 30, 40).
- **Cooldown:** Mỗi kỹ năng có thời gian hồi chiêu riêng.
- **Auto-cast:** Tự động sử dụng từ trái sang phải khi hồi chiêu xong (trong chế độ Auto).

### 2.2. Danh sách 20 kỹ năng

Được chia thành 3 nhóm để dễ lựa chọn: Tấn công, Khống chế, Hỗ trợ.

#### A. Nhóm Tấn công (Damage Dealer) - 10 Skills

| #   | Tên kỹ năng             | Cooldown | Mô tả logic (Level 1)                                                | Scaling  |
| :-- | :---------------------- | :------- | :------------------------------------------------------------------- | :------- |
| 1   | **Ném gạch**            | 2s       | Ném viên gạch vào mục tiêu đơn lẻ, gây 150% ATK.                     | +10% Dmg |
| 2   | **Quạt chả**            | 8s       | Quạt ra 3 luồng gió gây 120% ATK diện rộng hình nón.                 | +8% Dmg  |
| 3   | **Dép lào thần chưởng** | 12s      | Ném dép boomerang gây 200% ATK, quay lại gây thêm 100% nếu trúng.    | +15% Dmg |
| 4   | **Chém gió**            | 15s      | Tạo lốc xoáy gây 50% ATK/0.5s trong 3s tại vùng chỉ định.            | +5% Dmg  |
| 5   | **Phun mưa**            | 20s      | Phun nước gây 250% ATK diện rộng.                                    | +20% Dmg |
| 6   | **Mưa thiên thạch**     | 40s      | Triệu hồi 5 cục đá rơi xuống ngẫu nhiên, mỗi cục gây 300% ATK.       | +30% Dmg |
| 7   | **Đấm trâu**            | 5s       | Đấm mạnh 1 mục tiêu gây 250% ATK và đẩy lùi.                         | +15% Dmg |
| 8   | **Xả súng nước**        | 10s      | Bắn liên thanh 5 phát, mỗi phát 60% ATK.                             | +5% Dmg  |
| 9   | **Bom hẹn giờ**         | 15s      | Gắn bom lên đầu địch, sau 3s nổ gây 400% ATK lan ra xung quanh.      | +25% Dmg |
| 10  | **Tia laser**           | 25s      | Bắn tia laser xuyên thấu mọi kẻ địch trên đường thẳng, gây 350% ATK. | +20% Dmg |

#### B. Nhóm Khống chế & Suy yếu (CC & Debuff) - 5 Skills

| #   | Tên kỹ năng        | Cooldown | Mô tả logic (Level 1)                                                   | Scaling    |
| :-- | :----------------- | :------- | :---------------------------------------------------------------------- | :--------- |
| 11  | **Tiếng thét**     | 18s      | Giảm 20% ATK của toàn bộ địch trong 5s.                                 | +1% Effect |
| 12  | **Đặt bẫy chuột**  | 10s      | Đặt bẫy, địch dẫm phải bị Trói chân (Root) 2s và chịu 100% ATK.         | +10% Dmg   |
| 13  | **Mắt lé**         | 25s      | Làm kẻ địch Choáng (Stun) trong 1.5s (đơn mục tiêu).                    | -0.1s CD   |
| 14  | **Ném mắm tôm**    | 20s      | Ném lọ mắm tôm gây hiệu ứng Độc (Poison), mất 50% ATK/s trong 5s.       | +5% Dmg    |
| 15  | **Keo dính chuột** | 15s      | Tạo vùng keo dính làm Chậm (Slow) 50% tốc độ di chuyển của địch đi qua. | +2% Slow   |

#### C. Nhóm Hỗ trợ & Sinh tồn (Buff & Survival) - 5 Skills

| #   | Tên kỹ năng            | Cooldown | Mô tả logic (Level 1)                                                               | Scaling     |
| :-- | :--------------------- | :------- | :---------------------------------------------------------------------------------- | :---------- |
| 16  | **Uống nước tăng lực** | 30s      | Tăng 30% Tốc đánh và 20% Tốc chạy trong 8s.                                         | +1% Effect  |
| 17  | **Băng bó**            | 45s      | Hồi 20% HP tối đa trong 4s.                                                         | +2% Heal    |
| 18  | **Gồng mình**          | 40s      | Tạo khiên chặn sát thương bằng 300% ATK trong 5s.                                   | +20% Shield |
| 19  | **Nổi giận**           | 60s      | Tăng 50% ATK, giảm 30% Giáp trong 10s (All-in).                                     | +2% ATK     |
| 20  | **Trốn tìm**           | 35s      | Tàng hình trong 3s (địch không thể target), đòn đánh đầu tiên sau đó x2 sát thương. | +0.2s Time  |

---

## 3. Kỹ năng đồng đội (Teammate Skills)

Mỗi đồng đội trong 30 nhân vật sở hữu bộ kỹ năng cố định.

### 3.1. Cấu trúc

- **Kỹ năng Chủ động (Active):**
  - Tự động kích hoạt khi thanh năng lượng (Energy) của đồng đội đầy.
  - Có hiệu ứng mạnh (Sát thương lớn, hồi máu team, hoặc CC diện rộng).
- **Kỹ năng Bị động (Passive):**
  - Luôn kích hoạt hoặc kích hoạt theo điều kiện.
  - Thường là hào quang (Aura) tăng stat cho team hoặc nội tại bản thân.

### 3.2. Đặc trưng kỹ năng theo vai trò (Class)

Mọi đồng đội đều có 1 Active Skill (dùng Energy) và 1 Passive Skill (nội tại).

| Vai trò | Đặc trưng Active Skill | Đặc trưng Passive Skill |
| :------ | :--------------------- | :---------------------- |

- **Kỹ năng Chủ động (Active):**
  - Tự động kích hoạt khi thanh năng lượng (Energy) của đồng đội đầy.
  - Có hiệu ứng mạnh (Sát thương lớn, hồi máu team, hoặc CC diện rộng).
- **Kỹ năng Bị động (Passive):**
  - Luôn kích hoạt hoặc kích hoạt theo điều kiện.
  - Thường là hào quang (Aura) tăng stat cho team hoặc nội tại bản thân.

### 3.2. Danh sách & Scaling kỹ năng chi tiết

Dưới đây là thông số kỹ thuật của 60 kỹ năng đồng đội.

- **Active Scaling:** Chỉ số gia tăng mỗi khi nâng cấp kỹ năng.
- **Passive Scaling:** Chỉ số gia tăng mỗi khi đồng đội lên sao/cấp (tùy config game).

#### A. Nhóm Bình dân (Common)

_Base Scaling: Active +5% Effect, Passive +0.5% Stat_

| Tên nhân vật      | Kỹ năng   | Loại    | Mô tả (Lv 1)                         | Scaling / Lvl |
| :---------------- | :-------- | :------ | :----------------------------------- | :------------ |
| **Bé Tí bắn bi**  | Bắn bi    | Active  | Bắn bi gây 120% sát thương chuẩn.    | +5% Dmg       |
|                   | Ham chơi  | Passive | Tăng 10% Tốc chạy khi không có địch. | +1% Speed     |
| **Chú Tư xe thồ** | Chặn đầu  | Active  | Chặn 1 đòn đánh cho chủ nhân.        | -0.1s CD      |
|                   | Thồ hàng  | Passive | Tăng 10 slot thùng đồ.               | +1 Slot       |
| **Cô Bảy**        | Quét sạch | Active  | Xóa 1 debuff ngẫu nhiên.             | +5% Heal      |
|                   | Cần lao   | Passive | Tăng 5% Vàng rơi từ quái.            | +0.5% Gold    |
| **Cậu Vàng**      | Cắn trộm  | Active  | 150% Dmg + Slow 30%.                 | +5% Dmg       |
|                   | Đánh hơi  | Passive | Tăng 10% tỉ lệ tìm rương.            | +1% Rate      |
| **Bác bảo vệ**    | Đèn pin   | Active  | Giảm chính xác địch trong 3s.        | +0.2s Dur     |
|                   | Gác đêm   | Passive | Tăng 10% tầm nhìn map tối.           | +2% View      |

#### B. Nhóm Tập sự (Uncommon)

_Base Scaling: Active +8% Effect, Passive +0.8% Stat_

| Tên nhân vật    | Kỹ năng   | Loại    | Mô tả (Lv 1)                            | Scaling / Lvl |
| :-------------- | :-------- | :------ | :-------------------------------------- | :------------ |
| **Chị tạp vụ**  | Lau sàn   | Active  | Lướt tới gây Stun 1.5s.                 | +8% Dmg       |
|                 | Sàn trơn  | Passive | 10% khiến địch trượt ngã khi đánh mình. | +1% Rate      |
| **Anh Grab**    | Giao hàng | Active  | Ném hộp cơm gây AOE.                    | +8% Dmg       |
|                 | Đúng giờ  | Passive | Tăng 20% Speed sau dùng skill.          | +2% Speed     |
| **Tèo net**     | Rớt mạng  | Active  | Đóng băng (Freeze) địch 2s.             | +0.2s Dur     |
|                 | Lag       | Passive | Xác chặn đường 5s sau khi chết.         | +0.5s Dur     |
| **Cô hàng xóm** | Buôn dưa  | Active  | Giảm 20% Giáp toàn bộ địch.             | +1% Debuff    |
|                 | Hóng hớt  | Passive | Hồi 2% HP mỗi 5s.                       | +0.2% Heal    |
| **Ông chú câu** | Quăng cần | Active  | Kéo địch yếu nhất về.                   | +8% Dmg       |
|                 | Kiên nhẫn | Passive | Đứng im 3s tăng 20% Dmg.                | +2% Dmg       |
| **Bà bán xôi**  | Xôi gà    | Active  | Hồi 15% HP cho ally thấp máu.           | +1% Heal      |
|                 | Sáng sớm  | Passive | Tăng 10% Max HP team.                   | +1% HP        |

#### C. Nhóm Chuyên nghiệp (Rare)

_Base Scaling: Active +10% Effect, Passive +1% Stat_

| Tên nhân vật     | Kỹ năng   | Loại    | Mô tả (Lv 1)                      | Scaling / Lvl |
| :--------------- | :-------- | :------ | :-------------------------------- | :------------ |
| **Chú Ba xe ôm** | Đón khách | Active  | Húc xe gây Choáng 2s + Taunt.     | +10% Dmg      |
|                  | Vượt đèn  | Passive | Miễn nhiễm làm chậm.              | +5% Speed     |
| **Cô Tư nước**   | Trà đá    | Active  | Hồi Energy + Tốc đánh team.       | +2 Energy     |
|                  | Chém gió  | Passive | Tăng 15% ASPD hào quang.          | +1% ASPD      |
| **Anh Bảy điện** | Đấu tắt   | Active  | Sét giật 3 mục tiêu.              | +10% Dmg      |
|                  | Tích điện | Passive | Đòn thứ 3 gây thêm dmg & tê liệt. | +5% Dmg       |
| **Chị Mười cá**  | Cá đông   | Active  | 300% Dmg Crit chắc chắn.          | +15% Dmg      |
|                  | Mồm mép   | Passive | Phản 20% dmg chuẩn.               | +2% Reflect   |
| **Ninja Lead**   | Xi nhan   | Active  | Tăng 50% Né trong 5s.             | +0.5s Dur     |
|                  | Áo nắng   | Passive | Giảm 20% Dmg Phép nhận vào.       | +2% Resist    |
| **Thầy bói mù**  | Phán xét  | Active  | Dmg to hoặc Heal địch (80/20).    | +10% Effect   |
|                  | Thiên cơ  | Passive | Tăng 5% Crit Rate team.           | +0.5% Crit    |
| **Anh shipper**  | Mưa hàng  | Active  | AOE liên tục vùng chỉ định.       | +12% Dmg      |
|                  | Freeship  | Passive | Giảm 10% CD cho đồng đội gần.     | +1% CD Red    |
| **Chị đại gym**  | Squat     | Active  | Dậm đất gây Slow diện rộng.       | +10% Dmg      |
|                  | Protein   | Passive | Tự hồi 1% HP/s.                   | +0.2% Heal    |

#### D. Nhóm Tinh anh (Epic)

_Base Scaling: Active +15% Effect, Passive +1.5% Stat_

| Tên nhân vật     | Kỹ năng    | Loại    | Mô tả (Lv 1)                     | Scaling / Lvl |
| :--------------- | :--------- | :------ | :------------------------------- | :------------ |
| **Tổ trưởng**    | Loa phường | Active  | Tăng 30% ATK team trong 10s.     | +2% Buff      |
|                  | Uy tín     | Passive | Tăng 20% HP cho Common allies.   | +2% HP        |
| **Thợ cắt tóc**  | Múa kéo    | Active  | Combo 5 hit gây Bleed.           | +15% Dmg      |
|                  | Tút tát    | Passive | Kill địch tăng 30% ASPD.         | +3% ASPD      |
| **Bà chủ trọ**   | Đòi tiền   | Active  | Hút máu địch tạo khiên.          | +2% Drain     |
|                  | Luật rừng  | Passive | HP < 50% giảm 15% Dmg nhận.      | +2% Resist    |
| **Youtuber**     | Mukbang    | Active  | Ăn đùi gà hồi 50% HP.            | +5% Heal      |
|                  | Mỡ thừa    | Passive | Tăng HP vĩnh viễn thi kill quái. | +10 HP        |
| **Rapper**       | Diss       | Active  | AOE Dmg + Silence 3s.            | +15% Dmg      |
|                  | Vần điệu   | Passive | +50% Dmg lên địch dính Debuff.   | +5% Dmg       |
| **Hotgirl**      | Thả tim    | Active  | Bất tử 2s cho ally hấp hối.      | +0.5s Dur     |
|                  | Donate     | Passive | 50% rớt item Máu/Mana mỗi 10s.   | +1% Rate      |
| **Thầy thể dục** | Hít đất    | Active  | Stack ATK vĩnh viễn khi kill.    | +2 ATK        |
|                  | Kỷ luật    | Passive | Tăng 10% Def hào quang.          | +1% Def       |

#### E. Nhóm Huyền thoại (Legendary)

_Base Scaling: Active +25% Effect, Passive +2.5% Stat_

| Tên nhân vật   | Kỹ năng   | Loại    | Mô tả (Lv 1)                     | Scaling / Lvl |
| :------------- | :-------- | :------ | :------------------------------- | :------------ |
| **Vua cờ bạc** | Thần bài  | Active  | Rút bài hiệu ứng ngẫu nhiên.     | +25% Dmg      |
|                | Gian lận  | Passive | 20% x2 Damage đòn thường.        | +2% Rate      |
| **Đại ca**     | Gọi đệ    | Active  | Triệu hồi 2 đệ tử (Stats theo %) | +5% Stats     |
|                | Bảo kê    | Passive | Share 30% Dmg cho đệ tử.         | +2% Share     |
| **Bà trùm**    | Sổ tử     | Active  | 50% HP đã mất thành Dmg chuẩn.   | +5% Dmg       |
|                | Nuôi lô   | Passive | Dmg skill tăng 10% mỗi lần dùng. | +2% Stack     |
| **Tiến sĩ**    | Hack      | Active  | Reset Cooldown cả team (60s).    | -2s CD        |
|                | Lý thuyết | Passive | Tăng 20% EXP toàn đội.           | +2% EXP       |

---

## 4. Hệ thống hiệu ứng (Status Effects)

### 4.1. Gây hại (Debuff)

- **Stun (Choáng):** Đứng im hoàn toàn.
- **Root (Trói):** Không di chuyển được, vẫn đánh được.
- **Silence (Câm lặng):** Không dùng được skill.
- **Slow (Làm chậm):** Giảm Speed/ASPD.
- **Poison/Burn/Bleed:** Trừ máu theo thời gian (DoT).
- **Armor Break (Phá giáp):** Giảm % phòng thủ.

### 4.2. Có lợi (Buff)

- **Haste:** Tăng tốc đánh.
- **Shield:** Lớp giáp ảo.
- **Immortal:** Bất tử tạm thời.
- **Lifesteal:** Hồi máu khi đánh.
- **Invisible:** Tàng hình, untargetable.
