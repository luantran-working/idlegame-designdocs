# Công thức Chiến đấu

Chi tiết các công thức liên quan đến giao tranh, bao gồm tính sát thương (Damage), phòng thủ (Defense), và các cơ chế phụ trợ như Hồi máu (Lifesteal), Né tránh (Evasion).

---

## 1. Công thức Sát thương (Damage)

Sát thương trong game được tính theo quy trình 3 bước:

1.  **Raw Damage:** Sát thương đầu ra của người tấn công.
2.  **Mitigation:** Giảm sát thương bởi người phòng thủ.
3.  **Finalize:** Áp dụng biến thiên (Variance) và các loại sát thương chuẩn (True Damage).

### 1.1. Bước 1: Raw Damage

Tính sát thương lý thuyết trước khi chạm vào mục tiêu.

$$
RawDamage = (ATK_{Total} \times SkillMultiplier) \times (1 + DamageBonus\%) \times CritMultiplier
$$

- **ATK_Total:** Tổng ATK sau khi tính buff.
- **SkillMultiplier:** Hệ số của kỹ năng (VD: Đánh thường = 1.0, Skill = 2.5).
- **DamageBonus%:** Tổng các buff tăng sát thương chung (VD: "Tăng 10% sát thương lên Boss").
- **CritMultiplier:**
  - Kiểm tra `Random(0, 1) < CritRate`.
  - Nếu Crit: Giá trị là $(1.5 + CritDamage\%)$.
  - Nếu không Crit: Giá trị là $1.0$.

### 1.2. Bước 2: Mitigation (Giảm sát thương)

Sát thương bị giảm bởi chỉ số DEF của mục tiêu. Game sử dụng công thức **Diminishing Returns** (Hiệu quả giảm dần) để DEF không bao giờ đạt 100% giảm thương.

$$
ReductionFactor = \frac{DEF_{Target}}{DEF_{Target} + DEF\_CONSTANT}
$$

- **DEF_Target:** Chỉ số thủ của mục tiêu sau khi trừ Xuyên giáp (Penetration).
  - $DEF_{Target} = \max(0, DEF_{Original} \times (1 - Penetration\%))$.
- **DEF_CONSTANT:** Hằng số cân bằng (5000).

Sát thương sau khi qua giáp:

$$
MitigatedDamage = RawDamage \times (1 - ReductionFactor)
$$

Hay viết gọn lại:

$$
MitigatedDamage = RawDamage \times \left( \frac{DEF\_CONSTANT}{DEF_{Target} + DEF\_CONSTANT} \right)
$$

### 1.3. Bước 3: Finalize (Sát thương cuối)

$$
Damage_{Final} = MitigatedDamage \times Random(0.95, 1.05) + TrueDamage
$$

- **TrueDamage:** Sát thương chuẩn (bỏ qua giáp), cộng thêm vào cuối cùng.

---

## 2. Hệ thống Tốc độ và Thời gian (Speed & Timing)

### 2.1. Attack Speed (Tốc độ đánh)

Tốc độ đánh (ASPD) quy định số đòn đánh thực hiện được trong 1 giây.

$$
AttacksPerSecond = BaseASPD \times (1 + ASPDBonus\%)
$$

Thời gian giữa 2 đòn đánh (Cooldown):

$$
AttackInterval (s) = \frac{1}{AttacksPerSecond}
$$

- **Animation Scaling:** Animation đòn đánh sẽ được tăng tốc (speed up) tương ứng với $AttackInterval$.
- **Cap:** Giới hạn tối thiểu của Attack Interval là $0.2s$ (tức 5 đòn/giây).

### 2.2. Move Speed (Tốc độ di chuyển)

$$
MoveSpeed = BaseMoveSpeed \times (1 + MoveSpeedBonus\%)
$$

- Unit di chuyển: $Distance = MoveSpeed \times TimeDelta$.

---

## 3. Các cơ chế khác

### 3.1. Hút máu (Lifesteal)

Hồi máu dựa trên sát thương thực tế gây ra (Final Damage).

$$
HP_{Heal} = Damage_{Final} \times Lifesteal\%
$$

- Hồi máu hiển thị số màu xanh lá cây bay lên.
- Không hồi máu khi đánh vào khiên (Shield) hoặc khi mục tiêu bất tử (Invulnerable).

### 3.2. Né tránh và Chính xác (Evasion & Accuracy)

Cơ chế "Hit or Miss".

$$
HitChance = 1.0 + Accuracy\% - Evasion\%
$$

- **Giới hạn:** $HitChance$ luôn nằm trong khoảng $[MinHitChance, 1.0]$.
- $MinHitChance$ thường là $0.5$ (50%) để tránh việc build full né làm game bế tắc.

### 3.3. Hiệu ứng Khống chế (Crowd Control - CC)

Thời gian hiệu lực của CC bị ảnh hưởng bởi chỉ số "Kháng hiệu ứng" (Tenacity/Resist).

$$
Duration_{Actual} = Duration_{Base} \times (1 - Tenacity\%)
$$

- Tenacity tối đa: 80% (Không bao giờ miễn nhiễm hoàn toàn trừ khi có trạng thái "Unstoppable").

---

## 4. Ví dụ tính toán (Sample Calculation)

**Thông số:**

- **Player:** ATK = 1000, CritRate = 20%, CritDmg = 50% (Tổng multiplier 2.0), Skill = 200%.
- **Enemy:** DEF = 5000 (Giảm 50% sát thương vì $C=5000$).

**Trường hợp 1: Đòn đánh thường (Skill 100%), Không Crit**

1.  Raw Damage = $1000 \times 1.0 = 1000$.
2.  Qua giáp = $1000 \times (5000 / (5000+5000)) = 1000 \times 0.5 = 500$.
3.  Biến thiên (giả sử 1.0) = **500 Damage**.

**Trường hợp 2: Dùng Skill (200%), Có Crit**

1.  Raw Damage = $1000 \times 2.0 \times 2.0 (Crit) = 4000$.
2.  Qua giáp = $4000 \times 0.5 = 2000$.
3.  Biến thiên = **2000 Damage**.
