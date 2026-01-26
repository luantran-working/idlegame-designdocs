# Chỉ số kỹ năng đồng đội

Tài liệu này định nghĩa chi tiết thông số kỹ thuật, công thức tính toán và bảng cân bằng cho 60 kỹ năng của 30 đồng đội (mỗi đồng đội có 1 Active + 1 Passive).

---

## 1. Cấu trúc kỹ năng đồng đội

### 1.1. Phân loại kỹ năng

Mỗi đồng đội sở hữu 2 loại kỹ năng:

| Loại kỹ năng      | Cách kích hoạt             | Scaling theo | Ghi chú                       |
| :---------------- | :------------------------- | :----------- | :---------------------------- |
| **Active Skill**  | Energy bar đầy (100 điểm)  | Skill Level  | Mỗi lần bị đánh +10 Energy    |
| **Passive Skill** | Luôn kích hoạt / Điều kiện | Star Rank    | Tăng theo số sao của đồng đội |

### 1.2. Hệ thống Energy (Năng lượng)

$$Energy_{gain} = DamageReceived \times 0.01 + BaseEnergyRegen$$

- **BaseEnergyRegen:** 2 Energy/giây
- **Energy khi bị đánh:** +1% damage nhận vào chuyển thành Energy (tối đa +20/hit)
- **Energy max:** 100

**Thời gian trung bình để full energy:**
$$Time_{fullEnergy} = \frac{100}{BaseEnergyRegen} = 50 \text{ giây}$$
(Nhanh hơn nếu nhận damage)

---

## 2. Bảng scaling theo phẩm chất

### 2.1. Hệ số base theo Rarity

| Phẩm chất     | Active Scaling/Lv | Passive Scaling/Star | Base Stats Mult |
| :------------ | :---------------- | :------------------- | :-------------- |
| **Common**    | +5% effect        | +0.5% stat           | 1.0x            |
| **Uncommon**  | +8% effect        | +0.8% stat           | 1.2x            |
| **Rare**      | +10% effect       | +1.0% stat           | 1.5x            |
| **Epic**      | +15% effect       | +1.5% stat           | 2.0x            |
| **Legendary** | +25% effect       | +2.5% stat           | 3.0x            |

### 2.2. Công thức tính giá trị kỹ năng

**Active Skill:**
$$Value_{active} = BaseValue \times (1 + ScalingPerLv \times (Level - 1))$$

**Passive Skill:**
$$Value_{passive} = BaseValue \times (1 + ScalingPerStar \times (StarRank - 1))$$

---

## 3. Chi tiết kỹ năng theo phẩm chất

### 3.1. Nhóm Bình dân (Common) - 5 đồng đội

#### Bé Tí bắn bi

| Kỹ năng      | Loại    | Giá trị Lv1/1★                  | Scaling    | Giá trị Max (Lv20/5★) |
| :----------- | :------ | :------------------------------ | :--------- | :-------------------- |
| **Bắn bi**   | Active  | 120% DMG                        | +5% DMG/Lv | 225% DMG              |
| **Ham chơi** | Passive | +10% Move Speed khi không chiến | +0.5%/★    | +12% Move Speed       |

**Cơ chế Active:** Single target, projectile bay thẳng

#### Chú Tư xe thồ

| Kỹ năng      | Loại    | Giá trị Lv1/1★ | Scaling     | Giá trị Max (Lv20/5★)  |
| :----------- | :------ | :------------- | :---------- | :--------------------- |
| **Chặn đầu** | Active  | Block 1 hit    | -0.1s CD/Lv | Block 1 hit (CD 8s→6s) |
| **Thồ hàng** | Passive | +10 Inventory  | +1 slot/★   | +14 Inventory          |

**Cơ chế Active:** Tạo shield hấp thụ 1 đòn đánh cho nhân vật chính, CD 10s base

#### Cô Bảy quét rác

| Kỹ năng       | Loại    | Giá trị Lv1/1★   | Scaling     | Giá trị Max (Lv20/5★)  |
| :------------ | :------ | :--------------- | :---------- | :--------------------- |
| **Quét sạch** | Active  | Cleanse 1 debuff | +5% Heal/Lv | Cleanse + 100% HP heal |
| **Cần lao**   | Passive | +5% Gold drop    | +0.5%/★     | +7% Gold drop          |

#### Cậu Vàng

| Kỹ năng      | Loại    | Giá trị Lv1/1★      | Scaling    | Giá trị Max (Lv20/5★) |
| :----------- | :------ | :------------------ | :--------- | :-------------------- |
| **Cắn trộm** | Active  | 150% DMG + 30% Slow | +5% DMG/Lv | 255% DMG + 30% Slow   |
| **Đánh hơi** | Passive | +10% Chest rate     | +1%/★      | +14% Chest rate       |

#### Bác bảo vệ

| Kỹ năng     | Loại    | Giá trị Lv1/1★        | Scaling  | Giá trị Max (Lv20/5★) |
| :---------- | :------ | :-------------------- | :------- | :-------------------- |
| **Đèn pin** | Active  | -20% Accuracy địch 3s | +0.2s/Lv | -20% Accuracy 6.8s    |
| **Gác đêm** | Passive | +10% Vision tối       | +2%/★    | +18% Vision           |

---

### 3.2. Nhóm Tập sự (Uncommon) - 6 đồng đội

#### Chị tạp vụ

| Kỹ năng      | Loại    | Giá trị Lv1/1★   | Scaling    | Giá trị Max (Lv40/5★)       |
| :----------- | :------ | :--------------- | :--------- | :-------------------------- |
| **Lau sàn**  | Active  | Dash + 1.5s Stun | +8% DMG/Lv | Dash + 1.5s Stun + 420% DMG |
| **Sàn trơn** | Passive | 10% Slip chance  | +1%/★      | 14% Slip (1s Stun)          |

#### Anh Grab Food

| Kỹ năng       | Loại    | Giá trị Lv1/1★        | Scaling    | Giá trị Max (Lv40/5★) |
| :------------ | :------ | :-------------------- | :--------- | :-------------------- |
| **Giao hàng** | Active  | 180% DMG AOE          | +8% DMG/Lv | 492% DMG AOE          |
| **Đúng giờ**  | Passive | +20% Speed post-skill | +2%/★      | +28% Speed            |

#### Thằng Tèo net

| Kỹ năng      | Loại    | Giá trị Lv1/1★ | Scaling  | Giá trị Max (Lv40/5★) |
| :----------- | :------ | :------------- | :------- | :-------------------- |
| **Rớt mạng** | Active  | Freeze 2s      | +0.2s/Lv | Freeze 9.8s           |
| **Lag**      | Passive | Xác chặn 5s    | +0.5s/★  | Xác chặn 7s           |

**Giới hạn Freeze:** Cap 5s để không lock boss vĩnh viễn

#### Cô hàng xóm

| Kỹ năng         | Loại    | Giá trị Lv1/1★ | Scaling | Giá trị Max (Lv40/5★) |
| :-------------- | :------ | :------------- | :------ | :-------------------- |
| **Buôn dưa lê** | Active  | -20% DEF địch  | +1%/Lv  | -59% DEF địch         |
| **Hóng hớt**    | Passive | +2% HP /5s     | +0.2%/★ | +2.8% HP /5s          |

#### Ông chú câu cá

| Kỹ năng       | Loại    | Giá trị Lv1/1★        | Scaling    | Giá trị Max (Lv40/5★) |
| :------------ | :------ | :-------------------- | :--------- | :-------------------- |
| **Quăng cần** | Active  | Pull + 120% DMG       | +8% DMG/Lv | Pull + 432% DMG       |
| **Kiên nhẫn** | Passive | Đứng im 3s → +20% DMG | +2%/★      | +28% DMG              |

#### Bà bán xôi

| Kỹ năng      | Loại    | Giá trị Lv1/1★   | Scaling | Giá trị Max (Lv40/5★) |
| :----------- | :------ | :--------------- | :------ | :-------------------- |
| **Xôi gà**   | Active  | Heal 15% HP ally | +1%/Lv  | Heal 54% HP ally      |
| **Sáng sớm** | Passive | +10% Max HP team | +1%/★   | +14% Max HP team      |

---

### 3.3. Nhóm Chuyên nghiệp (Rare) - 8 đồng đội

#### Chú Ba xe ôm

| Kỹ năng       | Loại    | Giá trị Lv1/1★             | Scaling     | Giá trị Max (Lv60/5★) |
| :------------ | :------ | :------------------------- | :---------- | :-------------------- |
| **Đón khách** | Active  | 200% DMG + 2s Stun + Taunt | +10%/Lv     | 790% + 2s Stun        |
| **Vượt đèn**  | Passive | Immune Slow                | +5% Speed/★ | Immune + 20% Speed    |

#### Cô Tư bán nước

| Kỹ năng      | Loại    | Giá trị Lv1/1★             | Scaling      | Giá trị Max (Lv60/5★)  |
| :----------- | :------ | :------------------------- | :----------- | :--------------------- |
| **Trà đá**   | Active  | +50 Energy + 15% ASPD team | +2 Energy/Lv | +168 Energy + 15% ASPD |
| **Chém gió** | Passive | +15% ASPD aura             | +1%/★        | +19% ASPD aura         |

#### Anh Bảy thợ điện

| Kỹ năng       | Loại    | Giá trị Lv1/1★                 | Scaling | Giá trị Max (Lv60/5★) |
| :------------ | :------ | :----------------------------- | :------ | :-------------------- |
| **Đấu tắt**   | Active  | Chain 3 mục tiêu 180% DMG      | +10%/Lv | Chain 3, 770% DMG     |
| **Tích điện** | Passive | Đòn 3 +50% DMG + 0.5s Paralyze | +5%/★   | +70% DMG bonus        |

#### Chị Mười bán cá

| Kỹ năng     | Loại    | Giá trị Lv1/1★       | Scaling | Giá trị Max (Lv60/5★) |
| :---------- | :------ | :------------------- | :------ | :-------------------- |
| **Cá đông** | Active  | 300% DMG + 100% Crit | +15%/Lv | 1185% DMG + 100% Crit |
| **Mồm mép** | Passive | Reflect 20% DMG      | +2%/★   | Reflect 28% DMG       |

#### Ninja Lead

| Kỹ năng     | Loại    | Giá trị Lv1/1★ | Scaling  | Giá trị Max (Lv60/5★) |
| :---------- | :------ | :------------- | :------- | :-------------------- |
| **Xi nhan** | Active  | +50% Dodge 5s  | +0.5s/Lv | +50% Dodge 34.5s      |
| **Áo nắng** | Passive | -20% Magic DMG | +2%/★    | -28% Magic DMG        |

**Giới hạn Dodge buff:** Cap 80% để tránh bất tử

#### Thầy bói mù

| Kỹ năng      | Loại    | Giá trị Lv1/1★                      | Scaling | Giá trị Max (Lv60/5★) |
| :----------- | :------ | :---------------------------------- | :------ | :-------------------- |
| **Phán xét** | Active  | 80% → 500% DMG, 20% → Heal địch 20% | +10%/Lv | 80% → 1090% DMG       |
| **Thiên cơ** | Passive | +5% Crit Rate team                  | +0.5%/★ | +7% Crit Rate         |

**Cơ chế Random:** Roll RNG khi cast, không thể control

#### Anh shipper

| Kỹ năng      | Loại    | Giá trị Lv1/1★   | Scaling | Giá trị Max (Lv60/5★) |
| :----------- | :------ | :--------------- | :------ | :-------------------- |
| **Mưa hàng** | Active  | AOE 150%/s x 3s  | +12%/Lv | AOE 858%/s x 3s       |
| **Freeship** | Passive | -10% CD ally gần | +1%/★   | -14% CD               |

#### Chị đại gym

| Kỹ năng     | Loại    | Giá trị Lv1/1★         | Scaling | Giá trị Max (Lv60/5★) |
| :---------- | :------ | :--------------------- | :------ | :-------------------- |
| **Squat**   | Active  | AOE 200% + 40% Slow 3s | +10%/Lv | AOE 790% + 40% Slow   |
| **Protein** | Passive | +1% HP/s               | +0.2%/★ | +1.8% HP/s            |

---

### 3.4. Nhóm Tinh anh (Epic) - 7 đồng đội

#### Tổ trưởng dân phố

| Kỹ năng        | Loại    | Giá trị Lv1/1★     | Scaling | Giá trị Max (Lv80/5★) |
| :------------- | :------ | :----------------- | :------ | :-------------------- |
| **Loa phường** | Active  | +30% ATK team 10s  | +2%/Lv  | +188% ATK team 10s    |
| **Uy tín**     | Passive | Common get +20% HP | +2%/★   | +28% HP for Common    |

#### Thợ cắt tóc

| Kỹ năng     | Loại    | Giá trị Lv1/1★         | Scaling | Giá trị Max (Lv80/5★) |
| :---------- | :------ | :--------------------- | :------ | :-------------------- |
| **Múa kéo** | Active  | 5 hit x 80% + Bleed 3s | +15%/Lv | 5 hit x 1265% + Bleed |
| **Tút tát** | Passive | Kill → +30% ASPD 5s    | +3%/★   | Kill → +42% ASPD      |

#### Bà chủ trọ

| Kỹ năng       | Loại    | Giá trị Lv1/1★              | Scaling | Giá trị Max (Lv80/5★)  |
| :------------ | :------ | :-------------------------- | :------ | :--------------------- |
| **Đòi tiền**  | Active  | Drain 10% HP → Shield       | +2%/Lv  | Drain 168% HP → Shield |
| **Luật rừng** | Passive | HP &lt;50% → -15% DMG taken | +2%/★   | -23% DMG taken         |

#### Youtuber ẩm thực

| Kỹ năng     | Loại    | Giá trị Lv1/1★                | Scaling  | Giá trị Max (Lv80/5★)  |
| :---------- | :------ | :---------------------------- | :------- | :--------------------- |
| **Mukbang** | Active  | Heal 50% HP + 20% DEF 5s      | +5%/Lv   | Heal 445% HP + 20% DEF |
| **Mỡ thừa** | Passive | Kill → +10 Max HP (permanent) | +10 HP/★ | +50 HP/kill            |

**Giới hạn stack:** Tối đa 1000 stacks (10,000 bonus HP)

#### Rapper xóm

| Kỹ năng      | Loại    | Giá trị Lv1/1★        | Scaling | Giá trị Max (Lv80/5★) |
| :----------- | :------ | :-------------------- | :------ | :-------------------- |
| **Diss**     | Active  | AOE 250% + Silence 3s | +15%/Lv | AOE 1435% + Silence   |
| **Vần điệu** | Passive | +50% DMG vs Debuffed  | +5%/★   | +70% DMG              |

#### Hot girl livestream

| Kỹ năng     | Loại    | Giá trị Lv1/1★                | Scaling  | Giá trị Max (Lv80/5★) |
| :---------- | :------ | :---------------------------- | :------- | :-------------------- |
| **Thả tim** | Active  | Ally &lt;10% HP → Immortal 2s | +0.5s/Lv | Immortal 41.5s        |
| **Donate**  | Passive | 50% drop HP/Mana orb /10s     | +1%/★    | 54% drop rate         |

**Giới hạn Immortal:** Cap 5s để không break game

#### Thầy giáo thể dục

| Kỹ năng     | Loại    | Giá trị Lv1/1★                    | Scaling   | Giá trị Max (Lv80/5★)  |
| :---------- | :------ | :-------------------------------- | :-------- | :--------------------- |
| **Hít đất** | Active  | Kill → +2 ATK (permanent, max 10) | +2 ATK/Lv | +160 ATK/kill (max 10) |
| **Kỷ luật** | Passive | +10% DEF aura                     | +1%/★     | +14% DEF aura          |

---

### 3.5. Nhóm Huyền thoại (Legendary) - 4 đồng đội

#### Vua cờ bạc

| Kỹ năng      | Loại    | Giá trị Lv1/1★                                          | Scaling | Giá trị Max (Lv100/5★) |
| :----------- | :------ | :------------------------------------------------------ | :------ | :--------------------- |
| **Thần bài** | Active  | 3 lá bài: Xanh (50 Mana), Đỏ (400% DMG), Vàng (2s Stun) | +25%/Lv | Đỏ → 2875% DMG         |
| **Gian lận** | Passive | 20% x2 DMG auto-attack                                  | +2%/★   | 28% x2 DMG             |

#### Đại ca khu phố

| Kỹ năng    | Loại    | Giá trị Lv1/1★                      | Scaling | Giá trị Max (Lv100/5★) |
| :--------- | :------ | :---------------------------------- | :------ | :--------------------- |
| **Gọi đệ** | Active  | Summon 2 minions (30% player stats) | +5%/Lv  | 2 minions (525% stats) |
| **Bảo kê** | Passive | Redirect 30% DMG to minions         | +2%/★   | Redirect 38% DMG       |

**Cơ chế Minion:**

- Minion có HP = 50% Đại ca HP
- Minion có ATK = 30% Đại ca ATK (scaling)
- Minion tồn tại 20s hoặc đến khi chết

#### Bà trùm đề

| Kỹ năng     | Loại    | Giá trị Lv1/1★                        | Scaling | Giá trị Max (Lv100/5★)   |
| :---------- | :------ | :------------------------------------ | :------ | :----------------------- |
| **Sổ tử**   | Active  | After 5s: True DMG = 50% HP đã mất    | +5%/Lv  | 545% lost HP as True DMG |
| **Nuôi lô** | Passive | Skill DMG +10% /use (reset mỗi stage) | +2%/★   | +18% /use                |

**Công thức Sổ tử:**
$$TrueDamage = EnemyMaxHP \times LostHPPercent \times SkillMultiplier$$

#### Tiến sĩ giấy

| Kỹ năng       | Loại    | Giá trị Lv1/1★                  | Scaling   | Giá trị Max (Lv100/5★)        |
| :------------ | :------ | :------------------------------ | :-------- | :---------------------------- |
| **Hack**      | Active  | Reset all team CD (own CD: 60s) | -2s CD/Lv | Reset CD (own CD: -138s → 0s) |
| **Lý thuyết** | Passive | +20% EXP team                   | +2%/★     | +28% EXP team                 |

**Ghi chú:** Cooldown của skill này không thể về 0, minimum 30s

---

## 4. Bảng tổng hợp DPS đồng đội (Lv Max, 5★)

| Đồng đội             | Active DPS Potential | Passive Value  | Tier List |
| :------------------- | :------------------- | :------------- | :-------- |
| **Chị Mười bán cá**  | 1185% + 100% Crit    | Reflect 28%    | S         |
| **Rapper xóm**       | 1435% AOE + Silence  | +70% vs Debuff | S         |
| **Thợ cắt tóc**      | 6325% (5 hit)        | +42% ASPD      | S         |
| **Vua cờ bạc**       | 2875% (RNG Đỏ)       | 28% x2 Auto    | A+        |
| **Anh Bảy thợ điện** | 770% x3 Chain        | +70% hit 3     | A         |
| **Bà trùm đề**       | % HP True DMG        | Stack +18%     | A         |

---

## 5. Hướng dẫn cho đội phát triển

### 5.1. Cho lập trình viên

- Implement Energy system với tick rate 0.1s
- Mỗi đồng đội cần có state machine riêng cho AI behavior
- Passive aura cần có range check (thường 5 đơn vị)
- Minion system cần handle despawn khi chủ chết

### 5.2. Cho game designer

- Common đồng đội nên là "training wheels" - dễ hiểu, hiệu quả vừa phải
- Legendary đồng đội nên có cơ chế unique (minions, RNG effects, % HP damage)
- Passive của Support class nên có giá trị cao hơn DPS class
- Energy gain từ damage nên giảm khi đánh boss (tránh spam skill)

### 5.3. Tier list priority (cho người chơi mới)

| Giai đoạn      | Nên ưu tiên              | Lý do                 |
| :------------- | :----------------------- | :-------------------- |
| **Early game** | Bà bán xôi, Cô hàng xóm  | Heal + sustainability |
| **Mid game**   | Chú Ba xe ôm, Chị Mười   | Tank + DPS            |
| **Late game**  | Tiến sĩ giấy, Rapper xóm | Utility + AOE         |
| **Endgame**    | Vua cờ bạc, Bà trùm đề   | High risk high reward |
