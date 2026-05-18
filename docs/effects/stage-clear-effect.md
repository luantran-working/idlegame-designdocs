# Hiệu ứng Stage Clear

> Mô tả hiệu ứng khi người chơi vượt qua màn.

## Tổng quan

Khi tiêu diệt hết wave quái trong màn, phát animation stage clear.

## Chi tiết hiệu ứng

| Thành phần | Mô tả |
|-----------|-------|
| **Text "Clear!"** | Chữ lớn phóng to từ giữa màn hình, màu vàng gold, có glow |
| **Particle burst** | Hiệu ứng sao/tia sáng bắn ra từ center |
| **Rewards popup** | Danh sách phần thưởng trượt từ dưới lên (vàng, exp, item drop) |
| **Duration** | 1.5s — tự động chuyển màn tiếp |
| **Skip** | Tap anywhere để bỏ qua |

## Yêu cầu kỹ thuật

- Animation: Scale từ 0 → 1.2 → 1.0 (easeOutBack)
- Particle: 20-30 tia sáng, thời gian sống 1s
- Rewards: Dạng list, mỗi dòng slide-up cách nhau 0.1s
- Skip: Ngay lập tức tắt animation + chuyển màn
