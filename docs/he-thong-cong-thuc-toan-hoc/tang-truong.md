# Công thức Tăng trưởng

Mô tả các công thức liên quan đến sự phát triển sức mạnh (Scaling) của người chơi và quái vật, cũng như chi phí kinh tế (Inflation).

---

## 1. Chi phí nâng cấp (Upgrade Costs)

### 1.1. Level Up Nhân vật/Chỉ số

Nâng cấp chỉ số (Stat) bằng Vàng sử dụng công thức lũy thừa để tạo ra lạm phát giá, buộc người chơi phải kiếm nhiều vàng hơn ở các ải sau.

$$
Cost_{Lv} = BaseCost \times (GrowthFactor)^{Lv-1}
$$

- **BaseCost:** Giá tại level 1.
- **GrowthFactor:** Hệ số tăng giá (thường từ 1.05 đến 1.15).

**Bảng tham số chuẩn:**

| Stat          | Base Cost | Growth Factor | Ghi chú                                    |
| :------------ | :-------- | :------------ | :----------------------------------------- |
| **ATK**       | 100       | 1.07 (7%)     | Tăng giá vừa phải, chỉ số quan trọng nhất. |
| **HP**        | 100       | 1.06 (6%)     | Tăng giá chậm hơn chút để dễ sống sót.     |
| **Hồi phục**  | 200       | 1.08 (8%)     | Chỉ số phụ, giá cao hơn.                   |
| **Crit/ASPD** | 500       | 1.12 (12%)    | Chỉ số hiếm, tăng giá nhanh.               |

**Công thức tính tổng chi phí (Cumulative Cost):**
Để nâng từ Lv 1 đến Lv $n$:

$$
TotalCost_n = BaseCost \times \frac{(GrowthFactor^n - 1)}{GrowthFactor - 1}
$$

_(Đây là công thức tổng cấp số nhân)_

### 1.2. Level Up Trang bị

Chi phí nâng cấp trang bị thường dựa trên Bột rã đồ (Scrap) hoặc Đá cường hóa.

$$
UpgradeCost_{Eq} = BaseScrap \times (1.5)^{ItemTier} \times ItemLevel
$$

---

## 2. Sức mạnh Quái vật (Monster Scaling)

Quái vật mạnh lên theo Stage (Ải) và Wave (Đợt).

### 2.1. Scaling theo Stage (Chính)

Hệ thống sử dụng **Hàm mũ** để tạo độ khó "HP Wall".

$$
HP_{Monster}(Stage) = BaseHP \times (StageMultiplier)^{Stage}
$$

$$
ATK_{Monster}(Stage) = BaseATK \times (StageMultiplier)^{Stage}
$$

- **StageMultiplier (HP):** 1.20 (Tăng 20% máu mỗi ải).
- **StageMultiplier (ATK):** 1.15 (Tăng 15% dam mỗi ải - Tăng chậm hơn HP để tránh one-shot player).

### 2.2. Scaling theo Wave (Phụ)

Trong một ải có nhiều Wave, quái Wave sau mạnh hơn chút ít so với Wave trước.

$$
Stat_{Wave} = Stat_{Stage} \times (1 + WaveIndex \times 0.05)
$$

### 2.3. Boss Scaling

Boss tại các ải 5, 10, v.v... có chỉ số vượt trội so với quái thường.

- **Boss HP** = $Monster HP \times 10$.
- **Boss ATK** = $Monster ATK \times 1.5$.
- **Boss Time:** Giới hạn 60 giây để kill boss (DPS Check).

---

## 3. Lực chiến (Combat Power - CP)

Lực chiến là một con số tổng hợp để người chơi ước lượng sức mạnh. Nó không ảnh hưởng trực tiếp đến combat, chỉ dùng để hiển thị.

$$
CP = \sum (StatValue_i \times PowerWeight_i)
$$

**Trọng số quy đổi (Power Weight):**

| Chỉ số        | 1 đơn vị Stat bằng bao nhiêu CP? |
| :------------ | :------------------------------- |
| **ATK**       | 1.0 CP                           |
| **HP**        | 0.2 CP (5 HP = 1 CP)             |
| **DEF**       | 1.5 CP (Def hiếm hơn)            |
| **Crit Rate** | 20 CP (cho mỗi 1%)               |
| **Crit Dmg**  | 10 CP (cho mỗi 1%)               |
| **ASPD**      | 15 CP (cho mỗi 1%)               |

**Ví dụ:**
Nhân vật có: 1000 ATK, 5000 HP, 10% Crit Rate.

$$
CP = (1000 \times 1) + (5000 \times 0.2) + (10 \times 20)
= 1000 + 1000 + 200 = 2200 \text{ CP}
$$

---

## 4. Hệ thống Sao & Phẩm chất

Khi tăng sao (Star Up) hoặc đổi phẩm chất (Rarity), chỉ số cơ bản (Base Stat) sẽ được nhân lên.

$$
BaseStat_{New} = BaseStat_{Old} \times Multiplier_{StarUp}
$$

- 1 sao $\to$ 2 sao: $\times 1.5$
- 2 sao $\to$ 3 sao: $\times 1.5$
- ...
- 5 sao $\to$ 1 sao (Tier sau): $\times 2.0$

Điều này tạo động lực cực lớn cho việc gacha và nâng cấp tướng.
