# Chỉ số trang bị

Tài liệu này định nghĩa chi tiết các thông số kỹ thuật, công thức tính toán và bảng cân bằng cho hệ thống trang bị.

---

## 1. Cấu trúc hệ thống trang bị

### 1.1. Slot trang bị

Player có 4 slot trang bị:

| Slot           | Chỉ số chính            | Biểu tượng | Tầm quan trọng |
| :------------- | :---------------------- | :--------- | :------------- |
| **Vũ khí**     | ATK, ATK%               | Kiếm       | DPS            |
| **Áo giáp**    | HP, HP%, DEF            | Khiên      | Survival       |
| **Giày**       | ASPD, ASPD%, Move Speed | Giày       | DPS            |
| **Dây chuyền** | CRIT Rate, CRIT DMG     | Vòng       | Burst          |

### 1.2. Phẩm chất (Rarity)

| Rarity    | Màu        | Sub-stats | Max Level | Drop Rate (Farm) | Drop Rate (Gacha) |
| :-------- | :--------- | :-------- | :-------- | :--------------- | :---------------- |
| Common    | Trắng      | 0         | 20        | 60%              | 50%               |
| Uncommon  | Xanh lá    | 1         | 40        | 30%              | 30%               |
| Rare      | Xanh dương | 2         | 60        | 8%               | 15%               |
| Epic      | Tím        | 3         | 80        | 1.5%             | 4%                |
| Legendary | Cam        | 4         | 100       | 0.4%             | 0.9%              |
| Mythic    | Đỏ         | 4+Skill   | 120       | 0.1%             | 0.1%              |

### 1.3. Tier hệ thống

| Tier | Tên gợi ý     | Stage Drop | Base Stat Mult |
| :--- | :------------ | :--------- | :------------- |
| 1    | Đồ rác        | 1-10       | 1.0x           |
| 2    | Đồ phế liệu   | 11-25      | 2.5x           |
| 3    | Đồ tạm dùng   | 26-40      | 6.0x           |
| 4    | Đồ ổn         | 41-60      | 15.0x          |
| 5    | Đồ tốt        | 61-80      | 40.0x          |
| 6    | Đồ xịn        | 81-100     | 100.0x         |
| 7    | Đồ siêu xịn   | 101-130    | 250.0x         |
| 8    | Đồ thần thoại | 131-160    | 600.0x         |
| 9    | Đồ vô song    | 161-190    | 1,500x         |
| 10   | Đồ tối thượng | 191+       | 4,000x         |

---

## 2. Base Stats theo Slot & Tier

### 2.1. Vũ khí (Weapon) - Main stat: ATK

| Tier | Common ATK | Uncommon ATK | Rare ATK | Epic ATK | Legendary ATK | Mythic ATK |
| :--- | :--------- | :----------- | :------- | :------- | :------------ | :--------- |
| 1    | 10         | 12           | 15       | 20       | 30            | 50         |
| 2    | 25         | 30           | 38       | 50       | 75            | 125        |
| 3    | 60         | 72           | 90       | 120      | 180           | 300        |
| 4    | 150        | 180          | 225      | 300      | 450           | 750        |
| 5    | 400        | 480          | 600      | 800      | 1,200         | 2,000      |
| 6    | 1,000      | 1,200        | 1,500    | 2,000    | 3,000         | 5,000      |
| 7    | 2,500      | 3,000        | 3,750    | 5,000    | 7,500         | 12,500     |
| 8    | 6,000      | 7,200        | 9,000    | 12,000   | 18,000        | 30,000     |
| 9    | 15,000     | 18,000       | 22,500   | 30,000   | 45,000        | 75,000     |
| 10   | 40,000     | 48,000       | 60,000   | 80,000   | 120,000       | 200,000    |

### 2.2. Áo giáp (Armor) - Main stat: HP hoặc DEF

| Tier | HP (Base) | DEF (Base) | HP Rarity Mult | DEF Rarity Mult |
| :--- | :-------- | :--------- | :------------- | :-------------- |
| 1    | 50        | 5          | Same as ATK    | Same as ATK     |
| 2    | 125       | 12         | -              | -               |
| 3    | 300       | 30         | -              | -               |
| 4    | 750       | 75         | -              | -               |
| 5    | 2,000     | 200        | -              | -               |
| 6    | 5,000     | 500        | -              | -               |
| 7    | 12,500    | 1,250      | -              | -               |
| 8    | 30,000    | 3,000      | -              | -               |
| 9    | 75,000    | 7,500      | -              | -               |
| 10   | 200,000   | 20,000     | -              | -               |

### 2.3. Giày (Boots) - Main stat: ASPD

| Tier | ASPD Base (flat) | ASPD% Max | Move Speed Base |
| :--- | :--------------- | :-------- | :-------------- |
| 1    | 0.02             | 2%        | +5%             |
| 2    | 0.05             | 4%        | +8%             |
| 3    | 0.10             | 6%        | +12%            |
| 4    | 0.20             | 10%       | +16%            |
| 5    | 0.40             | 15%       | +22%            |
| 6    | 0.70             | 22%       | +30%            |
| 7    | 1.00             | 30%       | +40%            |
| 8    | 1.30             | 40%       | +50%            |
| 9    | 1.50             | 50%       | +60%            |
| 10   | 1.80             | 60%       | +75%            |

### 2.4. Dây chuyền (Accessory) - Main stat: CRIT

| Tier | CRIT Rate Base | CRIT DMG Base | CRIT Rate Max | CRIT DMG Max |
| :--- | :------------- | :------------ | :------------ | :----------- |
| 1    | 0.5%           | 5%            | 2%            | 15%          |
| 2    | 1.0%           | 8%            | 4%            | 25%          |
| 3    | 2.0%           | 12%           | 7%            | 40%          |
| 4    | 4.0%           | 18%           | 12%           | 60%          |
| 5    | 8.0%           | 25%           | 20%           | 90%          |
| 6    | 12.0%          | 35%           | 30%           | 130%         |
| 7    | 16.0%          | 50%           | 40%           | 180%         |
| 8    | 20.0%          | 70%           | 50%           | 240%         |
| 9    | 25.0%          | 100%          | 60%           | 320%         |
| 10   | 30.0%          | 150%          | 70%           | 400%         |

---

## 3. Sub-stats System

### 3.1. Sub-stat Pool

| Sub-stat   | Flat Range (Tier 1) | % Range (Tier 1) | Scale per Tier |
| :--------- | :------------------ | :--------------- | :------------- |
| ATK        | 1-5                 | 1-2%             | 2.5x           |
| HP         | 5-25                | 1-3%             | 2.5x           |
| DEF        | 1-3                 | 1-2%             | 2.5x           |
| ASPD       | 0.01-0.03           | 0.5-1%           | 2x             |
| CRIT Rate  | 0.1-0.5%            | -                | 2x             |
| CRIT DMG   | 1-3%                | -                | 2x             |
| Lifesteal  | 0.5-1%              | -                | 1.5x           |
| Dodge      | 0.3-1%              | -                | 1.5x           |
| Skill DMG  | 1-2%                | -                | 2x             |
| Gold Bonus | 1-3%                | -                | 1.5x           |
| EXP Bonus  | 1-3%                | -                | 1.5x           |

### 3.2. Số lượng Sub-stat theo Rarity

| Rarity    | Initial Sub-stats | Max Sub-stats |
| :-------- | :---------------- | :------------ |
| Common    | 0                 | 0             |
| Uncommon  | 1                 | 1             |
| Rare      | 2                 | 2             |
| Epic      | 2                 | 3             |
| Legendary | 3                 | 4             |
| Mythic    | 4                 | 4 + Skill     |

### 3.3. Sub-stat Roll Quality

Khi roll sub-stat, có xác suất roll được giá trị cao/thấp:

| Roll Quality | Probability | Value Range |
| :----------- | :---------- | :---------- |
| Low Roll     | 40%         | 70-85%      |
| Mid Roll     | 35%         | 85-100%     |
| High Roll    | 20%         | 100-115%    |
| Perfect Roll | 5%          | 115-130%    |

---

## 4. Công thức tính Equipment Stat

### 4.1. Main Stat tại Level

$$MainStat_{level} = BaseStat \times RarityMult \times (1 + Level \times 0.02)$$

**Ví dụ:** Tier 5 Legendary Weapon Level 80
$$ATK = 1200 \times 1.0 \times (1 + 80 \times 0.02) = 1200 \times 2.6 = 3,120$$

### 4.2. Tổng Stats từ Equipment

$$TotalATK_{equip} = \sum MainATK_i + \sum SubATK_i$$

$$TotalATK_{final} = BaseATK \times (1 + \sum ATK\%_i) + TotalATK_{flat}$$

---

## 5. Upgrade System

### 5.1. Enhancement (Cường hóa)

Tăng level của trang bị.

| Level Range | Gold/Level | Scrap/Level | Success Rate |
| :---------- | :--------- | :---------- | :----------- |
| 1-20        | 100        | 5           | 100%         |
| 21-40       | 500        | 15          | 100%         |
| 41-60       | 2,000      | 40          | 90%          |
| 61-80       | 8,000      | 100         | 80%          |
| 81-100      | 30,000     | 250         | 70%          |
| 101-120     | 100,000    | 500         | 50%          |

### 5.2. Merge (Ghép)

3 món cùng loại + cùng rarity → 1 món rarity cao hơn

| Input Rarity | Output Rarity | Extra Cost              |
| :----------- | :------------ | :---------------------- |
| 3 Common     | 1 Uncommon    | 500 Gold                |
| 3 Uncommon   | 1 Rare        | 2,000 Gold              |
| 3 Rare       | 1 Epic        | 10,000 Gold             |
| 3 Epic       | 1 Legendary   | 50,000 Gold             |
| 3 Legendary  | 1 Mythic      | 500,000 Gold + 100 Gems |

### 5.3. Reforge (Tẩy luyện)

Re-roll tất cả sub-stats.

| Rarity    | Reforge Stone Cost | Gold Cost |
| :-------- | :----------------- | :-------- |
| Epic      | 1                  | 10,000    |
| Legendary | 3                  | 50,000    |
| Mythic    | 10                 | 200,000   |

---

## 6. Set Bonus System

### 6.1. Danh sách Set

| Set Name            | 2-Piece Bonus          | 4-Piece Bonus           |
| :------------------ | :--------------------- | :---------------------- |
| **Du côn**          | +5% ATK                | +10% CRIT Rate          |
| **Nồi đồng cối đá** | +10% Max HP            | +1% HP Regen/s          |
| **Tốc độ**          | +5% ASPD               | Every 3rd hit: +50% DMG |
| **Hút máu**         | +3% Lifesteal          | On kill: Heal 5% Max HP |
| **Độc hại**         | +10% Skill DMG         | 20% chance: Poison 3s   |
| **Phản đòn**        | +5% DEF                | Reflect 10% DMG taken   |
| **May mắn**         | +5% Gold bonus         | +5% Rare drop rate      |
| **Bá đạo**          | +5% ATK, +5% CRIT Rate | Ignore 15% enemy DEF    |

### 6.2. Set Activation Rules

- 2-Piece: Wear 2 items from same set
- 4-Piece: Wear 4 items from same set (stacks with 2-piece)
- Mixed sets: Can have 2+2 or 4 from single set

---

## 7. Equipment Score

### 7.1. Công thức tính điểm trang bị

$$Score = MainStatScore + \sum SubStatScore + SetBonus + RarityBonus$$

### 7.2. Scoring Table

| Factor    | Score Formula                                                      |
| :-------- | :----------------------------------------------------------------- |
| Main Stat | Main Stat × 1.0                                                    |
| Sub Stat  | Sub Stat Value × Weight                                            |
| Set Bonus | +500 per piece in set                                              |
| Rarity    | Common +0, Unc +100, Rare +300, Epic +600, Leg +1000, Mythic +1500 |
| Level     | +10 per level                                                      |

---

## 8. Bảng tổng hợp Full Set Endgame

### 8.1. Full Legendary Set Tier 10 Level 100

| Slot          | Main Stat                | Sub Stats (Perfect Roll)                           |
| :------------ | :----------------------- | :------------------------------------------------- |
| **Weapon**    | 312,000 ATK              | +15% ATK, +12% CRIT, +8% ASPD, +5% Skill DMG       |
| **Armor**     | 520,000 HP               | +10% HP, +8% DEF, +5% Dodge, +3% Lifesteal         |
| **Boots**     | +156% ASPD               | +10% ATK, +8% CRIT Rate, +5% Move Speed, +5% Dodge |
| **Accessory** | 70% CRIT + 400% CRIT DMG | +12% ATK, +5% ASPD, +5% Skill DMG, +8% Lifesteal   |

**Total Stats từ Equipment:**

- ATK: 312,000 + ~47% bonus
- HP: 520,000 + ~18% bonus
- ASPD: +156% (capped at 5.0)
- CRIT Rate: ~90% (capped at 100%)
- CRIT DMG: 400%+
- Additional: Lifesteal, Dodge, Skill DMG

---

## 9. Hướng dẫn cho đội phát triển

### 9.1. Cho lập trình viên

- Equipment ID format: `{slot}_{rarity}_{tier}_{unique_id}`
- Implement weighted random for sub-stat rolls
- Cache equipment stats, recalculate on equip/upgrade
- Lock mechanism để tránh bán/phân giải nhầm

### 9.2. Cho game designer

- Legendary drop rate nên khá thấp (~1%) để giữ giá trị
- Merge system là sink chính cho low-tier equipment
- Reforge chỉ available cho Epic+ để có end-game content
- Set bonus nên synergy với teammate abilities

### 9.3. Cho artist

- Equipment icon: 128x128 (inventory), 256x256 (popup)
- Rarity border: Glow effect tăng dần theo rarity
- Mythic equipment cần particle effect riêng
- Animation khi upgrade thành công/thất bại
