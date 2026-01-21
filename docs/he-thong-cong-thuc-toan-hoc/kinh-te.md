# Công thức Kinh tế & Tài nguyên

Chi tiết về các dòng chảy tài nguyên (Economy Flow), công thức rơi đồ (Drop rate) và thu nhập thụ động (AFK/Idle).

---

## 1. Công thức Vàng (Gold Economy)

### 1.1. Gold Drop từ Quái

Lượng vàng rơi ra khi tiêu diệt một quái vật thường.

$$
Gold_{Monster} = BaseGold \times (1 + Stage \times 0.1) \times (1.07)^{Stage}
$$

- **BaseGold:** Lượng vàng cơ bản (VD: 10 vàng).
- **Linear Factor $(1 + Stage \times 0.1)$:** Tăng tuyến tính nhẹ.
- **Exponential Factor $(1.07)^{Stage}$:** Tăng theo hàm mũ để đuổi kịp chi phí nâng cấp (tương ứng với Growth Rate 1.07 của chi phí ATK).

### 1.2. Gold Drop từ Boss

$$
Gold_{Boss} = Gold_{Monster} \times 5
$$

### 1.3. Hệ số Bonus Vàng

Thu nhập vàng thực tế chịu ảnh hưởng bởi các chỉ số Bonus.

$$
ActualGold = CalculatedGold \times (1 + GoldBonus\%)
$$

Các nguồn Gold Bonus:

- Trang bị (Dòng: +% Vàng nhận được).
- Thẻ tháng / VIP.
- Quảng cáo (x2 Vàng).
- Skill của nhân vật Support (VD: Cô Tư bán nước).

---

## 2. Công thức AFK (Idle Rewards)

Game tính toán phần thưởng dựa trên thời gian offline của người chơi.

**Nguyên lý:**
Thay vì mô phỏng trận đấu (tốn CPU), game sử dụng công thức ước lượng dựa trên:

- **KPM (Kills Per Minute):** Số quái giết được mỗi phút trung bình ở ải hiện tại.
- **GPM (Gold Per Minute):** Thu nhập vàng mỗi phút.

### 2.1. Tính GPM & EPM (Gold/Exp per Minute)

$$
GPM = Gold_{Monster} \times Kills_{AvgPerMin}
$$

$$
EPM = Exp_{Monster} \times Kills_{AvgPerMin}
$$

- $Kills_{AvgPerMin}$ thường được set cứng là **30 - 40 quái/phút** (giả định 1.5s - 2s một quái) để đảm bảo công bằng, hoặc lấy thống kê từ lần online gần nhất.

### 2.2. Tính tổng quà AFK

$$
TotalGold = GPM \times OfflineMinutes \times (1 + AFKBonus\%)
$$

**Giới hạn thời gian:**

- Maximum Offline Time: 4 giờ (Cơ bản).
- Nâng cấp VIP có thể tăng lên 8h, 12h, 24h.

---

## 3. Quy đổi Tài nguyên (Exchange Rates)

Hệ thống sử dụng **Kim Cương (Gem)** làm đơn vị tiền tệ trung gian để định giá (Anchor Pricing).

| Tài nguyên                     | Công thức quy đổi tham chiếu | Giá trị (Gem) |
| :----------------------------- | :--------------------------- | :------------ |
| **1 Giờ Vàng (Instant Gold)**  | Thu nhập AFK 60'             | 20 Gem        |
| **1 Giờ Exp (Instant Exp)**    | Thu nhập AFK 60'             | 10 Gem        |
| **1 Vé Gacha (Summon Ticket)** | -                            | 300 Gem       |
| **10 Năng lượng (Stamina)**    | -                            | 50 Gem        |
| **1 Chìa khóa Rương**          | -                            | 100 Gem       |

Dựa vào bảng này để thiết kế các gói IAP hoặc giá bán trong Shop.

---

## 4. Tỉ lệ rơi đồ (Item Drop Rates)

Xác suất rơi trang bị khi đánh quái thường (không phải gacha).

$$
DropChance = BaseChance \times (1 + Luck\%)
$$

- **BaseChance:** Rất thấp, ví dụ 0.1% (1/1000 con).
- **Luck%:** Chỉ số may mắn từ trang bị/VIP.

**Phân bố phẩm chất (Rarity Distribution) theo Stage:**

Khi một trang bị rơi ra, phẩm chất của nó được quyết định bởi Stage đang đứng.

| Stage Group      | Common (Trắng) | Uncommon (Xanh lá) | Rare (Xanh dương) | Epic (Tím) |
| :--------------- | :------------- | :----------------- | :---------------- | :--------- |
| **Stage 1-10**   | 90%            | 10%                | 0%                | 0%         |
| **Stage 11-50**  | 70%            | 25%                | 5%                | 0%         |
| **Stage 50-100** | 50%            | 30%                | 19%               | 1%         |
| **Stage 100+**   | 30%            | 40%                | 25%               | 5%         |

Quy tắc: Càng lên cao, tỉ lệ ra đồ rác càng giảm, tỉ lệ đồ xịn tăng dần.
