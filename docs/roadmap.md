# Kế hoạch chi tiết thực hiện

Tài liệu này vạch ra lộ trình thực thi dự án game "Bảo vệ khu phố". Phát triển theo mô hình các khối chức năng (work blocks).

---

## 1. Nguyên tắc thực thi

| Hạng mục           | Mô tả                                                     |
| :----------------- | :-------------------------------------------------------- |
| **Tên chiến dịch** | "Một phát ăn ngay" (One-shot release)                     |
| **Mục tiêu**       | Hoàn thiện toàn bộ tính năng trong một quy trình liên tục |
| **Phương pháp**    | Agile development với sprint 2 tuần                       |
| **Kiểm thử**       | Test liên tục ngay sau khi hoàn thành từng tính năng      |

---

## 2. Tổng quan các khối công việc

```mermaid
flowchart LR
    A["BLOCK A<br/>Nền móng - 2 tuần"] --> B["BLOCK B<br/>Sức mạnh - 3 tuần"]
    B --> C["BLOCK C<br/>Meta Game - 2 tuần"]
    C --> D["BLOCK D<br/>Kinh tế - 2 tuần"]
    D --> E["BLOCK E<br/>Polish - 2 tuần"]

    style A fill:#e8f5e9,stroke:#2e7d32
    style B fill:#e3f2fd,stroke:#1565c0
    style C fill:#fff3e0,stroke:#ef6c00
    style D fill:#fce4ec,stroke:#c2185b
    style E fill:#f3e5f5,stroke:#7b1fa2
```

---

## 3. Block A: Nền móng và core gameplay

**Mục tiêu:** Nhân vật tự đánh, quái chết, rớt vàng.

| Công việc     | Thời gian | Deliverable                        |
| :------------ | :-------- | :--------------------------------- |
| Project setup | 2 ngày    | Github repo, Unity project         |
| Data layer    | 3 ngày    | ScriptableObjects, Save/Load       |
| Combat loop   | 3 ngày    | Player, Enemy, Damage system       |
| Game loop     | 2 ngày    | Stage system, Boss, Victory/Defeat |

---

## 4. Block B: Hệ thống sức mạnh

**Mục tiêu:** Người chơi có chỗ tiêu vàng và mạnh lên.

| Công việc     | Thời gian | Deliverable          |
| :------------ | :-------- | :------------------- |
| UI Framework  | 3 ngày    | 5 Tab, Popup system  |
| Upgrade Stats | 3 ngày    | Logic nâng chỉ số    |
| Inventory     | 5 ngày    | Equip/Merge system   |
| AFK System    | 2 ngày    | Offline reward       |
| Currency      | 2 ngày    | Gold/Diamond manager |

---

## 5. Block C: Meta game

**Mục tiêu:** Skill và đồng đội.

| Công việc       | Thời gian | Deliverable             |
| :-------------- | :-------- | :---------------------- |
| Skill System    | 5 ngày    | Skill manager, 5 skills |
| Teammate System | 5 ngày    | AI, Formation, Upgrade  |

---

## 6. Block D: Kinh tế và gacha

**Mục tiêu:** Hệ thống monetization.

| Công việc | Thời gian | Deliverable            |
| :-------- | :-------- | :--------------------- |
| Balancing | 3 ngày    | Drop tables, Formulas  |
| Gacha     | 5 ngày    | 3 banners, Pity system |
| Shop      | 2 ngày    | Item shop              |

---

## 7. Block E: Polish

**Mục tiêu:** Hoàn thiện audio, VFX, tutorial.

| Công việc    | Thời gian | Deliverable        |
| :----------- | :-------- | :----------------- |
| Audio        | 3 ngày    | SFX, BGM           |
| VFX          | 3 ngày    | Particles, Effects |
| Tutorial     | 2 ngày    | Hand pointing      |
| Optimization | 2 ngày    | Performance        |

---

## 8. Biểu đồ Gantt

```mermaid
gantt
    dateFormat YYYY-MM-DD
    title Lộ trình phát triển

    section Block A
    Setup           :a1, 2026-01-15, 2d
    Data            :a2, after a1, 3d
    Combat          :a3, after a2, 3d
    Game Loop       :a4, after a3, 2d

    section Block B
    UI Framework    :b1, after a4, 3d
    Stats           :b2, after b1, 3d
    Inventory       :b3, after b2, 5d
    AFK             :b4, after b3, 2d

    section Block C
    Skills          :c1, after b4, 5d
    Teammates       :c2, after c1, 5d

    section Block D
    Gacha           :d1, after c2, 5d
    Shop            :d2, after d1, 2d

    section Block E
    Audio VFX       :e1, after d2, 4d
    Final           :e2, after e1, 3d
```

---

## 9. QA Checklist

| Hạng mục  | Yêu cầu                   |
| :-------- | :------------------------ |
| Stability | Không crash 30 phút       |
| Save      | Không mất data            |
| AFK       | Tính đúng                 |
| Gacha     | Đúng tỉ lệ                |
| UI        | Hiển thị tốt mọi màn hình |
