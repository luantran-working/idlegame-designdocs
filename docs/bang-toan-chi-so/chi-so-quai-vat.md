# Chỉ số quái vật

Tài liệu này định nghĩa chi tiết các thông số kỹ thuật, công thức scaling và bảng cân bằng cho 48 loại quái thường và 4 Boss trong game.

---

## 1. Cấu trúc dữ liệu quái vật

### 1.1. Các thuộc tính chính

Mỗi quái vật được định nghĩa bởi các thuộc tính sau:

| Thuộc tính           | Ký hiệu        | Mô tả                               | Ví dụ                   |
| :------------------- | :------------- | :---------------------------------- | :---------------------- |
| **ID quái**          | `monster_id`   | Mã định danh duy nhất               | "ENM_C1_01"             |
| **Tên**              | `name`         | Tên hiển thị trong game             | "Bà hàng xóm đa chuyện" |
| **Chương**           | `chapter`      | Thuộc chương nào (1-4)              | 1                       |
| **Loại**             | `type`         | Thường/Elite/Boss                   | "normal"                |
| **HP cơ bản**        | `base_hp`      | Máu tại Stage 1, Wave 1             | 100                     |
| **ATK cơ bản**       | `base_atk`     | Sát thương tại Stage 1, Wave 1      | 10                      |
| **DEF cơ bản**       | `base_def`     | Giáp cơ bản                         | 0                       |
| **Tốc độ đánh**      | `attack_speed` | Số đòn/giây                         | 1.0                     |
| **Tốc độ di chuyển** | `move_speed`   | Đơn vị/giây                         | 2.0                     |
| **EXP thưởng**       | `exp_reward`   | Kinh nghiệm khi bị tiêu diệt        | 10                      |
| **Gold thưởng**      | `gold_reward`  | Vàng rơi khi chết                   | 5                       |
| **Kỹ năng**          | `skills`       | Danh sách kỹ năng đặc biệt (nếu có) | []                      |

### 1.2. Cấu trúc JSON mẫu

```json
{
  "monster_id": "ENM_C1_01",
  "name": "Bà hàng xóm đa chuyện",
  "chapter": 1,
  "type": "normal",
  "base_hp": 100,
  "base_atk": 10,
  "base_def": 0,
  "attack_speed": 1.0,
  "move_speed": 2.0,
  "exp_reward": 10,
  "gold_reward": 5,
  "skills": ["gossip_debuff"]
}
```

---

## 2. Công thức Scaling quái vật

### 2.1. Scaling theo Stage (Chính)

Quái vật mạnh lên theo hàm mũ qua mỗi Stage để tạo "HP Wall":

$$HP_{monster}(Stage) = BaseHP \times (HPMultiplier)^{Stage-1}$$

$$ATK_{monster}(Stage) = BaseATK \times (ATKMultiplier)^{Stage-1}$$

**Tham số mặc định:**

- **HPMultiplier:** 1.20 (tăng 20% HP mỗi stage)
- **ATKMultiplier:** 1.15 (tăng 15% ATK mỗi stage - chậm hơn để tránh one-shot)

### 2.2. Scaling theo Wave (Phụ)

Trong mỗi Stage có 10 Wave, quái ở Wave sau mạnh hơn chút:

$$Stat_{wave} = Stat_{stage} \times (1 + WaveIndex \times 0.05)$$

**Ví dụ:** Wave 5 sẽ có stats = Stage stats × 1.25

### 2.3. Scaling theo Chapter

Mỗi Chapter mới bắt đầu với quái mạnh hơn đáng kể:

$$BaseStat_{chapter} = BaseStat_{ch1} \times (ChapterMultiplier)^{Chapter-1}$$

**ChapterMultiplier:** 2.0 (gấp đôi mỗi chapter)

### 2.4. Công thức tổng hợp

$$FinalHP = BaseHP_{ch} \times (HPMult)^{Stage-1} \times (1 + Wave \times 0.05) \times TypeMult$$

| Type       | HP Multiplier | ATK Multiplier | Ghi chú                |
| :--------- | :------------ | :------------- | :--------------------- |
| **Normal** | 1.0x          | 1.0x           | Quái thường            |
| **Elite**  | 3.0x          | 1.5x           | Quái tinh anh (Wave 5) |
| **Boss**   | 10.0x         | 2.0x           | Boss (Wave 10)         |

---

## 3. Bảng chi tiết quái theo chương

### 3.1. Chương 1: Ngõ nhỏ & Vỉa hè (12 quái + 1 Boss)

| ID        | Tên quái              | Base HP | Base ATK | ASPD | Kỹ năng đặc biệt           |
| :-------- | :-------------------- | :------ | :------- | :--- | :------------------------- |
| ENM_C1_01 | Bà hàng xóm đa chuyện | 80      | 8        | 0.8  | Gossip: -10% ATK player 3s |
| ENM_C1_02 | Thanh niên xăm trổ    | 120     | 15       | 1.2  | Intimidate: Fear 1s        |
| ENM_C1_03 | Bác xe ôm ngủ gật     | 100     | 10       | 0.6  | Ngủ gật: 30% miss attack   |
| ENM_C1_04 | Chị bán rau chặt chém | 90      | 12       | 1.0  | Throw Vegetable: Ranged    |
| ENM_C1_05 | Anh thợ điện          | 110     | 18       | 0.9  | Electric Shock: Stun 0.5s  |
| ENM_C1_06 | Cô gái bán hoa rong   | 70      | 6        | 0.7  | Slow (bicycle blocking)    |
| ENM_C1_07 | Thằng bé bán vé số    | 50      | 5        | 1.5  | Dodge +20%                 |
| ENM_C1_08 | Ông chú say rượu      | 130     | 20       | 0.5  | 30% x2 DMG khi hit         |
| ENM_C1_09 | Bà ghi lô đề          | 85      | 9        | 0.8  | +15% Gold drop             |
| ENM_C1_10 | Thanh niên đa cấp     | 95      | 11       | 1.1  | Recruit: +1 ally quái      |
| ENM_C1_11 | Shipper vội vã        | 75      | 8        | 1.8  | High speed, low HP         |
| ENM_C1_12 | Bảo vệ ngủ gật        | 140     | 12       | 0.4  | High HP, slow attack       |

**BOSS C1: Tổ trưởng dân phố**

| Thuộc tính           | Giá trị                                   |
| :------------------- | :---------------------------------------- |
| **Base HP**          | 1,000                                     |
| **Base ATK**         | 25                                        |
| **ASPD**             | 1.0                                       |
| **Skill 1**          | Loa Phường: AOE -20% ATK team 5s (CD 10s) |
| **Skill 2**          | Quát Tháo: Stun single target 2s (CD 15s) |
| **Skill 3 (Enrage)** | HP &lt;30%: +50% ATK, +30% ASPD           |
| **EXP Reward**       | 500                                       |
| **Gold Reward**      | 200                                       |

---

### 3.2. Chương 2: Khu Chợ & Bến Xe (12 quái + 1 Boss)

| ID        | Tên quái              | Base HP | Base ATK | ASPD | Kỹ năng đặc biệt            |
| :-------- | :-------------------- | :------ | :------- | :--- | :-------------------------- |
| ENM_C2_01 | Móc túi chuyên nghiệp | 80      | 12       | 1.4  | Steal: -5% Gold /hit        |
| ENM_C2_02 | Phe vé chợ đen        | 100     | 10       | 1.0  | Inflate: Tăng giá item 10%  |
| ENM_C2_03 | Bà bán thịt heo       | 180     | 25       | 0.7  | Cleaver: Bleed 2s           |
| ENM_C2_04 | Cửu vạn (bốc vác)     | 200     | 15       | 0.6  | Throw Cargo: AOE damage     |
| ENM_C2_05 | Chị bán cá chua ngoa  | 120     | 18       | 1.0  | Splash: Wet debuff -10% DEF |
| ENM_C2_06 | Lơ xe hách dịch       | 110     | 14       | 1.1  | Push: Knockback 2 units     |
| ENM_C2_07 | Thầy bói dạo          | 90      | 8        | 0.8  | Curse: 20% DMG reflection   |
| ENM_C2_08 | Ăn xin giả dạng       | 60      | 5        | 0.5  | Pretend Dead: Revive 30%    |
| ENM_C2_09 | Tiểu thương gian lận  | 95      | 11       | 1.0  | Scam: Steal 10 Gold         |
| ENM_C2_10 | Giang hồ bến xe       | 160     | 22       | 0.9  | Smoke: Blind 2s             |
| ENM_C2_11 | Cò mồi bệnh viện      | 85      | 9        | 1.2  | Lure: Pull player           |
| ENM_C2_12 | Bà bán nước mía       | 100     | 10       | 0.8  | Sticky: Slow 30%            |

**BOSS C2: Trùm bảo kê chợ**

| Thuộc tính           | Giá trị                                 |
| :------------------- | :-------------------------------------- |
| **Base HP**          | 2,500                                   |
| **Base ATK**         | 50                                      |
| **ASPD**             | 0.8                                     |
| **Skill 1**          | Mã Tấu: Cone AOE 200% DMG (CD 8s)       |
| **Skill 2**          | Đàn em ơi: Summon 2 minion (CD 20s)     |
| **Skill 3 (Enrage)** | HP &lt;30%: Berserk +100% ATK, -50% DEF |
| **EXP Reward**       | 1,200                                   |
| **Gold Reward**      | 500                                     |

---

### 3.3. Chương 3: Khu Sống Ảo (12 quái + 1 Boss)

| ID        | Tên quái             | Base HP | Base ATK | ASPD | Kỹ năng đặc biệt           |
| :-------- | :------------------- | :------ | :------- | :--- | :------------------------- |
| ENM_C3_01 | Hot girl kem trộn    | 100     | 12       | 1.0  | Charm: Confuse 2s          |
| ENM_C3_02 | Thánh livestream     | 90      | 10       | 1.2  | Flash: Blind 1.5s          |
| ENM_C3_03 | Anh hùng bàn phím    | 150     | 20       | 0.9  | Keyboard Block: DEF +50%   |
| ENM_C3_04 | Ninja Lead           | 120     | 15       | 1.4  | Dodge: Evasion +30%        |
| ENM_C3_05 | Trẻ trâu nẹt pô      | 80      | 18       | 1.6  | Speed boost on hit         |
| ENM_C3_06 | Streamer toxic       | 110     | 16       | 1.1  | Rage: ATK +20% khi bị đánh |
| ENM_C3_07 | Rich kid rởm         | 130     | 14       | 0.8  | Money Shield: Absorb DMG   |
| ENM_C3_08 | Thợ chụp ảnh dạo     | 95      | 22       | 0.7  | Flash Bang: Blind all 1s   |
| ENM_C3_09 | Gymer khoe cơ        | 180     | 25       | 0.6  | Flex: Taunt + DEF up       |
| ENM_C3_10 | Tiktoker nhảy nhót   | 70      | 8        | 2.0  | Distract: Miss +15%        |
| ENM_C3_11 | Phượt thủ ý thức kém | 140     | 12       | 0.9  | Litter: Create hazard zone |
| ENM_C3_12 | Hacker mũ đen        | 85      | 30       | 0.5  | Hack: Disable skill 3s     |

**BOSS C3: Idol giới trẻ**

| Thuộc tính           | Giá trị                                        |
| :------------------- | :--------------------------------------------- |
| **Base HP**          | 5,000                                          |
| **Base ATK**         | 80                                             |
| **ASPD**             | 1.2                                            |
| **Skill 1**          | Fan Attack: Summon 3 fans (CD 15s)             |
| **Skill 2**          | Heart Beam: AOE DMG + Charm (CD 12s)           |
| **Skill 3**          | Stage Light: Blind all 3s (CD 25s)             |
| **Skill 4 (Enrage)** | HP &lt;30%: Final Performance - Full heal once |
| **EXP Reward**       | 3,000                                          |
| **Gold Reward**      | 1,200                                          |

---

### 3.4. Chương 4: Văn Phòng Công Sở (12 quái + 1 Boss)

| ID        | Tên quái               | Base HP | Base ATK | ASPD | Kỹ năng đặc biệt             |
| :-------- | :--------------------- | :------ | :------- | :--- | :--------------------------- |
| ENM_C4_01 | Sếp hách dịch          | 200     | 35       | 0.8  | Power Trip: Fear all 2s      |
| ENM_C4_02 | Thực tập sinh ngáo ngơ | 60      | 6        | 1.0  | Clumsy: Self damage 10%      |
| ENM_C4_03 | Kế toán khó tính       | 120     | 15       | 1.0  | Audit: -20% Gold reward      |
| ENM_C4_04 | HR thảo mai            | 100     | 12       | 1.2  | Backstab: +50% DMG from back |
| ENM_C4_05 | IT support cáu kỉnh    | 140     | 25       | 0.9  | Debug: Remove buff 1         |
| ENM_C4_06 | Sale chèo kéo          | 90      | 10       | 1.5  | Persistence: Revive 20%      |
| ENM_C4_07 | Drama queen            | 110     | 14       | 1.1  | Gossip Chain: Spread debuff  |
| ENM_C4_08 | Thánh ngủ trưa         | 160     | 8        | 0.3  | Sleep: Immune while sleeping |
| ENM_C4_09 | Nhân viên OT kiệt sức  | 180     | 30       | 0.7  | Burnout: High DMG, low HP    |
| ENM_C4_10 | Đồng nghiệp đổ lỗi     | 100     | 12       | 1.0  | Blame: Redirect DMG 30%      |
| ENM_C4_11 | Bà cô lao công         | 130     | 20       | 1.1  | Mop Spin: AOE knockback      |
| ENM_C4_12 | Bảo vệ tòa nhà         | 170     | 15       | 0.6  | Block: Cannot pass           |

**BOSS C4: Chủ tịch giả danh**

| Thuộc tính      | Giá trị                                      |
| :-------------- | :------------------------------------------- |
| **Base HP**     | 10,000                                       |
| **Base ATK**    | 150                                          |
| **ASPD**        | 1.0                                          |
| **Skill 1**     | Fraud: Steal 50 Gold /hit (CD 0s - passive)  |
| **Skill 2**     | Security: Summon 2 guards (CD 20s)           |
| **Skill 3**     | Power Point: AOE Sleep 3s (CD 30s)           |
| **Skill 4**     | Golden Parachute: At 10% HP, escape (Enrage) |
| **EXP Reward**  | 8,000                                        |
| **Gold Reward** | 3,000                                        |

---

## 4. Bảng Scaling mẫu theo Stage

### 4.1. Stats quái thường (Chương 1, ENM_C1_01 - Bà hàng xóm)

| Stage | Wave 1 HP | Wave 5 HP (Elite) | Wave 10 HP (Boss) | Gold Drop |
| :---- | :-------- | :---------------- | :---------------- | :-------- |
| 1     | 80        | 300               | 1,000             | 5         |
| 5     | 165       | 622               | 2,074             | 10        |
| 10    | 412       | 1,545             | 5,150             | 25        |
| 20    | 2,550     | 9,563             | 31,877            | 155       |
| 50    | 703,688   | 2,638,831         | 8,796,103         | 42,750    |
| 100   | 6.9B      | 25.8B             | 86B               | 418M      |

**Công thức áp dụng:**
$$HP_{stage50} = 80 \times 1.2^{49} \times 1.0 = 703,688$$

### 4.2. Stats Boss theo Chapter và Stage

| Chapter | Stage 10 HP | Stage 50 HP | Stage 100 HP |
| :------ | :---------- | :---------- | :----------- |
| 1       | 5,150       | 8.8M        | 86B          |
| 2       | 12,875      | 22M         | 215B         |
| 3       | 25,750      | 44M         | 430B         |
| 4       | 51,500      | 88M         | 860B         |

---

## 5. Reward Scaling

### 5.1. Công thức EXP

$$EXP_{reward} = BaseEXP \times (1 + Stage \times 0.1) \times TypeMult$$

| Type   | EXP Multiplier |
| :----- | :------------- |
| Normal | 1.0x           |
| Elite  | 3.0x           |
| Boss   | 10.0x          |

### 5.2. Công thức Gold

$$Gold_{reward} = BaseGold \times (1.05)^{Stage} \times TypeMult \times (1 + GoldBonus\%)$$

### 5.3. Drop Table

| Loại quái | Equipment Drop % | Material Drop % | Rare Drop % |
| :-------- | :--------------- | :-------------- | :---------- |
| Normal    | 1%               | 10%             | 0.1%        |
| Elite     | 5%               | 30%             | 0.5%        |
| Boss      | 20%              | 100%            | 2%          |

---

## 6. AI Behavior Pattern

### 6.1. Pattern cơ bản

| Behavior     | Điều kiện                   | Hành động                 |
| :----------- | :-------------------------- | :------------------------ |
| **Approach** | Distance > Attack Range     | Di chuyển về phía player  |
| **Attack**   | Distance &lt;= Attack Range | Tấn công theo ASPD        |
| **Skill**    | Skill CD = 0 && HP > 30%    | Sử dụng skill nếu có      |
| **Enrage**   | HP &lt;= 30%                | Kích hoạt buff đặc biệt   |
| **Flee**     | Một số quái (Móc túi)       | Chạy trốn khi HP &lt; 20% |

### 6.2. Boss Phase

Mỗi Boss có 3 phase dựa trên HP:

| Phase   | HP Range | Behavior Change                |
| :------ | :------- | :----------------------------- |
| Phase 1 | 100%-60% | Normal attack pattern          |
| Phase 2 | 60%-30%  | Sử dụng skill thường xuyên hơn |
| Phase 3 | &lt;30%  | Enrage + Special ability       |

---

## 7. Hướng dẫn cho đội phát triển

### 7.1. Cho lập trình viên

- Implement object pooling cho quái thường (spawn/despawn nhanh)
- Boss cần state machine riêng cho các phase
- Damage number cần queue system để không overlap
- Preload assets của quái theo chapter

### 7.2. Cho game designer

- Đảm bảo player có thể clear Stage X nếu có power level tương đương
- Elite quái nên xuất hiện từ Wave 5 trở đi
- Boss timer nên là 60-120s tùy chapter
- Tránh CC lock player quá 3s liên tục

### 7.3. Cho artist

- Mỗi quái cần: Idle, Walk, Attack, Hit, Death animation
- Boss cần thêm: Skill cast, Enrage transformation
- Size scaling: Normal 1x, Elite 1.2x, Boss 1.5-2x
- Hiệu ứng Enrage: Đỏ rực, particle lửa/điện
