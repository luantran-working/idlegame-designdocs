# Hiệu ứng Boss xuất hiện

> Mô tả hiệu ứng khi boss xuất hiện ở đầu wave cuối.

## Tổng quan

Khi wave boss bắt đầu, phát hiệu ứng entrance.

## Chi tiết hiệu ứng

| Thành phần | Mô tả |
|-----------|-------|
| **Screen shake** | Rung nhẹ 0.3s |
| **Dark overlay** | Overlay đen + spotlight vào vị trí boss |
| **Boss intro** | Animation boss xuất hiện (hạ cánh/trồi lên) |
| **Boss name + HP bar** | Text tên + thanh máu ở top |
| **Duration** | 1.0s — không skip được |

## Yêu cầu kỹ thuật

- Screen shake: Random offset ±5px trên trục XY, giảm dần
- Dark overlay: Alpha từ 0 → 0.6 trong 0.3s
- Boss intro: Phụ thuộc vào animation của từng boss
- HP bar: Xuất hiện sau intro 0.3s
