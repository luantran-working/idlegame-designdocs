# Bảng cân bằng kinh tế (Economy Data Tables)

Tài liệu này cung cấp các bảng số liệu chi tiết để cân bằng game, bao gồm progression curves, drop rates, và cost scaling.

---

## 1. Bảng scaling chỉ số quái vật

### 1.1. HP và ATK theo Ải

**Công thức cơ bản:**

- $HP = BaseHP \times (1.15)^{Stage}$
- $ATK = BaseATK \times (1.12)^{Stage}$

| Ải  | Chương | HP Quái thường | HP Elite (x3) | HP Boss (x10) | ATK Quái | Gold/con |
| :-- | :----- | :------------- | :------------ | :------------ | :------- | :------- |
| 1   | 1      | 100            | 300           | 1,000         | 10       | 5        |
| 5   | 1      | 200            | 600           | 2,000         | 18       | 12       |
| 10  | 1      | 400            | 1,200         | 4,000         | 31       | 25       |
| 15  | 2      | 800            | 2,400         | 8,000         | 55       | 50       |
| 20  | 2      | 1,600          | 4,800         | 16,000        | 97       | 100      |
| 30  | 3      | 6,600          | 19,800        | 66,000        | 300      | 350      |
| 40  | 4      | 27,000         | 81,000        | 270,000       | 930      | 1,200    |
| 50  | 5      | 110,000        | 330,000       | 1,100,000     | 2,900    | 4,000    |
| 75  | 7-8    | 2,500,000      | 7,500,000     | 25,000,000    | 50,000   | 50,000   |
| 100 | 10     | 57,000,000     | 171,000,000   | 570,000,000   | 850,000  | 300,000  |

### 1.2. Yêu cầu lực chiến khuyến nghị

| Ải Range | Lực chiến min    | Lực chiến comfort | Thời gian farm dự kiến |
| :------- | :--------------- | :---------------- | :--------------------- |
| 1-10     | 0 - 500          | 300 - 800         | 0-30 phút              |
| 11-20    | 500 - 2,000      | 1,500 - 3,500     | 30 phút - 2 giờ        |
| 21-30    | 2,000 - 8,000    | 6,000 - 12,000    | 2 giờ - 1 ngày         |
| 31-40    | 8,000 - 30,000   | 25,000 - 50,000   | 1-3 ngày               |
| 41-50    | 30,000 - 100,000 | 80,000 - 150,000  | 3-7 ngày               |
| 51-75    | 100,000 - 1M     | 500,000 - 2M      | 1-2 tuần               |
| 76-100   | 1M - 10M         | 5M - 20M          | 2-4 tuần               |

---

## 2. Bảng chi phí nâng cấp

### 2.1. Nâng cấp chỉ số bằng Vàng

**Công thức:** $Cost = 10 \times (1.07)^{Level}$

| Level | Chi phí   | Tổng đã tiêu | ATK/HP tăng thêm |
| :---- | :-------- | :----------- | :--------------- |
| 1     | 10        | 10           | +1               |
| 10    | 19        | 138          | +1               |
| 25    | 54        | 623          | +1               |
| 50    | 294       | 4,131        | +1               |
| 100   | 8,676     | 121,868      | +1               |
| 150   | 256,158   | 3,602,283    | +1               |
| 200   | 7,564,684 | 106,426,700  | +1               |
| 300   | 6.6B      | 93B          | +1               |
| 500   | 5.1T      | 72T          | +1               |

### 2.2. Nâng cấp trang bị

**Công thức:** $Cost = BaseCost \times Rarity\_Mult \times (1.05)^{Level}$

| Rarity Multiplier |
| :---------------- |
| Trắng: 1.0        |
| Xanh lá: 1.5      |
| Xanh dương: 2.5   |
| Tím: 4.0          |
| Cam: 7.0          |
| Đỏ: 12.0          |

**Bảng chi phí mẫu (Vũ khí Cam):**

| Level   | Vàng cần   | Cờ lê cần | ATK tăng |
| :------ | :--------- | :-------- | :------- |
| 1->10   | 7,000      | 10        | +500     |
| 10->20  | 20,000     | 25        | +600     |
| 20->30  | 50,000     | 50        | +700     |
| 30->40  | 120,000    | 100       | +800     |
| 40->50  | 280,000    | 200       | +1,000   |
| 50->60  | 650,000    | 350       | +1,200   |
| 60->70  | 1,500,000  | 500       | +1,500   |
| 70->80  | 3,500,000  | 750       | +2,000   |
| 80->90  | 8,000,000  | 1,000     | +2,500   |
| 90->100 | 18,000,000 | 1,500     | +3,500   |

### 2.3. Nâng cấp đồng đội

| Level  | Vàng    | Bánh mì | Stat tăng |
| :----- | :------ | :------ | :-------- |
| 1->10  | 5,000   | 10      | +10%      |
| 10->20 | 15,000  | 30      | +10%      |
| 20->30 | 40,000  | 60      | +10%      |
| 30->40 | 100,000 | 100     | +10%      |
| 40->50 | 250,000 | 150     | +10%      |

**Tăng sao đồng đội:**

| Sao  | Mảnh cần | Bonus stat |
| :--- | :------- | :--------- |
| 1->2 | 20       | +20%       |
| 2->3 | 50       | +25%       |
| 3->4 | 100      | +30%       |
| 4->5 | 200      | +50%       |

---

## 3. Bảng thu nhập tài nguyên

### 3.1. Thu nhập Vàng theo nguồn (per day - active play 30 min)

| Nguồn            | Level 1-20 | Level 21-50 | Level 51-100  | Level 100+    |
| :--------------- | :--------- | :---------- | :------------ | :------------ |
| Farm quái        | 5,000      | 30,000      | 200,000       | 2,000,000     |
| AFK (8h)         | 10,000     | 80,000      | 600,000       | 5,000,000     |
| Nhiệm vụ ngày    | 3,000      | 15,000      | 50,000        | 100,000       |
| Phó bản (3 lượt) | 10,000     | 50,000      | 200,000       | 1,000,000     |
| **Tổng/ngày**    | **28,000** | **175,000** | **1,050,000** | **8,100,000** |

### 3.2. Thu nhập Kim cương (F2P per day)

| Nguồn              | Số lượng    |
| :----------------- | :---------- |
| Nhiệm vụ ngày      | 30-50       |
| Vượt ải lần đầu    | 10-30       |
| Arena daily        | 10-30       |
| Xem quảng cáo      | 50          |
| Event (trung bình) | 20          |
| **Tổng/ngày**      | **120-180** |

### 3.3. Thu nhập F2P vs Tiêu thụ

| Hạng mục         | Thu/ngày  | Tiêu/ngày (optimal) | Balance  |
| :--------------- | :-------- | :------------------ | :------- |
| Vàng (Mid-game)  | 175,000   | 200,000             | -25,000  |
| Vàng (Late-game) | 1,050,000 | 1,500,000           | -450,000 |
| Kim cương        | 150       | 300 (gacha x1)      | -150     |

_Thiếu hụt được bù bằng: Event, Thành tựu, AFK lâu hơn, Nạp tiền_

---

## 4. Bảng Drop Rate

### 4.1. Drop trang bị từ quái

| Loại quái   | Drop rate | Phẩm chất distribution                        |
| :---------- | :-------- | :-------------------------------------------- |
| Quái thường | 2%        | 80% Trắng, 15% Xanh lá, 4% Xanh dương, 1% Tím |
| Quái Elite  | 10%       | 50% Xanh lá, 35% Xanh dương, 12% Tím, 3% Cam  |
| Boss ải     | 100%      | 40% Xanh dương, 40% Tím, 18% Cam, 2% Đỏ       |

### 4.2. Gacha rates

**Banner Trang bị:**

| Phẩm chất  | Rate | Pity                    |
| :--------- | :--- | :---------------------- |
| Trắng      | 50%  | -                       |
| Xanh lá    | 30%  | -                       |
| Xanh dương | 15%  | Đảm bảo 1/10 pull       |
| Tím        | 4%   | -                       |
| Cam        | 0.9% | Soft pity @50, Hard @80 |
| Đỏ         | 0.1% | Hard pity @200          |

**Banner Đồng đội:**

| Phẩm chất | Rate | Pity                    |
| :-------- | :--- | :---------------------- |
| Mảnh Rare | 60%  | -                       |
| Rare full | 25%  | Đảm bảo 1/10 pull       |
| Epic      | 10%  | -                       |
| Legendary | 4.5% | Soft pity @50, Hard @80 |
| Feature   | 0.5% | Hard pity @180 (50/50)  |

---

## 5. Bảng tiến độ người chơi

### 5.1. Player Journey milestones

| Ngày chơi | Level dự kiến | Ải cao nhất | Lực chiến       | Milestone              |
| :-------- | :------------ | :---------- | :-------------- | :--------------------- |
| Ngày 1    | 1-15          | 1-10        | 100-1,000       | Tutorial complete      |
| Ngày 3    | 20-30         | 15-25       | 2,000-5,000     | Full team unlocked     |
| Ngày 7    | 40-50         | 30-40       | 10,000-30,000   | Ch.3-4, Gacha unlocked |
| Ngày 14   | 60-80         | 45-55       | 50,000-150,000  | First Prestige         |
| Ngày 30   | 100-120       | 60-75       | 200,000-500,000 | Multiple Prestige      |
| Ngày 60   | 150+          | 80-100      | 1M-5M           | Full Legendary team    |
| Ngày 90   | 200+          | 100+        | 10M+            | Endgame content        |

### 5.2. Retention targets

| Metric | Target | Critical | Excellent |
| :----- | :----- | :------- | :-------- |
| D1     | 40%    | &lt;30%  | &gt;50%   |
| D7     | 15%    | &lt;10%  | &gt;20%   |
| D30    | 5%     | &lt;3%   | &gt;8%    |
| D60    | 3%     | &lt;2%   | &gt;5%    |

---

## 6. Bảng Monetization

### 6.1. Giá IAP và giá trị

| Gói          | Giá (VND) | KC    | Bonus lần đầu | KC/1000đ |
| :----------- | :-------- | :---- | :------------ | :------- |
| Gói nhỏ      | 22,000    | 60    | +60           | 2.7      |
| Gói vừa      | 109,000   | 330   | +330          | 3.0      |
| Gói lớn      | 499,000   | 1,800 | +1,800        | 3.6      |
| Gói khủng    | 1,099,000 | 4,200 | +4,200        | 3.8      |
| Gói ultimate | 2,199,000 | 9,000 | +9,000        | 4.1      |

### 6.2. ARPU/ARPPU targets

| Metric | Target (VND)    | Industry benchmark |
| :----- | :-------------- | :----------------- |
| ARPDAU | 500-1,000       | 300-800            |
| ARPU   | 15,000-30,000   | 10,000-25,000      |
| ARPPU  | 300,000-500,000 | 250,000-400,000    |

### 6.3. Conversion funnel

| Stage                    | Target rate |
| :----------------------- | :---------- |
| Install -> D1            | 40%         |
| D1 -> D7                 | 35%         |
| D7 -> First purchase     | 5-8%        |
| First -> Second purchase | 40-50%      |
| Whale (>1M VND/month)    | 0.5-1%      |

---

## 7. Công cụ cân bằng

### 7.1. Formulas cheat sheet

```
# Damage
FinalDamage = ATK * SkillMult * (1 - DEF/(DEF+5000)) * CritMult

# Power Rating
CP = ATK + HP/5 + DEF*2 + CritRate*100 + ASPD*500 + CritDmg*50

# Cost Scaling
UpgradeCost = BaseCost * (GrowthRate ^ Level)

# Drop Rate Boost
EffectiveRate = BaseRate * (1 + BonusRate%) * (1 + LuckStat/100)

# AFK Reward
AFKGold = GoldPerMinute * min(OfflineMinutes, MaxAFKMinutes) * AFKBonus
```

### 7.2. Balance checklist

- [ ] F2P có thể hoàn thành main story trong 30 ngày
- [ ] Whale không vượt quá 3x power so với F2P cùng thời gian
- [ ] Mỗi hệ thống có ít nhất 1 sink cho gold
- [ ] Kim cương income đủ cho 2 x10 pull/tuần (F2P)
- [ ] Prestige tăng ít nhất 20% progression speed
- [ ] Boss không thể one-shot player ở lực chiến comfort
