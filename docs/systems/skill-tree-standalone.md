# Skill Tree — Cây kỹ năng độc lập

> Tách Skill Tree từ Prestige system thành màn hình riêng trong Hub Tab.

## Tổng quan

Skill Tree hiện tại nằm trong Hệ thống Prestige (he-thong-prestige.md). Tách ra màn riêng để dễ dàng mở rộng và truy cập.

## 4 nhánh kỹ năng (kế thừa từ Prestige)

| Nhánh | Tập trung | Skill mẫu |
|-------|-----------|-----------|
| **Tấn công** | ATK, CRIT, ASPD | +10% ATK, +5% Crit Rate |
| **Sinh tồn** | HP, DEF, HP Regen | +15% HP, +5% DEF |
| **Kinh tế** | Vàng, EXP, Drop rate | +20% Gold, +10% EXP |
| **Tiện ích** | AFK time, Inventory | +2h AFK, +10 Inventory |

## UI Layout

```
+--------------------------------------+
|          SKILL TREE                  |
|   [Tấn công] [Sinh tồn] [Kinh tế]   |  ← tab nhánh
+--------------------------------------+
|                                       |
|  [Skill 1] ████████░░░░ Lv 8/10     |
|  +10% ATK                            |
|  [Up] — Cost: 5 Prestige Point      |
|                                       |
|  [Skill 2] ██████░░░░░░ Lv 6/10     |
|  +5% Crit Rate                       |
|  [Locked] Yêu cầu Lv 5 Tấn công     |
|                                       |
+--------------------------------------+
|  Prestige Points: 25                |
+--------------------------------------+
```

> **Lưu ý:** Data skill tree chi tiết xem tại `he-thong-prestige.md`.
