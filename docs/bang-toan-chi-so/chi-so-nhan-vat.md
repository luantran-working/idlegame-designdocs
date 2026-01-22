# Chỉ số nhân vật chính (Player Stats)

Tài liệu này định nghĩa chi tiết hệ thống chỉ số (Stats) của nhân vật chính, bao gồm ý nghĩa, công thức tính toán và giới hạn (Cap).

---

## 1. Phân loại chỉ số

### 1.1. Chỉ số cơ bản (Primary Stats)

Đây là các chỉ số có thể nâng cấp vô hạn bằng Vàng (Gold).

| Tên chỉ số   | Ký hiệu    | Mô tả                                             | Công thức tăng trưởng (Growth)                  |
| :----------- | :--------- | :------------------------------------------------ | :---------------------------------------------- |
| **Tấn công** | `ATK`      | Sát thương gây ra trong mỗi đòn đánh thường.      | Tuyến tính (Linear). Tăng cố định theo mỗi cấp. |
| **Máu**      | `HP`       | Khả năng chịu đựng sát thương. Về 0 thì thua màn. | Tuyến tính (Linear). Tăng cố định theo mỗi cấp. |
| **Hồi máu**  | `HP_REGEN` | Số lượng máu hồi phục mỗi giây (HP/s).            | Tuyến tính (Linear).                            |

### 1.2. Chỉ số nâng cao (Secondary Stats)

Các chỉ số này thường tăng qua Trang bị, Kỹ năng, hoặc nâng cấp đặc biệt.

| Tên chỉ số              | Ký hiệu      | Mô tả                                                | Giới hạn (Hard Cap)                                           |
| :---------------------- | :----------- | :--------------------------------------------------- | :------------------------------------------------------------ |
| **Tốc độ đánh**         | `ASPD`       | Số đòn đánh thực hiện trong 1 giây.                  | Max `5.0` (đánh siêu nhanh nhưng không làm cháy máy).         |
| **Tỉ lệ Bạo kích**      | `CRIT_RATE`  | Xác suất gây sát thương bạo kích.                    | Max `100%`.                                                   |
| **Sát thương Bạo kích** | `CRIT_DMG`   | Hệ số nhân sát thương khi bạo kích. Mặc định `150%`. | Không giới hạn (Soft cap do chi phí).                         |
| **Đa tầng**             | `MULTI_SHOT` | Xác suất bắn ra thêm 1 đòn đánh (Double shot).       | Max `100%` (Sau đó chuyển sang Triple shot nếu game mở rộng). |
| **Giảm hồi chiêu**      | `CDR`        | Giảm thời gian hồi chiêu của kỹ năng.                | Max `50%` (Tránh spam skill liên tục gây lỗi).                |

### 1.3. Chỉ số phòng thủ & Hỗ trợ (Defensive/Utility)

| Tên chỉ số   | Ký hiệu     | Mô tả                                      | Ghi chú                                               |
| :----------- | :---------- | :----------------------------------------- | :---------------------------------------------------- |
| **Né tránh** | `DODGE`     | Xác suất né hoàn toàn sát thương nhận vào. | Cap `60%` (Tránh việc nhân vật bất tử).               |
| **Hút máu**  | `LIFESTEAL` | Hồi máu dựa trên % sát thương gây ra.      | Tính trên dmg thực tế gây ra (sau khi trừ giáp quái). |
| **Tốc chạy** | `MOV_SPD`   | Tốc độ di chuyển tiếp cận quái.            | Chỉ quan trọng với tướng cận chiến.                   |

---

## 2. Công thức toán học (Formulas)

### 2.1. Chi phí nâng cấp (Upgrade Cost)

Áp dụng cho ATK, HP, HP_REGEN nâng bằng Vàng.
Công thức tăng chi phí theo luỹ thừa để kiểm soát lạm phát kinh tế.

$$Cost_{n} = Cost_{base} \times (Rate)^{n-1}$$

- **Cost_base:** Chi phí cấp 1 (Ví dụ: 10 Vàng).
- **Rate:** Hệ số tăng giá (Ví dụ: 1.07 cho ATK, 1.05 cho HP).
- **n:** Cấp độ hiện tại.

### 2.2. Sát thương đầu ra (Output Damage)

Công thức tính DMG thực tế trong 1 đòn đánh (trước khi trừ giáp quái):

Nếu **Không Bạo kích**:
$$Dmg = ATK \times (1 + \%Bonus_{equip} + \%Bonus_{skill})$$

Nếu **Bạo kích**:
$$Dmg_{crit} = Dmg \times CRIT\_DMG$$

### 2.3. Sát thương theo thời gian (DPS - Damage Per Second)

Chỉ số quan trọng nhất để so sánh sức mạnh:

$$DPS = Dmg_{avg} \times ASPD$$

Trong đó $Dmg_{avg}$ (Sát thương trung bình) tính cả tỷ lệ Crit:
$$Dmg_{avg} = Dmg \times (1 - CRIT\_RATE) + Dmg_{crit} \times CRIT\_RATE$$
Rút gọn:
$$Dmg_{avg} = Dmg \times (1 + CRIT\_RATE \times (CRIT\_DMG - 1))$$

---

## 3. Bảng cân bằng chỉ số (Balance Table) - Cấp 1 đến 100

_Ghi chú: Giả định các hệ số cơ bản để Dev tham khảo nhập liệu._

| Cấp (Level) | ATK (Base) | Cost ATK | HP (Base) | Cost HP |
| :---------- | :--------- | :------- | :-------- | :------ |
| 1           | 10         | 10       | 100       | 10      |
| 10          | 55         | 50       | 550       | 45      |
| 20          | 105        | 200      | 1050      | 180     |
| 50          | 255        | 5,000    | 2550      | 4,500   |
| 100         | 505        | 150,000  | 5050      | 120,000 |

_(Số liệu chính xác sẽ được cân chỉnh trong file Excel Balance)_

---

## 4. Quy tắc hiển thị số lớn (Big Number Formatting)

Do là game Idle, chỉ số sẽ leo lên hàng tỷ, nghìn tỷ rất nhanh. Cần quy ước hiển thị:

- **Dưới 10.000 (10k):** Hiển thị đầy đủ (Ví dụ: 9,999).
- **Trên 10k:** Sử dụng K, M, B, T (Tiếng Anh) hoặc vạn, triệu, tỷ (Tiếng Việt - Tùy user chọn).
  - 1,000 = 1K
  - 1,000,000 = 1M
  - 1,000,000,000 = 1B
  - 1,000,000,000,000 = 1T
  - Sau T sẽ dùng bảng chữ cái: aa, ab, ac...

---

## 5. Tương tác với hệ thống khác

- **Trang bị:** Cộng thẳng vào stats (Flat) hoặc cộng % (Percent).
  - Ví dụ: Dép lào cấp 1: `+10 ATK`. Dép lào cấp 100: `+10% ATK`.
- **Đồng đội:** Chủ yếu buff Passive % stats cho nhân vật chính.
  - Ví dụ: Đồng đội "Bà hàng xóm" buff `+5% ASPD`.
