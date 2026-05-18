# Upgradable Point Indicator

> Hiển thị trực quan khi tính năng có thể nâng cấp.

## Các loại indicator

| Loại | Mô tả | Vị trí |
|------|-------|--------|
| **Red dot** | Chấm đỏ nhỏ | Góc trên icon tab/item |
| **Glow** | Viền sáng | Quanh nút/item upgradeable |
| **Badge số** | Số lượng khả dụng | VD: tab Hero hiện "3" |
| **"Up!" text** | Chữ trên item | Item đạt điều kiện |

## Quy tắc hiển thị

- Chỉ hiển thị cho lần nâng cấp **đầu tiên có thể**
- Sau khi người chơi đã thấy → chuyển về red dot
- Priority: Badge > Red dot > Glow > Text

## Danh sách áp dụng

| Màn hình | Indicator | Điều kiện |
|---------|-----------|-----------|
| Bottom nav tab "Hero" | Badge | Có chỉ số có thể nâng cấp |
| Bottom nav tab "Equipment" | Badge | Có trang bị chưa mặc/cường hóa |
| Bottom nav tab "Gacha" | Red dot | Có vé gacha miễn phí |
| Skill tree | Red dot | Có skill point chưa dùng |
| Collection | Red dot | Có item mới unlock |
