# Feature Boosters — Design Spec

> Các tính năng bổ sung cho game "Bảo vệ khu phố" — v2.1
> Ngày: 18/05/2026

---

## 1. Tổng quan

Tài liệu này mô tả các tính năng bổ sung và cải tiến cho game idle RPG "Bảo vệ khu phố", được chia làm 3 nhóm:

- **Nhóm 1: Hiệu ứng & Visual** — Stage Clear, Boss Entrance, Point Click VFX
- **Nhóm 2: UI/UX Improvements** — Mobile-first redesign, AFK Lock Screen, Continue Gacha, Upgradable Point Indicator
- **Nhóm 3: Hệ thống Mới** — Hub Tab, Collection System (hoàn toàn mới)

---

## 2. Nhóm 1: Hiệu ứng & Visual

### 2.1. Stage Clear Effect

Khi người chơi vượt qua màn (tiêu diệt hết wave quái), phát animation:

| Thành phần | Mô tả |
|-----------|-------|
| **Chữ "Clear!"** | Text lớn, phóng to từ giữa màn hình, màu vàng gold, có glow |
| **Particle burst** | Hiệu ứng sao/tia sáng bắn ra từ center |
| **Rewards popup** | Danh sách phần thưởng trượt từ dưới lên (vàng, exp, item drop) |
| **Duration** | 1.5s — tự động chuyển sang màn tiếp theo |
| **Skip** | Tap anywhere để bỏ qua hiệu ứng ngay lập tức |

### 2.2. Boss Entrance Effect

Khi boss xuất hiện ở đầu wave cuối:

| Thành phần | Mô tả |
|-----------|-------|
| **Screen shake** | Rung nhẹ màn hình (0.3s) |
| **Dark overlay** | Màn hình tối dần + focus light vào vị trí boss |
| **Boss intro** | Boss xuất hiện với animation: hạ cánh/nhảy xuống/trồi lên |
| **Boss name & HP bar** | Text tên boss + thanh máu xuất hiện ở top |
| **Duration** | 1.0s — không skip được |

### 2.3. Point Click Effect

Khi người chơi tap vào tài nguyên (AFK collect, click nhận thưởng, etc.):

| Thành phần | Mô tả |
|-----------|-------|
| **Ripple** | Sóng tròn lan ra từ vị trí tap |
| **Number popup** | "+X vàng" hoặc "+Y exp" bay lên và fade out |
| **Particle** | Tia sáng nhỏ bắn ra, màu tương ứng loại tài nguyên |
| **Haptic** | Rung nhẹ (nếu thiết bị hỗ trợ) |

---

## 3. Nhóm 2: UI/UX Improvements

### 3.1. Mobile-first UI Redesign

Redesign toàn bộ layout game theo hướng mobile-first:

| Nguyên tắc | Chi tiết |
|-----------|---------|
| **Touch targets** | Tất cả nút tối thiểu 48x48px, khuyến nghị 56x56px |
| **Spacing** | Padding 16px tối thiểu từ viền màn hình |
| **1-hand zone** | Thao tác chính đặt ở nửa dưới màn hình (reachable zone) |
| **Font size** | Tối thiểu 14px cho nội dung, 18px cho label |
| **Bottom nav** | Thanh điều khiển chính đặt dưới cùng, dễ thumb reach |
| **Gestures** | Swipe để chuyển tab, long-press để xem chi tiết |

### 3.2. AFK Lock Screen

Khi người chơi không tương tác trong thời gian dài:

| Thuộc tính | Giá trị |
|-----------|---------|
| **Thời gian inactive** | 5 phút |
| **Màn hình khóa** | Overlay tối + animation hoạt hình nhân vật ngủ gật |
| **Hiển thị** | Thời gian AFK, tài nguyên đã farm được khi vắng mặt |
| **Mở khóa** | Swipe hoặc tap 3 lần — animation thức dậy |
| **Tùy chọn** | Có thể tắt trong Settings — chỉ cảnh báo lần đầu |

Luồng:
```
Player inactive 5 phút → Màn tối dần (1s) → Overlay AFK
     ↓
Tài nguyên tích lũy hiển thị real-time
     ↓
Player tap 3 lần → Overlay biến mất → Game tiếp tục
```

### 3.3. Continue Gacha

Khi gacha ra item, thay vì phải đóng popup và bấm lại:

| Tính năng | Mô tả |
|-----------|-------|
| **Nút "Gacha tiếp"** | Trong popup kết quả gacha, có nút gacha ngay (x1 hoặc x10) |
| **Auto-tiếp** | Nếu đủ currency, hiển thị nút; nếu không, tự động chuyển sang shop |
| **Batch animation** | Khi gacha nhiều lần liên tiếp, animation rút gọn dần |
| **Skip animation** | Nút skip ở góc, tap để bỏ qua animation kết quả |

### 3.4. Upgradable Point Indicator

Hiển thị trực quan khi một tính năng có thể nâng cấp hoặc sử dụng:

| Loại indicator | Mô tả |
|---------------|-------|
| **Red dot** | Trên tab/icon — có nội dung mới hoặc có thể nâng cấp |
| **Glow** | Viền sáng xung quanh nút/item có thể nâng cấp |
| **Number badge** | Số lượng nâng cấp khả dụng (VD: tab "Hero" hiện "3") |
| **"Up!" text** | Chữ nhỏ trên item đạt điều kiện nâng cấp |
| **Priority** | Chỉ hiển thị cho lần nâng cấp đầu tiên có thể — sau khi người chơi đã thấy thì thường về red dot |

---

## 4. Nhóm 3: Hệ thống Mới

### 4.1. Hub Tab

Tab riêng trong thanh điều khiển (bottom nav) — nơi tập trung Skill Tree và Tàn tích.

Layout Hub Tab:
```
+--------------------------------------+
|            TRUNG TÂM                 |
+--------------------------------------+
|                                       |
|   [Skill Tree]      [Tàn tích]       |
|                                       |
|   Cây kỹ năng       Đập bình farm    |
|   (đã thiết kế)     (đã thiết kế)    |
|                                       |
+--------------------------------------+
|  Nút chuyển nhanh đến Main Hero     |
+--------------------------------------+
```

- **Skill Tree**: Tách từ Prestige system hiện tại, UI dạng cây độc lập
- **Tàn tích**: Mini-game đập bình đã thiết kế, chuyển vào Hub
- **Navigation**: Tap vào card để vào màn hình chi tiết tương ứng

### 4.2. Collection System (Hoàn toàn mới)

#### 4.2.1. Khái niệm

Hệ thống sưu tầm toàn bộ vật phẩm trong game. Lần đầu sở hữu một item sẽ ghi vào Collection và tặng chỉ số vĩnh viễn toàn cục.

#### 4.2.2. Các bộ sưu tập

| Bộ sưu tập | Đối tượng | Phần thưởng |
|-----------|-----------|-------------|
| **Nhân vật** | Tất cả đồng đội (30+) | ATK%, HP% |
| **Trang bị** | Tất cả item (4 slot × nhiều tier) | DEF%, Crit% |
| **Thánh vật** | 7 slot × 6 phẩm chất (42 item) | All Stats% |
| **Quái vật** | Tất cả quái trong game | DMG to monsters |
| **Kỹ năng** | Tất cả skill nhân vật chính | Skill DMG% |

#### 4.2.3. Cơ chế

- **Điều kiện**: Sở hữu item lần đầu (không cần giữ trong kho)
- **Phần thưởng**: Stat vĩnh viễn + milestone theo số lượng
- **Full bộ**: Bonus đặc biệt khi sưu tầm đủ tất cả item trong 1 bộ
- **Theo dõi**: Progress bar + preview milestone tiếp theo

#### 4.2.4. UI Layout

```
+--------------------------------------+
|      BỘ SƯU TẬP (Collection)        |
+--------------------------------------+
| [Nhân vật] [Trang bị] [Thánh vật]... |  ← tab
+--------------------------------------+
|                                       |
|  Nhân vật: 12/30 ▼  (+5% ATK)        |
|  [icon] [icon] [icon] [???] [???]     |
|  [icon] [icon] [???]  [???]  [???]    |
|          ...                           |
|  Progress: ████░░░░ 40%               |
|  Milestone tiếp: 15 → +7% ATK       |
|                                       |
+--------------------------------------+
```

#### 4.2.5. Milestone mẫu (Nhân vật)

| Mốc | Yêu cầu | Phần thưởng |
|-----|---------|-------------|
| 1 | 5 nhân vật | +2% ATK |
| 2 | 10 nhân vật | +5% ATK |
| 3 | 15 nhân vật | +7% ATK, +3% HP |
| 4 | 20 nhân vật | +10% ATK, +5% HP |
| Full | 30+ nhân vật | +15% ATK, +10% HP, +5% ASPD |

---

## 5. Thứ tự ưu tiên & Phụ thuộc

### Phase 1: UI/UX nền tảng
| Thứ tự | Task | Phụ thuộc |
|--------|------|-----------|
| 1 | Mobile-first UI Redesign | — |
| 2 | Upgradable Point Indicator | Phase 1.1 |
| 3 | AFK Lock Screen | Phase 1.1 |
| 4 | Continue Gacha | — |

### Phase 2: Hiệu ứng
| Thứ tự | Task | Phụ thuộc |
|--------|------|-----------|
| 1 | Point Click Effect | — |
| 2 | Stage Clear Effect | — |
| 3 | Boss Entrance Effect | — |

### Phase 3: Hệ thống mới
| Thứ tự | Task | Phụ thuộc |
|--------|------|-----------|
| 1 | Hub Tab | Phase 1.1 |
| 2 | Skill Tree (tách từ Prestige) | Phase 3.1 |
| 3 | Tàn tích vào Hub | Phase 3.1 |
| 4 | Collection System | Phase 3.1 |
