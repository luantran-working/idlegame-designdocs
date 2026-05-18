# Mobile-first UI Redesign

> Chiến lược redesign giao diện tối ưu cho thiết bị di động.

## Nguyên tắc thiết kế

| Nguyên tắc | Chi tiết |
|-----------|---------|
| **Touch targets** | Nút tối thiểu 48x48px, khuyến nghị 56x56px |
| **Spacing** | Padding 16px tối thiểu từ viền |
| **1-hand zone** | Thao tác chính ở nửa dưới màn hình |
| **Font size** | Tối thiểu 14px content, 18px label |
| **Bottom nav** | Thanh điều khiển dưới cùng |
| **Gestures** | Swipe chuyển tab, long-press xem chi tiết |

## Danh sách màn hình cần chỉnh sửa

1. **Màn hình chính** — Gom thông tin, nút lớn hơn
2. **Màn hình chiến đấu** — HUD thu gọn, thanh máu dễ đọc
3. **Popup** — Bottom sheet thay vì center popup (dễ thao tác 1 tay)
4. **Inventory** — Grid view với item size lớn hơn
5. **Bottom nav** — 5 tab tối đa, icon + label

## Spec cho UI Developer

- Breakpoint: 360px (nhỏ nhất support)
- Safe area: Respect notch/cutout
- Touch debounce: 300ms
- Scroll: Momentum scrolling
