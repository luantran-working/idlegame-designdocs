# Tổng quan hệ thống công thức

Tài liệu này định nghĩa các hằng số, biến số toàn cục và nguyên tắc toán học cốt lõi được sử dụng xuyên suốt game "Bảo vệ khu phố".

---

## 1. Nguyên tắc thiết kế (Math Philosophy)

### 1.1. Big Numbers (Số lớn)

Game thuộc thể loại Idle, vì vậy các con số sẽ tăng trưởng phi tuyến tính và đạt giá trị rất lớn.
Hệ thống cần hỗ trợ hiển thị và tính toán các số lên đến $10^{300}$ (Double precision floating point hoặc BigInt library).

**Quy ước hiển thị:**

- 1,000 = 1K
- 1,000,000 = 1M
- 1,000,000,000 = 1B
- 1,000,000,000,000 = 1T
- $10^{15}$ = 1aa, $10^{18}$ = 1ab, ...

### 1.2. Hạn chế Linear Scaling (Tăng trưởng tuyến tính)

Hầu hết các hệ thống (chi phí, sức mạnh quái) đều sử dụng hàm mũ (Exponential) để tạo độ khó tăng dần và cảm giác "bùng nổ" sức mạnh khi nâng cấp.

---

## 2. Hằng số toàn cục (Global Constants)

Các hằng số này được dùng chung trong nhiều công thức khác nhau.

| Hằng số                    | Tên biến (Code)   | Giá trị | Ý nghĩa                                                                           |
| :------------------------- | :---------------- | :------ | :-------------------------------------------------------------------------------- |
| **Hằng số Giáp**           | `DEF_CONSTANT`    | 5000    | Dùng để tính % giảm thương. Giá trị này xác định mốc DEF nào đạt 50% giảm thương. |
| **Giới hạn Tốc độ đánh**   | `MAX_ASPD`        | 5.0     | Số đòn đánh tối đa mỗi giây (để tránh lỗi animation).                             |
| **Tốc độ di chuyển chuẩn** | `BASE_MOVE_SPEED` | 3.0     | Đơn vị Unity/giây.                                                                |
| **Số khung hình chuẩn**    | `FRAME_RATE`      | 60      | Dùng để quy đổi thời gian sang frames.                                            |
| **Hệ số Crit cơ bản**      | `BASE_CRIT_DMG`   | 1.5     | Sát thương mặc định khi chí mạng (150%).                                          |

---

## 3. Các loại chỉ số (Stats Types)

### 3.1. Chỉ số cơ bản (Primary Stats)

Tăng trực tiếp qua Level Up và Equipment.

- **ATK (Attack):** Sức tấn công.
- **HP (Health Point):** Máu tối đa.
- **DEF (Defense):** Giáp.

### 3.2. Chỉ số phụ (Secondary Stats)

Thường ở dạng % và có giới hạn (Hard Cap).

- **Crit Rate (%):** Tỷ lệ chí mạng. Max 100%.
- **Crit Damage (%):** Sát thương cộng thêm khi chí mạng. Không giới hạn.
- **ASPD (%):** Tốc độ đánh cộng thêm.
- **Evasion (%):** Tỷ lệ né tránh. Max 80%.
- **Accuracy (%):** Độ chính xác, trừ vào Evasion đối phương.

---

## 4. Thứ tự tính toán (Calculation Order)

Khi có nhiều nguồn tăng chỉ số (Base, Buff cộng thẳng, Buff phần trăm), thứ tự áp dụng như sau:

$$
Stat_{Final} = (Base + \sum FlatBonus) \times (1 + \sum PercentBonus)
$$

**Ví dụ:**

- Base ATK = 100
- Trang bị cộng thêm: +50 ATK (Flat)
- Skill Passive: +20% ATK (Additive Percent)
- Buff của đồng đội: +10% ATK (Additive Percent)

$$
ATK_{Final} = (100 + 50) \times (1 + 0.20 + 0.10) = 150 \times 1.3 = 195
$$

**Lưu ý:** Rất ít nguồn buff là _Multiplicative_ (nhân sau cùng). Nếu có sẽ được ghi chú riêng là "Final Damage Multiplier".
