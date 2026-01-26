# Chỉ số kỹ năng chính

Tài liệu này định nghĩa chi tiết các thông số kỹ thuật, công thức tính toán và bảng cân bằng cho 20 kỹ năng của nhân vật chính.

---

## 1. Thông số cơ bản của kỹ năng

### 1.1. Cấu trúc dữ liệu kỹ năng

Mỗi kỹ năng được định nghĩa bởi các thuộc tính sau:

| Thuộc tính             | Ký hiệu           | Mô tả                                        | Ví dụ            |
| :--------------------- | :---------------- | :------------------------------------------- | :--------------- |
| **ID kỹ năng**         | `skill_id`        | Mã định danh duy nhất                        | "skill_nem_gach" |
| **Cấp độ**             | `level`           | Cấp độ hiện tại của kỹ năng                  | 10               |
| **Cấp độ tối đa**      | `max_level`       | Giới hạn cấp độ                              | 50               |
| **Thời gian hồi**      | `cooldown`        | Thời gian chờ giữa các lần sử dụng (giây)    | 2.0              |
| **Hệ số sát thương**   | `damage_mult`     | Phần trăm ATK được chuyển thành sát thương   | 150%             |
| **Thời gian hiệu ứng** | `effect_duration` | Thời gian debuff/buff kéo dài (giây)         | 3.0              |
| **Vùng ảnh hưởng**     | `aoe_radius`      | Bán kính tác động (đơn vị game)              | 2.5              |
| **Năng lượng**         | `energy_cost`     | Chi phí năng lượng để sử dụng (nếu có)       | 0                |
| **Loại mục tiêu**      | `target_type`     | Đơn/Diện rộng/Bản thân/Đồng đội              | "single"         |
| **Thuộc tính scaling** | `scaling_stat`    | Chỉ số được dùng để tính sát thương/hiệu ứng | "ATK"            |

---

## 2. Công thức tính toán

### 2.1. Sát thương kỹ năng (Skill Damage)

Công thức cơ bản cho kỹ năng gây sát thương:

$$SkillDamage = ATK \times DamageMultiplier_{level} \times (1 + SkillDmgBonus\%)$$

Trong đó:

- **ATK:** Tổng tấn công của nhân vật (đã bao gồm trang bị và buff)
- **DamageMultiplier_level:** Hệ số sát thương tại cấp độ hiện tại
- **SkillDmgBonus:** Bonus sát thương kỹ năng từ trang bị hoặc bộ hiệu ứng

### 2.2. Công thức tăng trưởng theo cấp độ

Mỗi kỹ năng có hệ số tăng trưởng riêng. Công thức chung:

$$DamageMultiplier_{level} = BaseMultiplier + (ScalingPerLevel \times (Level - 1))$$

**Ví dụ cho skill "Ném gạch":**

- Base Multiplier: 150%
- Scaling per Level: +10% mỗi cấp
- Tại Level 10: $150\% + (10\% \times 9) = 240\%$

### 2.3. Công thức giảm hồi chiêu

Một số kỹ năng có scaling giảm cooldown:

$$Cooldown_{actual} = Cooldown_{base} \times (1 - CDR\%) - CDReduction_{level}$$

**Giới hạn:** Cooldown tối thiểu = $Cooldown_{base} \times 0.5$ (không bao giờ giảm quá 50%)

### 2.4. Công thức hiệu ứng CC

Thời gian CC scaling theo level:

$$Duration_{level} = BaseDuration + (DurationScaling \times (Level - 1))$$

---

## 3. Bảng chi tiết 20 kỹ năng

### 3.1. Nhóm Tấn công (10 kỹ năng)

#### Kỹ năng 1: Ném gạch

| Thuộc tính       | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :--------------- | :---------- | :--------- | :----------------- |
| **Cooldown**     | 2.0s        | -          | 2.0s               |
| **Damage Mult**  | 150%        | +10%       | 640%               |
| **Mục tiêu**     | Đơn         | -          | Đơn                |
| **Hiệu ứng phụ** | Không       | -          | Không              |

**Công thức DPS lý thuyết:**
$$DPS_{NemGach} = \frac{ATK \times DamageMult}{Cooldown} = \frac{ATK \times 1.5}{2.0} = 0.75 \times ATK$$

#### Kỹ năng 2: Quạt chả

| Thuộc tính             | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :--------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**           | 8.0s        | -          | 8.0s               |
| **Damage Mult**        | 120%        | +8%        | 512%               |
| **Mục tiêu**           | Hình nón    | -          | Hình nón           |
| **Số mục tiêu tối đa** | 5           | -          | 5                  |
| **Vùng ảnh hưởng**     | 60 độ       | -          | 60 độ              |

#### Kỹ năng 3: Dép lào thần chưởng

| Thuộc tính           | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**         | 12.0s       | -          | 12.0s              |
| **Damage Mult (đi)** | 200%        | +15%       | 935%               |
| **Damage Mult (về)** | 100%        | +7.5%      | 467%               |
| **Mục tiêu**         | Xuyên qua   | -          | Xuyên qua          |
| **Tầm xa**           | 8 đơn vị    | -          | 8 đơn vị           |

**Ghi chú:** Dép bay đi xuyên qua mục tiêu, gây sát thương lần 1, rồi quay về gây sát thương lần 2.

#### Kỹ năng 4: Chém gió

| Thuộc tính            | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**          | 15.0s       | -          | 15.0s              |
| **Damage/Tick**       | 50%         | +5%        | 295%               |
| **Thời gian tồn tại** | 3.0s        | -          | 3.0s               |
| **Tick rate**         | 0.5s        | -          | 0.5s (6 tick)      |
| **Vùng ảnh hưởng**    | Bán kính 3  | -          | Bán kính 3         |

**Tổng sát thương tiềm năng (6 tick):**
$$TotalDmg_{Lv1} = 50\% \times 6 = 300\%$$
$$TotalDmg_{Lv50} = 295\% \times 6 = 1770\%$$

#### Kỹ năng 5: Phun mưa

| Thuộc tính      | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------- | :---------- | :--------- | :----------------- |
| **Cooldown**    | 20.0s       | -          | 20.0s              |
| **Damage Mult** | 250%        | +20%       | 1230%              |
| **Mục tiêu**    | Hình nón    | -          | Hình nón           |
| **Góc**         | 90 độ       | -          | 90 độ              |
| **Tầm xa**      | 5 đơn vị    | -          | 5 đơn vị           |

#### Kỹ năng 6: Mưa thiên thạch

| Thuộc tính               | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :----------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**             | 40.0s       | -          | 40.0s              |
| **Damage/Thiên thạch**   | 300%        | +30%       | 1770%              |
| **Số lượng thiên thạch** | 5           | -          | 5                  |
| **Bán kính nổ**          | 1.5 đơn vị  | -          | 1.5 đơn vị         |

**Tổng sát thương tiềm năng (nếu trúng hết):**
$$TotalDmg_{Lv1} = 300\% \times 5 = 1500\%$$
$$TotalDmg_{Lv50} = 1770\% \times 5 = 8850\%$$

#### Kỹ năng 7: Đấm trâu

| Thuộc tính       | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :--------------- | :---------- | :--------- | :----------------- |
| **Cooldown**     | 5.0s        | -          | 5.0s               |
| **Damage Mult**  | 250%        | +15%       | 985%               |
| **Mục tiêu**     | Đơn         | -          | Đơn                |
| **Hiệu ứng phụ** | Knockback   | -          | Knockback 2 đơn vị |

#### Kỹ năng 8: Xả súng nước

| Thuộc tính        | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :---------------- | :---------- | :--------- | :----------------- |
| **Cooldown**      | 10.0s       | -          | 10.0s              |
| **Damage/Phát**   | 60%         | +5%        | 305%               |
| **Số phát bắn**   | 5           | -          | 5                  |
| **Thời gian bắn** | 1.0s        | -          | 1.0s (5 phát/giây) |

**Tổng sát thương:** $60\% \times 5 = 300\%$ (Lv1) → $305\% \times 5 = 1525\%$ (Lv50)

#### Kỹ năng 9: Bom hẹn giờ

| Thuộc tính           | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**         | 15.0s       | -          | 15.0s              |
| **Damage Mult**      | 400%        | +25%       | 1625%              |
| **Thời gian nổ**     | 3.0s        | -          | 3.0s               |
| **Bán kính nổ**      | 2.0 đơn vị  | -          | 2.0 đơn vị         |
| **Mục tiêu ban đầu** | Đơn         | -          | Đơn                |

#### Kỹ năng 10: Tia laser

| Thuộc tính      | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------- | :---------- | :--------- | :----------------- |
| **Cooldown**    | 25.0s       | -          | 25.0s              |
| **Damage Mult** | 350%        | +20%       | 1330%              |
| **Loại**        | Xuyên thấu  | -          | Xuyên thấu         |
| **Chiều dài**   | 15 đơn vị   | -          | 15 đơn vị          |
| **Chiều rộng**  | 1.0 đơn vị  | -          | 1.0 đơn vị         |

---

### 3.2. Nhóm Khống chế & Suy yếu (5 kỹ năng)

#### Kỹ năng 11: Tiếng thét

| Thuộc tính           | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**         | 18.0s       | -          | 18.0s              |
| **Giảm ATK địch**    | 20%         | +1%        | 69%                |
| **Thời gian debuff** | 5.0s        | +0.05s     | 7.45s              |
| **Vùng ảnh hưởng**   | Bán kính 4  | -          | Bán kính 4         |

**Giới hạn giảm ATK:** Tối đa 50% (không thể stack quá mức này)

#### Kỹ năng 12: Đặt bẫy chuột

| Thuộc tính            | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**          | 10.0s       | -          | 10.0s              |
| **Damage Mult**       | 100%        | +10%       | 590%               |
| **Thời gian Root**    | 2.0s        | +0.02s     | 2.98s              |
| **Số bẫy tối đa**     | 3           | -          | 3                  |
| **Thời gian tồn tại** | 30s         | -          | 30s                |

#### Kỹ năng 13: Mắt lé

| Thuộc tính         | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :----------------- | :---------- | :--------- | :----------------- |
| **Cooldown**       | 25.0s       | -0.1s      | 20.1s              |
| **Thời gian Stun** | 1.5s        | +0.02s     | 2.48s              |
| **Mục tiêu**       | Đơn         | -          | Đơn                |

#### Kỹ năng 14: Ném mắm tôm

| Thuộc tính            | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**          | 20.0s       | -          | 20.0s              |
| **Damage/Tick (DoT)** | 50%         | +5%        | 295%               |
| **Thời gian Poison**  | 5.0s        | -          | 5.0s               |
| **Tick rate**         | 1.0s        | -          | 1.0s (5 tick)      |
| **Bán kính vũng**     | 2.0 đơn vị  | -          | 2.0 đơn vị         |

**Tổng sát thương DoT:** $50\% \times 5 = 250\%$ (Lv1) → $295\% \times 5 = 1475\%$ (Lv50)

#### Kỹ năng 15: Keo dính chuột

| Thuộc tính            | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :-------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**          | 15.0s       | -          | 15.0s              |
| **Slow %**            | 50%         | +2%        | 148%               |
| **Thời gian tồn tại** | 5.0s        | -          | 5.0s               |
| **Bán kính vũng**     | 3.0 đơn vị  | -          | 3.0 đơn vị         |

**Giới hạn Slow:** Tối đa 80% (không thể làm địch đứng yên hoàn toàn)

---

### 3.3. Nhóm Hỗ trợ & Sinh tồn (5 kỹ năng)

#### Kỹ năng 16: Uống nước tăng lực

| Thuộc tính          | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------ | :---------- | :--------- | :----------------- |
| **Cooldown**        | 30.0s       | -          | 30.0s              |
| **Tăng ASPD**       | 30%         | +1%        | 79%                |
| **Tăng Move Speed** | 20%         | +0.5%      | 44.5%              |
| **Thời gian buff**  | 8.0s        | +0.1s      | 12.9s              |

#### Kỹ năng 17: Băng bó

| Thuộc tính          | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------ | :---------- | :--------- | :----------------- |
| **Cooldown**        | 45.0s       | -          | 45.0s              |
| **Hồi % HP tối đa** | 20%         | +2%        | 118%               |
| **Thời gian hồi**   | 4.0s        | -          | 4.0s               |
| **Tick rate**       | 0.5s        | -          | 0.5s (8 tick)      |

**Ghi chú:** Hiệu ứng HoT (Heal over Time), nếu bị gián đoạn sẽ mất phần còn lại

#### Kỹ năng 18: Gồng mình

| Thuộc tính           | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**         | 40.0s       | -          | 40.0s              |
| **Shield = % ATK**   | 300%        | +20%       | 1280%              |
| **Thời gian shield** | 5.0s        | +0.05s     | 7.45s              |

**Công thức Shield:**
$$ShieldAmount = ATK \times ShieldMultiplier$$

#### Kỹ năng 19: Nổi giận

| Thuộc tính         | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :----------------- | :---------- | :--------- | :----------------- |
| **Cooldown**       | 60.0s       | -          | 60.0s              |
| **Tăng ATK**       | 50%         | +2%        | 148%               |
| **Giảm DEF**       | 30%         | -          | 30% (không đổi)    |
| **Thời gian buff** | 10.0s       | +0.1s      | 14.9s              |

**Ghi chú:** Kỹ năng "High Risk, High Reward" - Tăng sát thương lớn nhưng dễ chết hơn

#### Kỹ năng 20: Trốn tìm

| Thuộc tính              | Giá trị Lv1 | Scaling/Lv | Giá trị Max (Lv50) |
| :---------------------- | :---------- | :--------- | :----------------- |
| **Cooldown**            | 35.0s       | -          | 35.0s              |
| **Thời gian tàng hình** | 3.0s        | +0.2s      | 12.8s              |
| **Bonus First Strike**  | 200%        | +5%        | 445%               |

**Cơ chế First Strike:**

- Khi thoát tàng hình, đòn đánh đầu tiên (trong 2 giây) được nhân thêm hệ số
- Công thức: $FirstStrikeDmg = NormalDmg \times FirstStrikeMultiplier$

---

## 4. Chi phí nâng cấp kỹ năng

### 4.1. Nguyên liệu nâng cấp

| Cấp độ  | Vàng cần   | Sách kỹ năng | Ghi chú                   |
| :------ | :--------- | :----------- | :------------------------ |
| 1 → 10  | 1,000/lv   | 1/lv         | Giai đoạn đầu             |
| 11 → 20 | 5,000/lv   | 3/lv         | Bắt đầu tốn kém           |
| 21 → 30 | 20,000/lv  | 5/lv         | Trung game                |
| 31 → 40 | 100,000/lv | 10/lv        | Late game                 |
| 41 → 50 | 500,000/lv | 25/lv        | Endgame (whale territory) |

### 4.2. Công thức tổng chi phí

$$TotalCost_{gold} = \sum_{i=1}^{n} Cost_{tier}(i)$$

**Tổng vàng để max 1 skill (Lv50):**

- Tier 1-10: 10,000
- Tier 11-20: 50,000
- Tier 21-30: 200,000
- Tier 31-40: 1,000,000
- Tier 41-50: 5,000,000
- **Tổng: 6,260,000 vàng**

---

## 5. Bảng so sánh DPS kỹ năng (Lv50)

| Kỹ năng             | Cooldown | Tổng Damage % | DPS hiệu quả (/s) | Ghi chú          |
| :------------------ | :------- | :------------ | :---------------- | :--------------- |
| **Ném gạch**        | 2s       | 640%          | 320%              | Single target    |
| **Mưa thiên thạch** | 40s      | 8850%         | 221%              | AOE, RNG vị trí  |
| **Bom hẹn giờ**     | 15s      | 1625%         | 108%              | Delay 3s, AOE    |
| **Tia laser**       | 25s      | 1330%         | 53%               | Xuyên thấu       |
| **Chém gió**        | 15s      | 1770%         | 118%              | DOT, AOE         |
| **Dép lào**         | 12s      | 1402%         | 117%              | 2 lần sát thương |

**Ghi chú:** DPS hiệu quả = Tổng Damage / Cooldown. Con số này không tính đến AoE, CC, hay các yếu tố phụ.

---

## 6. Hướng dẫn cho đội phát triển

### 6.1. Cho lập trình viên

- Mỗi skill cần có struct/class chứa đầy đủ các parameter như bảng trên
- Implement skill level scaling theo công thức linear
- Kiểm tra giới hạn (cap) cho các chỉ số như Slow, ATK reduction
- Animation speed có thể giữ nguyên, chỉ thay đổi VFX intensity theo level

### 6.2. Cho game designer (Balancing)

- Skill damage nên scale chậm hơn stat growth để tránh power creep
- CC duration nên có soft cap (~3s) để không lock địch vĩnh viễn
- Skill với CD thấp nên có damage thấp hơn per hit nhưng DPS cao hơn
- Ultimate skill (CD > 30s) nên có damage burst cao để rewarding

### 6.3. Bảng màu hiệu ứng (cho VFX artist)

| Nhóm kỹ năng  | Màu chủ đạo   | Hiệu ứng particle      |
| :------------ | :------------ | :--------------------- |
| **Tấn công**  | Đỏ, Cam       | Lửa, Bụi, Vỡ vụn       |
| **Khống chế** | Tím, Xanh đậm | Sóng âm, Khói, Xoắn ốc |
| **Hỗ trợ**    | Xanh lá, Vàng | Tim, Sao, Hào quang    |
