# Hệ thống kỹ năng (Skills)

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

### 3.2. Chi tiết

_(Xem chi tiết danh sách kỹ năng của từng đồng đội trong tài liệu **Hệ thống đồng đội**)_.

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
