# Chỉ số cấp độ tầng

Tài liệu này định nghĩa chi tiết hệ thống tầng (Stage/Floor), độ khó, phần thưởng và các mốc tiến trình của game.

---

## 1. Cấu trúc hệ thống tầng

### 1.1. Phân cấp

Hệ thống game được chia thành các cấp độ sau:

```
Chapter (Chương) → Stage (Tầng/Ải) → Wave (Đợt)
```

| Cấp độ      | Số lượng     | Mô tả                           |
| :---------- | :----------- | :------------------------------ |
| **Chapter** | 4 (Launch)   | Theme khác nhau, quái khác nhau |
| **Stage**   | Vô hạn (∞)   | Độ khó tăng liên tục            |
| **Wave**    | 10 per Stage | Mini-progression trong stage    |

### 1.2. Cấu trúc Wave trong Stage

| Wave | Nội dung              | Thời gian max |
| :--- | :-------------------- | :------------ |
| 1-4  | Quái thường (4-6 con) | 30s mỗi wave  |
| 5    | Quái thường + 1 Elite | 45s           |
| 6-9  | Quái thường (6-8 con) | 30s mỗi wave  |
| 10   | BOSS + 2 quái thường  | 60-120s       |

**Tổng thời gian tối đa 1 Stage:** ~8 phút (nếu chậm clear)

---

## 2. Công thức Scaling theo Stage

### 2.1. Độ khó quái vật

Công thức cơ bản cho HP và ATK của quái:

$$MonsterHP_{stage} = BaseHP_{chapter} \times (1.2)^{Stage-1}$$

$$MonsterATK_{stage} = BaseATK_{chapter} \times (1.15)^{Stage-1}$$

### 2.2. Base Stats theo Chapter

| Chapter | Base HP (Normal) | Base ATK (Normal) | Base HP (Boss) | Base ATK (Boss) |
| :------ | :--------------- | :---------------- | :------------- | :-------------- |
| 1       | 100              | 10                | 1,000          | 25              |
| 2       | 200              | 20                | 2,500          | 50              |
| 3       | 400              | 40                | 5,000          | 80              |
| 4       | 800              | 80                | 10,000         | 150             |

### 2.3. Bảng HP quái theo Stage milestone

| Stage | Chapter 1 Normal | Chapter 1 Boss | Chapter 4 Normal | Chapter 4 Boss |
| :---- | :--------------- | :------------- | :--------------- | :------------- |
| 1     | 100              | 1,000          | 800              | 10,000         |
| 10    | 516              | 5,160          | 4,128            | 51,600         |
| 25    | 5,312            | 53,120         | 42,496           | 531,200        |
| 50    | 87,965           | 879,650        | 703,720          | 8,796,500      |
| 100   | 8.28B            | 82.8B          | 66.2B            | 828B           |
| 200   | 6.86×10^16       | 6.86×10^17     | 5.49×10^17       | 6.86×10^18     |

---

## 3. Phần thưởng theo Stage

### 3.1. Công thức phần thưởng cơ bản

**Gold per monster:**
$$Gold = BaseGold \times (1.08)^{Stage-1} \times WaveMult \times TypeMult$$

**EXP per monster:**
$$EXP = BaseEXP \times (1 + Stage \times 0.05) \times TypeMult$$

### 3.2. Bảng phần thưởng chi tiết

| Stage | Gold (Normal) | Gold (Boss) | EXP (Normal) | EXP (Boss) |
| :---- | :------------ | :---------- | :----------- | :--------- |
| 1     | 5             | 200         | 10           | 500        |
| 10    | 21            | 860         | 15           | 750        |
| 25    | 116           | 4,640       | 22.5         | 1,125      |
| 50    | 1,180         | 47,200      | 35           | 1,750      |
| 100   | 109,358       | 4,374,320   | 60           | 3,000      |

### 3.3. First Clear Bonus

Lần đầu clear một Stage mới sẽ nhận bonus:

| Stage Range | First Clear Gold | First Clear Gems | Special Reward    |
| :---------- | :--------------- | :--------------- | :---------------- |
| 1-10        | 100              | 5                | -                 |
| 11-25       | 250              | 10               | Gacha Ticket x1   |
| 26-50       | 500              | 20               | Equipment Box     |
| 51-100      | 1,000            | 50               | Rare Gacha Ticket |
| 101-200     | 2,500            | 100              | Epic Gacha Ticket |
| 201+        | 5,000            | 200              | Legendary Ticket  |

---

## 4. Unlock System

### 4.1. Feature Unlock theo Stage

| Stage | Feature Unlock                  |
| :---- | :------------------------------ |
| 1     | Tutorial, Basic Combat          |
| 3     | Equipment System                |
| 5     | First Teammate (Gacha tutorial) |
| 8     | Skill System unlock             |
| 10    | Boss Mode, Auto-battle          |
| 15    | Equipment Upgrade               |
| 20    | Equipment Merge                 |
| 25    | Teammate Advancement            |
| 30    | Set Equipment                   |
| 40    | Reforge System                  |
| 50    | Challenge Mode                  |
| 75    | Prestige System (nếu có)        |
| 100   | Endgame Content                 |

### 4.2. Skill Slot Unlock

| Player Level | Skill Slots Available |
| :----------- | :-------------------- |
| 1            | 1                     |
| 5            | 2                     |
| 10           | 3                     |
| 20           | 4                     |
| 30           | 5                     |
| 40           | 6 (Maximum)           |

---

## 5. Difficulty Curve Design

### 5.1. Target Clear Time

| Stage Range | Target Clear Time/Stage | Player Power Level  |
| :---------- | :---------------------- | :------------------ |
| 1-10        | 2-3 phút                | 1,000 - 5,000 CP    |
| 11-25       | 3-4 phút                | 5,000 - 25,000 CP   |
| 26-50       | 4-5 phút                | 25,000 - 200,000 CP |
| 51-100      | 5-6 phút                | 200K - 5M CP        |
| 101+        | 6-8 phút                | 5M+ CP              |

### 5.2. Power Wall (Checkpoint)

Các mốc "Wall" buộc player phải farm/upgrade:

| Stage | Reason          | Expected Solutions            |
| :---- | :-------------- | :---------------------------- |
| 10    | First Boss      | Upgrade ATK, Get equipment    |
| 25    | HP Wall         | Merge equipment, Team up      |
| 50    | DPS Check       | Max equipment, Skill upgrades |
| 100   | Gear Check      | Full Epic+ gear required      |
| 150   | Whale Territory | Legendary gear, Max teammates |

### 5.3. Biểu đồ độ khó

_(Biểu đồ thể hiện Power Curve tăng theo cấp số nhân, trong khi sức mạnh người chơi cần đuổi kịp theo từng giai đoạn)_ -> _Xem file Excel cân bằng chi tiết._

---

## 6. Idle/AFK Progression

### 6.1. Offline Reward

Khi player offline, game tính toán progress dựa trên highest cleared stage:

$$OfflineGold = GoldPerMinute \times OfflineMinutes \times EfficiencyRate$$

| Highest Stage | Gold/Minute | EXP/Minute | Efficiency Cap |
| :------------ | :---------- | :--------- | :------------- |
| 1-10          | 10          | 5          | 8h             |
| 11-25         | 50          | 20         | 12h            |
| 26-50         | 200         | 80         | 16h            |
| 51-100        | 1,000       | 300        | 24h            |
| 101+          | 5,000       | 1,000      | 48h            |

### 6.2. Auto-Battle Settings

| Setting       | Effect                 | Unlock Stage |
| :------------ | :--------------------- | :----------- |
| Auto-Attack   | Tự động đánh thường    | 5            |
| Auto-Skill    | Tự động dùng skill     | 10           |
| Auto-Progress | Tự động tiến stage mới | 15           |
| Speed x2      | Tăng tốc 2x            | 25           |
| Speed x4      | Tăng tốc 4x            | 50 (Premium) |

---

## 7. Challenge/Hard Mode

### 7.1. Hard Mode Modifier

Sau khi clear Normal mode, người chơi có thể chơi Hard mode với modifier:

| Difficulty | Monster HP Mult | Monster ATK Mult | Reward Mult | Unlock    |
| :--------- | :-------------- | :--------------- | :---------- | :-------- |
| Normal     | 1.0x            | 1.0x             | 1.0x        | Default   |
| Hard       | 2.0x            | 1.5x             | 1.5x        | Stage 50  |
| Hell       | 5.0x            | 2.0x             | 2.5x        | Stage 100 |
| Nightmare  | 10.0x           | 3.0x             | 5.0x        | Stage 200 |

### 7.2. Time Attack Mode

| Stage | Par Time | Bronze     | Silver    | Gold      | Platinum  |
| :---- | :------- | :--------- | :-------- | :-------- | :-------- |
| 10    | 3:00     | &lt; 5:00  | &lt; 3:30 | &lt; 2:30 | &lt; 1:30 |
| 25    | 4:00     | &lt; 6:00  | &lt; 4:30 | &lt; 3:30 | &lt; 2:00 |
| 50    | 5:00     | &lt; 8:00  | &lt; 6:00 | &lt; 4:00 | &lt; 2:30 |
| 100   | 6:00     | &lt; 10:00 | &lt; 7:00 | &lt; 5:00 | &lt; 3:00 |

---

## 8. Hướng dẫn cho đội phát triển

### 8.1. Cho lập trình viên

- Stage data nên được load từ config file (JSON/ScriptableObject)
- Implement infinite stage system với procedural generation
- Offline calculation cần được validate server-side
- Cache highest cleared stage để optimize loading

### 8.2. Cho game designer

- Đảm bảo 1 stage có thể clear trong &lt; 10 phút
- Power Wall nên xuất hiện mỗi 20-25 stage
- Reward curve phải catch up với difficulty curve
- First clear bonus là động lực chính push stage mới

### 8.3. Balancing Checklist

- [ ] Player có thể farm stage -10 để upgrade
- [ ] Boss không thể bị CC lock vĩnh viễn
- [ ] Elite phải khó hơn Normal nhưng không quá OP
- [ ] Gold income đủ để upgrade 1 stat mỗi 2-3 stage
- [ ] F2P player có thể reach Stage 100 trong 2 tuần active play
