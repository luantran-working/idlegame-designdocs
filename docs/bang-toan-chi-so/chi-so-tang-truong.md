# Chỉ số tăng trưởng

Tài liệu này định nghĩa chi tiết các công thức tăng trưởng sức mạnh, chi phí nâng cấp, và các curve progression trong game.

---

## 1. Tổng quan hệ thống tăng trưởng

### 1.1. Các nguồn tăng sức mạnh

Player có thể tăng sức mạnh từ các nguồn sau:

| Nguồn            | Loại tăng      | Giới hạn      | Chi phí chính |
| :--------------- | :------------- | :------------ | :------------ |
| **Stat Upgrade** | ATK, HP, REGEN | Soft cap      | Vàng          |
| **Equipment**    | All stats      | Tier + Rarity | Vàng + Scrap  |
| **Skills**       | Skill power    | Level 50      | Vàng + Books  |
| **Teammates**    | Passive buffs  | Star + Level  | Shards + Vàng |
| **Set Bonus**    | % bonus        | 4 món         | Equipment     |
| **Affinity**     | Hidden stats   | 5 tướng       | Own teammates |

### 1.2. Contribution Breakdown (Lý tưởng)

Phân bố sức mạnh lý tưởng tại các mốc game:

| Giai đoạn      | Stat Upgrade | Equipment | Skills | Teammates |
| :------------- | :----------- | :-------- | :----- | :-------- |
| Early (1-25)   | 60%          | 25%       | 10%    | 5%        |
| Mid (26-75)    | 40%          | 35%       | 15%    | 10%       |
| Late (76-150)  | 25%          | 40%       | 15%    | 20%       |
| Endgame (150+) | 15%          | 35%       | 15%    | 35%       |

---

## 2. Công thức nâng cấp chỉ số (Stat Upgrade)

### 2.1. Chi phí nâng cấp

Công thức chung cho chi phí:

$$Cost_{level} = BaseCost \times (GrowthRate)^{Level-1}$$

### 2.2. Tham số cho từng stat

| Stat         | Base Cost | Growth Rate | Giá trị tăng/Level |
| :----------- | :-------- | :---------- | :----------------- |
| **ATK**      | 100       | 1.07        | +5 ATK             |
| **HP**       | 100       | 1.06        | +25 HP             |
| **HP Regen** | 200       | 1.08        | +0.5 HP/s          |
| **DEF**      | 500       | 1.12        | +2 DEF             |

### 2.3. Bảng chi phí chi tiết

#### ATK Upgrade (Growth 1.07)

| Level | Cost   | Cumulative Cost | Total ATK Gain |
| :---- | :----- | :-------------- | :------------- |
| 1     | 100    | 100             | +5             |
| 10    | 184    | 1,306           | +50            |
| 25    | 505    | 5,427           | +125           |
| 50    | 2,947  | 38,837          | +250           |
| 100   | 86,771 | 1,208,467       | +500           |
| 200   | 7.53M  | 111M            | +1,000         |
| 500   | 4.6T   | 68.5T           | +2,500         |

#### HP Upgrade (Growth 1.06)

| Level | Cost   | Cumulative Cost | Total HP Gain |
| :---- | :----- | :-------------- | :------------ |
| 1     | 100    | 100             | +25           |
| 10    | 169    | 1,248           | +250          |
| 25    | 405    | 4,292           | +625          |
| 50    | 1,842  | 28,168          | +1,250        |
| 100   | 33,930 | 545,917         | +2,500        |
| 200   | 1.15M  | 19.4M           | +5,000        |
| 500   | 4.87B  | 84.6B           | +12,500       |

### 2.4. Công thức tổng chi phí (Cumulative)

$$TotalCost_{1 \to n} = BaseCost \times \frac{GrowthRate^n - 1}{GrowthRate - 1}$$

---

## 3. Tăng trưởng trang bị

### 3.1. Base Stats theo Tier

| Tier    | Base ATK | Base HP | Base ASPD | Base CRIT |
| :------ | :------- | :------ | :-------- | :-------- |
| Tier 1  | 10       | 50      | 0.02      | 0.5%      |
| Tier 2  | 25       | 125     | 0.05      | 1.0%      |
| Tier 3  | 60       | 300     | 0.10      | 2.0%      |
| Tier 4  | 150      | 750     | 0.20      | 4.0%      |
| Tier 5  | 400      | 2,000   | 0.40      | 8.0%      |
| Tier 6  | 1,000    | 5,000   | 0.70      | 12.0%     |
| Tier 7  | 2,500    | 12,500  | 1.00      | 16.0%     |
| Tier 8  | 6,000    | 30,000  | 1.30      | 20.0%     |
| Tier 9  | 15,000   | 75,000  | 1.50      | 25.0%     |
| Tier 10 | 40,000   | 200,000 | 1.80      | 30.0%     |

### 3.2. Rarity Multiplier

| Rarity    | Stat Multiplier | Sub-stats | Max Level |
| :-------- | :-------------- | :-------- | :-------- |
| Common    | 1.0x            | 0         | 20        |
| Uncommon  | 1.2x            | 1         | 40        |
| Rare      | 1.5x            | 2         | 60        |
| Epic      | 2.0x            | 3         | 80        |
| Legendary | 3.0x            | 4         | 100       |
| Mythic    | 5.0x            | 4+Skill   | 120       |

### 3.3. Equipment Level Scaling

$$EquipStat_{level} = BaseStat \times RarityMult \times (1 + Level \times 0.02)$$

**Ví dụ:** Tier 5 Legendary Weapon Level 50
$$ATK = 400 \times 3.0 \times (1 + 50 \times 0.02) = 400 \times 3.0 \times 2.0 = 2,400$$

### 3.4. Equipment Upgrade Cost

| Level Range | Gold Cost/Level | Scrap Cost/Level |
| :---------- | :-------------- | :--------------- |
| 1-20        | 100             | 5                |
| 21-40       | 500             | 15               |
| 41-60       | 2,000           | 40               |
| 61-80       | 8,000           | 100              |
| 81-100      | 30,000          | 250              |
| 101-120     | 100,000         | 500              |

---

## 4. Tăng trưởng đồng đội

### 4.1. Level Scaling

$$TeammateStats_{level} = BaseStats \times RarityMult \times (1 + (Level-1) \times 0.03)$$

### 4.2. Star Rank Multiplier

| Star Rank | Stats Multiplier | Passive Bonus | Shards Required |
| :-------- | :--------------- | :------------ | :-------------- |
| 1★        | 1.0x             | Base          | 0               |
| 2★        | 1.5x             | +1 tier       | 10              |
| 3★        | 2.0x             | +2 tier       | 30              |
| 4★        | 3.0x             | +3 tier       | 60              |
| 5★        | 5.0x             | +4 tier       | 120             |
| 6★        | 8.0x             | Max           | 200             |

### 4.3. Công thức sức mạnh đồng đội

$$Power_{teammate} = BaseStats \times RarityMult \times StarMult \times LevelMult$$

**Ví dụ:** Legendary 5★ Level 80
$$Power = 1000 \times 3.0 \times 5.0 \times (1 + 79 \times 0.03) = 1000 \times 3.0 \times 5.0 \times 3.37 = 50,550$$

---

## 5. Skill Growth

### 5.1. Skill Level Cost

| Level Range | Gold Cost/Level | Skill Books/Level |
| :---------- | :-------------- | :---------------- |
| 1-10        | 1,000           | 1                 |
| 11-20       | 5,000           | 3                 |
| 21-30       | 20,000          | 5                 |
| 31-40       | 100,000         | 10                |
| 41-50       | 500,000         | 25                |

### 5.2. Skill Damage Scaling

Damage skills follow linear scaling:

$$SkillDmg_{level} = BaseDmg\% + (ScalingPerLevel \times (Level-1))$$

---

## 6. Lực chiến (Combat Power)

### 6.1. Công thức tính tổng

$$CP = \sum_{i}(Stat_i \times Weight_i)$$

### 6.2. Bảng trọng số

| Stat      | Weight | Explanation      |
| :-------- | :----- | :--------------- |
| ATK       | 1.0    | Baseline         |
| HP        | 0.2    | 5 HP = 1 CP      |
| DEF       | 2.0    | DEF khó tăng     |
| ASPD      | 500    | 0.01 ASPD = 5 CP |
| CRIT Rate | 20     | 1% = 20 CP       |
| CRIT DMG  | 10     | 1% = 10 CP       |
| Lifesteal | 30     | 1% = 30 CP       |
| Dodge     | 25     | 1% = 25 CP       |

### 6.3. CP Milestone

| CP Range       | Game Phase      | Expected Content |
| :------------- | :-------------- | :--------------- |
| 0 - 1,000      | Tutorial        | Stage 1-5        |
| 1,000 - 5,000  | Early Game      | Stage 5-15       |
| 5,000 - 25,000 | Early-Mid       | Stage 15-35      |
| 25,000 - 100K  | Mid Game        | Stage 35-60      |
| 100K - 500K    | Mid-Late        | Stage 60-90      |
| 500K - 2M      | Late Game       | Stage 90-130     |
| 2M - 10M       | Endgame         | Stage 130-180    |
| 10M+           | Whale Territory | Stage 180+       |

---

## 7. Progression Timeline

### 7.1. F2P Daily Progress (Active 2h/day)

| Day | Expected CP | Highest Stage | Key Milestone      |
| :-- | :---------- | :------------ | :----------------- |
| 1   | 500         | 3             | Complete tutorial  |
| 3   | 2,000       | 10            | First boss clear   |
| 7   | 8,000       | 25            | Full Common team   |
| 14  | 25,000      | 45            | Rare equipment set |
| 30  | 80,000      | 70            | Epic equipment     |
| 60  | 250,000     | 100           | First Legendary    |
| 90  | 600,000     | 130           | Full Epic team     |

### 7.2. Whale Progress (Unlimited spend)

| Day | Expected CP | Highest Stage | Key Milestone        |
| :-- | :---------- | :------------ | :------------------- |
| 1   | 5,000       | 15            | Premium starter pack |
| 3   | 50,000      | 50            | Full Rare team       |
| 7   | 300,000     | 100           | Multiple Legendary   |
| 14  | 2,000,000   | 150           | Full Legendary team  |
| 30  | 10,000,000  | 200           | Max everything       |

---

## 8. Diminishing Returns

### 8.1. Efficiency Curve

Hiệu quả của mỗi đồng vàng bỏ ra giảm dần:

$$Efficiency_{level} = \frac{StatGain}{Cost_{level}} = \frac{Flat}{\text{BaseCost} \times \text{GrowthRate}^{Level-1}}$$

### 8.2. Bảng efficiency

| ATK Level | Cost   | ATK Gain | Efficiency (ATK/Gold) |
| :-------- | :----- | :------- | :-------------------- |
| 1         | 100    | 5        | 0.0500                |
| 10        | 184    | 5        | 0.0272                |
| 50        | 2,947  | 5        | 0.0017                |
| 100       | 86,771 | 5        | 0.000058              |
| 200       | 7.53M  | 5        | 0.00000066            |

**Kết luận:** Sau Level 100, việc upgrade stat trở nên rất kém hiệu quả, player nên focus vào equipment và teammates.

---

## 9. Hướng dẫn cho đội phát triển

### 9.1. Cho lập trình viên

- Sử dụng BigNumber library cho số lớn (>10^15)
- Cache calculated stats, chỉ recalculate khi có thay đổi
- Implement offline progress calculation với delta compression
- Validate tất cả upgrade requests server-side

### 9.2. Cho game designer

- Điều chỉnh GrowthRate (1.05-1.10) để control speed
- First clear bonuses nên đủ để push 2-3 stage
- F2P player nên có progression rõ ràng trong 7 ngày đầu
- Power wall nên có "escape hatch" qua side content

### 9.3. Monetization Integration

| Power Source | F2P Rate | Premium Rate | Revenue Impact |
| :----------- | :------- | :----------- | :------------- |
| Gold         | 100%     | 300%         | Medium         |
| Equipment    | 70%      | 150%         | High           |
| Teammates    | 50%      | 200%         | Very High      |
| Skills       | 90%      | 110%         | Low            |

**Philosophy:** F2P có thể đạt mọi thứ, Premium đạt nhanh hơn 3-5x.
