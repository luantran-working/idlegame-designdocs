# Công thức và Xác suất Gacha

Tài liệu chi tiết về thuật toán RNG (Random Number Generation), tỉ lệ quay thưởng và cơ chế bảo hiểm (Pity).

---

## 1. Thuật toán Ngẫu nhiên (Random Algorithm)

### 1.1. Weighted Random Selection

Hệ thống KHÔNG dùng random đều (Uniform Random) mà dùng **Random có trọng số** để dễ dàng điều chỉnh tỉ lệ mà không cần sửa code logic nhiều.

**Công thức:**
Cho danh sách vật phẩm $I = \{i_1, i_2, ..., i_n\}$ với trọng số tương ứng $W = \{w_1, w_2, ..., w_n\}$.

1.  Tính tổng trọng số: $W_{total} = \sum w_i$.
2.  Lấy số ngẫu nhiên $R \in [0, W_{total})$.
3.  Duyệt qua danh sách, trừ dần $R$ cho $w_i$. Nếu $R < 0$, chọn vật phẩm $i$.

**Ví dụ:**

- Item A (Rác): Weight 900
- Item B (Hiếm): Weight 90
- Item C (Huyền thoại): Weight 10
- Tổng = 1000.
- Tỉ lệ Item C = 10/1000 = 1%.

---

## 2. Các Bể Gacha (Gacha Pools)

### 2.1. Banner Nhân vật (Character Banner)

| Phẩm chất (Rarity)    | Trọng số (Weight) | Tỉ lệ hiển thị (Rate) |
| :-------------------- | :---------------- | :-------------------- |
| **R (Common/Shards)** | 6000              | 60.0%                 |
| **SR (Rare)**         | 3000              | 30.0%                 |
| **SSR (Epic)**        | 850               | 8.5%                  |
| **UR (Legendary)**    | 150               | **1.5%**              |
| **Tổng**              | 10,000            | 100%                  |

### 2.2. Banner Trang bị (Equipment Banner)

| Phẩm chất (Rarity)     | Trọng số (Weight) | Tỉ lệ hiển thị (Rate) |
| :--------------------- | :---------------- | :-------------------- |
| **Trắng (Common)**     | 5000              | 50.0%                 |
| **Xanh lá (Uncommon)** | 3000              | 30.0%                 |
| **Xanh dương (Rare)**  | 1500              | 15.0%                 |
| **Tím (Epic)**         | 400               | 4.0%                  |
| **Cam (Legendary)**    | 90                | **0.9%**              |
| **Đỏ (Mythic)**        | 10                | **0.1%**              |

---

## 3. Cơ chế Bảo hiểm (Pity System)

Để đảm bảo trải nghiệm người dùng, hệ thống áp dụng cơ chế Soft Pity và Hard Pity cho các vật phẩm hiếm nhất (UR/Legendary).

### 3.1. Nguyên lý hoạt động

Mỗi banner có một bộ đếm `PityCounter` riêng. Counter tăng 1 mỗi lần quay không ra đồ hiếm nhất. Counter reset về 0 khi ra đồ hiếm nhất.

### 3.2. Công thức Pity tích lũy (Soft Pity)

- **Ngưỡng bắt đầu (Soft Cap):** 50 lượt quay.
- **Ngưỡng cam kết (Hard Cap):** 80 lượt quay.

**Tỉ lệ thực tế ($Rate_{Actual}$):**

$$
Rate_{Actual}(n) =
\begin{cases}
Rate_{Base} & \text{nếu } n < 50 \\
Rate_{Base} + (n - 50) \times 2\% & \text{nếu } 50 \le n < 80 \\
100\% & \text{nếu } n = 80
\end{cases}
$$

**Biểu diễn:**

- Lượt 1-49: Tỉ lệ 1.5% (đối với tướng UR).
- Lượt 50: Tỉ lệ $1.5\% + 0\% = 1.5\%$.
- Lượt 51: Tỉ lệ $1.5\% + 2\% = 3.5\%$.
- Lượt 60: Tỉ lệ $1.5\% + 20\% = 21.5\%$.
- Lượt 70: Tỉ lệ $1.5\% + 40\% = 41.5\%$.
- ...

### 3.3. Tỉ lệ tổng hợp (Consolidated Probability)

Với cơ chế Pity trên, tỉ lệ rơi trung bình thực tế (Average Rate) sẽ cao hơn tỉ lệ gốc.

- Base Rate: 1.5%
- Consolidated Rate: ~2.3%

Game Designer cần dùng con số ~2.3% để tính toán kinh tế, nhưng hiển thị con số 1.5% cho user (hoặc hiển thị cả hai tùy luật pháp).

---

## 4. Logic Pseudo-Random cho Critical/Evasion

Trong chiến đấu, để tránh việc xui xẻo liên tiếp (ví dụ 80% Crit mà đánh 5 cái không crit cái nào), có thể áp dụng **PRD (Pseudo-Random Distribution)** như Warcraft 3 hoặc Dota 2.

Tuy nhiên, với game Idle số lượng đòn đánh rất lớn, **True Random** thường đủ tốt và ít tốn performance hơn.
Hiện tại game sử dụng **True Random** cho chiến đấu và **Pity System** cho Gacha.
