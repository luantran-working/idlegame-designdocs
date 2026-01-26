# Chỉ số đồng đội

Tài liệu này định nghĩa chi tiết các thông số kỹ thuật, scaling và bảng cân bằng cho 30 đồng đội trong game.

---

## 1. Cấu trúc dữ liệu đồng đội

### 1.1. Các thuộc tính chính

| Thuộc tính    | Ký hiệu        | Mô tả                            | Ví dụ           |
| :------------ | :------------- | :------------------------------- | :-------------- |
| **ID**        | `teammate_id`  | Mã định danh duy nhất            | "TM_COMMON_001" |
| **Tên**       | `name`         | Tên hiển thị                     | "Bé Tí bắn bi"  |
| **Phẩm chất** | `rarity`       | Common → Legendary               | "common"        |
| **Vai trò**   | `class`        | Tank/Warrior/Ranger/Mage/Support | "ranger"        |
| **Số sao**    | `star_rank`    | 1★ → 6★                          | 3               |
| **Cấp độ**    | `level`        | 1 → Max Level (theo rarity)      | 45              |
| **Base HP**   | `base_hp`      | Máu cơ bản tại Lv1, 1★           | 200             |
| **Base ATK**  | `base_atk`     | Tấn công cơ bản                  | 30              |
| **Base DEF**  | `base_def`     | Phòng thủ cơ bản                 | 10              |
| **ASPD**      | `attack_speed` | Tốc độ đánh cơ bản               | 1.0             |

### 1.2. Cấu trúc JSON mẫu

```json
{
  "teammate_id": "TM_COMMON_001",
  "name": "Bé Tí bắn bi",
  "rarity": "common",
  "class": "ranger",
  "star_rank": 3,
  "level": 20,
  "base_hp": 200,
  "base_atk": 30,
  "base_def": 10,
  "attack_speed": 1.0,
  "active_skill": {
    "id": "skill_ban_bi",
    "level": 10
  },
  "passive_skill": {
    "id": "passive_ham_choi",
    "tier": 3
  }
}
```

---

## 2. Phẩm chất và giới hạn

### 2.1. Bảng phẩm chất

| Rarity    | Màu sắc    | Max Level | Max Star | Base Stat Mult | Gacha Rate |
| :-------- | :--------- | :-------- | :------- | :------------- | :--------- |
| Common    | Trắng      | 20        | 5★       | 1.0x           | 60%        |
| Uncommon  | Xanh lá    | 40        | 5★       | 1.2x           | 25%        |
| Rare      | Xanh dương | 60        | 6★       | 1.5x           | 10%        |
| Epic      | Tím        | 80        | 6★       | 2.0x           | 4%         |
| Legendary | Cam        | 100       | 6★       | 3.0x           | 0.9%       |
| Mythic    | Đỏ         | 120       | 6★       | 5.0x           | 0.1%       |

### 2.2. Star Rank Multiplier

| Star Rank | Stats Mult | Passive Tier | Shards to Promote |
| :-------- | :--------- | :----------- | :---------------- |
| 1★        | 1.0x       | Tier 1       | 0                 |
| 2★        | 1.5x       | Tier 2       | 10 shards         |
| 3★        | 2.0x       | Tier 3       | 30 shards         |
| 4★        | 3.0x       | Tier 4       | 60 shards         |
| 5★        | 5.0x       | Tier 5       | 120 shards        |
| 6★        | 8.0x       | Tier 6       | 200 shards        |

---

## 3. Base Stats theo vai trò (Class)

### 3.1. Stats Distribution

| Class       | HP Weight | ATK Weight | DEF Weight | ASPD Base | Range  |
| :---------- | :-------- | :--------- | :--------- | :-------- | :----- |
| **Tank**    | 1.5x      | 0.8x       | 1.5x       | 0.8       | Melee  |
| **Warrior** | 1.2x      | 1.2x       | 1.0x       | 1.0       | Melee  |
| **Ranger**  | 0.8x      | 1.3x       | 0.6x       | 1.3       | Ranged |
| **Mage**    | 0.7x      | 1.5x       | 0.5x       | 0.9       | Ranged |
| **Support** | 1.0x      | 0.7x       | 0.8x       | 1.0       | Ranged |

### 3.2. Base Stats mẫu (Tại Lv1, 1★, Common)

| Class       | Base HP | Base ATK | Base DEF |
| :---------- | :------ | :------- | :------- |
| **Tank**    | 300     | 24       | 15       |
| **Warrior** | 240     | 36       | 10       |
| **Ranger**  | 160     | 39       | 6        |
| **Mage**    | 140     | 45       | 5        |
| **Support** | 200     | 21       | 8        |

---

## 4. Bảng Stats chi tiết 30 đồng đội

### 4.1. Nhóm Common (5 đồng đội)

| Tên             | Class   | HP (1★/5★) | ATK (1★/5★) | DEF (1★/5★) | ASPD |
| :-------------- | :------ | :--------- | :---------- | :---------- | :--- |
| Bé Tí bắn bi    | Ranger  | 160/800    | 39/195      | 6/30        | 1.3  |
| Chú Tư xe thồ   | Tank    | 300/1,500  | 24/120      | 15/75       | 0.8  |
| Cô Bảy quét rác | Support | 200/1,000  | 21/105      | 8/40        | 1.0  |
| Cậu Vàng        | Warrior | 240/1,200  | 36/180      | 10/50       | 1.0  |
| Bác bảo vệ      | Tank    | 320/1,600  | 22/110      | 18/90       | 0.7  |

### 4.2. Nhóm Uncommon (6 đồng đội)

| Tên            | Class   | HP (1★/5★) | ATK (1★/5★) | DEF (1★/5★) | ASPD |
| :------------- | :------ | :--------- | :---------- | :---------- | :--- |
| Chị tạp vụ     | Warrior | 290/1,740  | 43/258      | 12/72       | 1.1  |
| Anh Grab Food  | Ranger  | 192/1,152  | 47/282      | 7/42        | 1.4  |
| Thằng Tèo net  | Mage    | 168/1,008  | 54/324      | 6/36        | 0.9  |
| Cô hàng xóm    | Support | 240/1,440  | 25/150      | 10/60       | 1.0  |
| Ông chú câu cá | Ranger  | 204/1,224  | 45/270      | 8/48        | 1.2  |
| Bà bán xôi     | Support | 252/1,512  | 23/138      | 11/66       | 0.9  |

### 4.3. Nhóm Rare (8 đồng đội)

| Tên              | Class   | HP (1★/6★) | ATK (1★/6★) | DEF (1★/6★) | ASPD |
| :--------------- | :------ | :--------- | :---------- | :---------- | :--- |
| Chú Ba xe ôm     | Tank    | 450/3,600  | 36/288      | 23/184      | 0.8  |
| Cô Tư bán nước   | Support | 300/2,400  | 32/256      | 12/96       | 1.0  |
| Anh Bảy thợ điện | Mage    | 210/1,680  | 68/544      | 8/64        | 1.0  |
| Chị Mười bán cá  | Warrior | 360/2,880  | 54/432      | 15/120      | 1.2  |
| Ninja Lead       | Tank    | 420/3,360  | 42/336      | 20/160      | 0.9  |
| Thầy bói mù      | Mage    | 225/1,800  | 63/504      | 9/72        | 0.85 |
| Anh shipper      | Ranger  | 255/2,040  | 51/408      | 11/88       | 1.35 |
| Chị đại gym      | Warrior | 390/3,120  | 48/384      | 18/144      | 1.0  |

### 4.4. Nhóm Epic (7 đồng đội)

| Tên                 | Class   | HP (1★/6★) | ATK (1★/6★) | DEF (1★/6★) | ASPD |
| :------------------ | :------ | :--------- | :---------- | :---------- | :--- |
| Tổ trưởng dân phố   | Support | 400/3,200  | 42/336      | 16/128      | 1.0  |
| Thợ cắt tóc         | Warrior | 480/3,840  | 72/576      | 20/160      | 1.4  |
| Bà chủ trọ          | Tank    | 600/4,800  | 48/384      | 30/240      | 0.75 |
| Youtuber ẩm thực    | Tank    | 560/4,480  | 44/352      | 28/224      | 0.8  |
| Rapper xóm          | Mage    | 280/2,240  | 84/672      | 12/96       | 1.0  |
| Hot girl livestream | Support | 360/2,880  | 52/416      | 14/112      | 1.1  |
| Thầy giáo thể dục   | Warrior | 520/4,160  | 64/512      | 24/192      | 1.1  |

### 4.5. Nhóm Legendary (4 đồng đội)

| Tên            | Class   | HP (1★/6★) | ATK (1★/6★) | DEF (1★/6★) | ASPD |
| :------------- | :------ | :--------- | :---------- | :---------- | :--- |
| Vua cờ bạc     | Ranger  | 480/3,840  | 90/720      | 18/144      | 1.3  |
| Đại ca khu phố | Warrior | 720/5,760  | 81/648      | 36/288      | 0.95 |
| Bà trùm đề     | Mage    | 420/3,360  | 105/840     | 15/120      | 0.9  |
| Tiến sĩ giấy   | Support | 540/4,320  | 63/504      | 21/168      | 1.0  |

---

## 5. Công thức tính Stats cuối

### 5.1. Stats tại Level và Star

$$Stat_{final} = BaseStat \times RarityMult \times StarMult \times LevelMult$$

Trong đó:

- **LevelMult** = $1 + (Level - 1) \times 0.03$

### 5.2. Ví dụ tính toán

**Vua cờ bạc 5★ Level 80:**

- Base ATK: 90
- Rarity Mult (Legendary): 3.0x
- Star Mult (5★): 5.0x
- Level Mult: $1 + 79 \times 0.03 = 3.37$

$$ATK = 90 \times 3.0 \times 5.0 \times 3.37 = 4,549.5 ≈ 4,550$$

### 5.3. Bảng tham khảo nhanh

| Đồng đội          | 1★ Lv1 ATK | 5★ Lv Max ATK | 6★ Lv Max ATK |
| :---------------- | :--------- | :------------ | :------------ |
| Bé Tí (Common)    | 39         | 659           | -             |
| Cô hàng xóm (Unc) | 30         | 760           | -             |
| Ninja Lead (Rare) | 63         | 2,014         | 3,222         |
| Rapper xóm (Epic) | 168        | 5,376         | 8,602         |
| Vua cờ bạc (Leg)  | 270        | 9,112         | 14,580        |

---

## 6. Chi phí nâng cấp đồng đội

### 6.1. Level Up Cost

| Level Range | Gold/Level | Fodder Shards |
| :---------- | :--------- | :------------ |
| 1-20        | 500        | 0             |
| 21-40       | 2,000      | 5             |
| 41-60       | 8,000      | 10            |
| 61-80       | 30,000     | 20            |
| 81-100      | 100,000    | 40            |
| 101-120     | 300,000    | 80            |

### 6.2. Star Promotion Cost

| Star Upgrade | Same-Char Shards | Gold      | Rare Material |
| :----------- | :--------------- | :-------- | :------------ |
| 1★ → 2★      | 10               | 5,000     | -             |
| 2★ → 3★      | 30               | 20,000    | -             |
| 3★ → 4★      | 60               | 100,000   | 1 Star Stone  |
| 4★ → 5★      | 120              | 500,000   | 3 Star Stone  |
| 5★ → 6★      | 200              | 2,000,000 | 5 Star Stone  |

---

## 7. Affinity System (Duyên phận)

### 7.1. Các bộ duyên

| Bộ duyên           | Thành viên                               | Bonus 2        | Bonus 3-4     | Bonus 5           |
| :----------------- | :--------------------------------------- | :------------- | :------------ | :---------------- |
| Giao thông vận tải | Chú Ba, Ninja Lead, Chú Tư, Anh Grab     | +10% Speed     | +15% Dodge    | +5% HP Regen      |
| Chợ tin đồn        | Cô hàng xóm, Bà bán xôi, Cô Tư, Chị Mười | +20% CC Resist | -             | -15% DEF địch     |
| Ban quản lý        | Bác bảo vệ, Tổ trưởng, Bà chủ trọ        | +20% HP        | +20% Gold     | -                 |
| Gen Z              | Tèo net, Hot girl, Rapper, Youtuber      | +10% CRIT      | -             | +20% ASPD on Crit |
| Thế giới ngầm      | Đại ca, Bà trùm, Vua cờ bạc              | +30% ATK       | +50% True DMG | -                 |

### 7.2. Activation Rules

- Chỉ cần sở hữu nhân vật (không cần deploy)
- Bonus được áp dụng cho toàn team
- Có thể kích hoạt nhiều bộ duyên cùng lúc

---

## 8. Team Composition Guidelines

### 8.1. Team Template chuẩn (5 slot)

| Position | Recommended Class | Priority Stats |
| :------- | :---------------- | :------------- |
| Slot 1   | Tank              | HP, DEF        |
| Slot 2   | Warrior           | ATK, HP        |
| Slot 3   | Ranger/Mage       | ATK, ASPD/CRIT |
| Slot 4   | Ranger/Mage       | ATK, CRIT DMG  |
| Slot 5   | Support           | HP, CDR        |

### 8.2. Synergy Examples

**Team "Full DPS":**

- Thợ cắt tóc (Warrior) + Chị Mười (Warrior) + Rapper (Mage) + Vua cờ bạc (Ranger) + Tổ trưởng (Support)
- Focus: Maximum damage output

**Team "Unkillable":**

- Chú Ba (Tank) + Bà chủ trọ (Tank) + Youtuber (Tank) + Bà bán xôi (Support) + Hot girl (Support)
- Focus: Survival and sustain

---

## 9. Hướng dẫn cho đội phát triển

### 9.1. Cho lập trình viên

- Teammate data nên được load từ config/database
- Implement AI behavior riêng cho từng class
- Cache calculated stats, update on level/star change
- Shard system cần validate khi promote

### 9.2. Cho game designer

- Legendary teammates nên có unique mechanics
- Affinity bonus không nên quá mạnh (10-20% là hợp lý)
- F2P nên có khả năng collect đủ 1 Legendary sau 1 tháng
- Balance giữa các class cần test thoroughly

### 9.3. Cho artist

- Mỗi teammate cần: Idle, Walk, Attack, Skill, Hit, Death
- Star rank thể hiện qua border và particle
- Legendary và Mythic cần animation đặc biệt
- Expression phải match với personality
