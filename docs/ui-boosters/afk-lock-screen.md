# AFK Lock Screen

> Màn hình khóa tự động khi người chơi AFK lâu.

## Tổng quan

Khi người chơi không tương tác ≥ 5 phút, màn hình tự động khóa.

## Luồng hoạt động

```mermaid
flowchart TD
    A["Player inactive 5 phút"] --> B["Màn tối dần (1s)"]
    B --> C["AFK Overlay hiển thị"]
    C --> D["Tài nguyên AFK hiển thị real-time"]
    D --> E{"Player tap 3 lần?"}
    E -->|Chưa đủ| D
    E -->|Đủ| F["Overlay biến mất"]
    F --> G["Game tiếp tục"]
```

## Chi tiết

| Thành phần | Giá trị |
|-----------|---------|
| **Timeout** | 5 phút |
| **Overlay** | Animation tối dần + nhân vật ngủ gật |
| **Hiển thị** | Thời gian AFK, tài nguyên đã farm |
| **Mở khóa** | Swipe hoặc tap 3 lần |
| **Tắt** | Có thể tắt trong Settings |

## Yêu cầu kỹ thuật

- Timer: Reset khi có touch/click event
- Resource calculation: Tính toán dựa trên idle earning rate
- Animation: Character idle sleep animation (looping)
- Transition: 1s fade in / 0.5s fade out
