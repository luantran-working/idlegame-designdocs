# Hub Tab — Trung tâm

> Tab riêng trong bottom nav, nơi tập trung Skill Tree và Tàn tích.

## Layout

```
+--------------------------------------+
|            TRUNG TÂM                 |
+--------------------------------------+
|                                       |
|  ╔══════════════╗ ╔══════════════╗  |
|  ║  Skill Tree  ║ ║   Tàn tích   ║  |
|  ║  Cây kỹ năng ║ ║  Đập bình   ║  |
|  ╚══════════════╝ ╚══════════════╝  |
|                                       |
|  [Nút: Main Hero →]                  |
+--------------------------------------+
```

## Chi tiết

- **Vị trí**: Tab thứ 3 trong bottom nav (hiện tại 5 tab → thêm tab thứ 6)
- **Nội dung**: 2 card lớn dạng button dẫn đến màn hình con
- **Card Skill Tree**: Icon + tên + preview số skill point khả dụng
- **Card Tàn tích**: Icon + tên + preview số búa hiện có
- **Nút phụ**: Chuyển nhanh đến Main Hero

## Navigation sau khi chọn

| Tap vào | Đi đến |
|---------|--------|
| Card Skill Tree | Màn hình Skill Tree (docs/systems/skill-tree-standalone) |
| Card Tàn tích | Màn hình Tàn tích (đã có trong he-thong-thanh-vat) |
| Nút Main Hero | Màn hình Main Hero |
