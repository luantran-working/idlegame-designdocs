# Tổng quan bảng toán chỉ số

Đây là mục lục tổng hợp cho tất cả các bảng toán chỉ số trong game. Tài liệu này giúp đội phát triển nhanh chóng tìm kiếm thông tin cần thiết.

---

## Danh sách tài liệu

### 1. [Chỉ số nhân vật chính](./chi-so-nhan-vat.md)

Định nghĩa các chỉ số cơ bản của player character:

- Chỉ số chính: ATK, HP, HP_REGEN, DEF
- Chỉ số phụ: ASPD, CRIT Rate, CRIT DMG, Dodge, Lifesteal
- Công thức tính chi phí nâng cấp
- Công thức DPS và Damage output

### 2. [Chỉ số kỹ năng chính](./chi-so-ky-nang-chinh.md)

Thông số kỹ thuật cho 20 kỹ năng của nhân vật chính:

- 10 kỹ năng tấn công (Ném gạch, Mưa thiên thạch, ...)
- 5 kỹ năng khống chế (Tiếng thét, Mắt lé, ...)
- 5 kỹ năng hỗ trợ (Băng bó, Gồng mình, ...)
- Công thức scaling theo level
- Chi phí nâng cấp

### 3. [Chỉ số kỹ năng đồng đội](./chi-so-ky-nang-dong-doi.md)

Thông số cho 60 kỹ năng đồng đội (30 Active + 30 Passive):

- Phân loại theo phẩm chất: Common → Legendary
- Energy system mechanics
- Scaling theo level và star rank
- Tier list và priority

### 4. [Chỉ số quái vật](./chi-so-quai-vat.md)

Chi tiết 48 quái thường + 4 Boss:

- Base stats theo chapter
- Công thức scaling theo Stage/Wave
- Kỹ năng đặc biệt của từng loại quái
- Boss phase và mechanics
- Reward system (EXP, Gold, Drop rate)

### 5. [Chỉ số cấp độ tầng](./chi-so-cap-do-tang.md)

Hệ thống Stage progression:

- Cấu trúc Chapter → Stage → Wave
- Difficulty scaling curves
- Unlock system và milestone
- Idle/AFK progression
- Challenge mode modifiers

### 6. [Chỉ số tăng trưởng](./chi-so-tang-truong.md)

Công thức và curve progression:

- Chi phí nâng cấp cho mọi hệ thống
- Efficiency curves và diminishing returns
- Combat Power (CP) calculation
- F2P vs Whale progression timeline

### 7. [Chỉ số trang bị](./chi-so-trang-bi.md)

Hệ thống equipment chi tiết:

- Base stats theo Slot + Tier + Rarity
- Sub-stats system và roll quality
- Upgrade, Merge, Reforge mechanics
- Set bonus effects

### 8. [Chỉ số đồng đội](./chi-so-dong-doi.md)

Stats và scaling cho 30 đồng đội:

- Base stats theo Class và Rarity
- Level và Star rank multipliers
- Chi phí level up và promotion
- Affinity (duyên phận) system

---

## Quick Reference

### Các công thức frequently used

#### Chi phí nâng cấp (Exponential)

$$Cost(Level) = BaseCost \times (GrowthRate)^{Level-1}$$

#### Sát thương đầu ra

$$Damage = ATK \times SkillMult \times (1 + Bonus\%) \times CritMult$$

#### Giảm sát thương (DEF)

$$Reduction = \frac{DEF}{DEF + DEF\_CONSTANT}$$

#### Lực chiến (Combat Power)

$$CP = ATK \times 1.0 + HP \times 0.2 + DEF \times 2.0 + CRIT\% \times 20 + ASPD\% \times 500$$

---

## Các hằng số quan trọng

| Constant      | Value | Usage                    |
| :------------ | :---- | :----------------------- |
| DEF_CONSTANT  | 5,000 | Damage reduction formula |
| ASPD_CAP      | 5.0   | Max attacks per second   |
| CRIT_RATE_CAP | 100%  | Max critical chance      |
| DODGE_CAP     | 80%   | Max dodge chance         |
| SLOW_CAP      | 80%   | Max slow effect          |
| CDR_CAP       | 50%   | Max cooldown reduction   |

---

## Sử dụng tài liệu này

### Cho Game Designer

1. Sử dụng bảng stats để cân bằng content
2. Tham khảo công thức để tạo content mới
3. Check progression timeline để verify game pace

### Cho Developer

1. Implement công thức chính xác như documented
2. Sử dụng constants từ bảng reference
3. Follow data structure templates

### Cho QA

1. Verify stats match với tài liệu
2. Test edge cases (cap values)
3. Validate progression curves

---

## Changelog

| Phiên bản | Ngày       | Thay đổi                          |
| :-------- | :--------- | :-------------------------------- |
| 1.0       | 2026-01-26 | Khởi tạo toàn bộ bảng toán chỉ số |
