# Continue Gacha

> Cho phép gacha liên tiếp sau khi nhận item.

## Tổng quan

Trong popup kết quả gacha, thêm nút "Gacha tiếp" để gacha ngay lập tức.

## Chi tiết

| Tính năng | Mô tả |
|-----------|-------|
| **Nút "Gacha x1"** | Gacha tiếp 1 lần |
| **Nút "Gacha x10"** | Gacha tiếp 10 lần |
| **Auto-check** | Nếu không đủ currency → chuyển sang shop |
| **Skip animation** | Nút skip ở góc popup |
| **Batch** | Gacha nhiều lần → animation rút gọn dần |

## Luồng

```mermaid
flowchart LR
    A["Gacha"] --> B["Hiển thị kết quả"]
    B --> C{"Đủ currency?"}
    C -->|Có| D["Nút: Gacha tiếp x1 / x10"]
    C -->|Không| E["Nút: Đến Shop"]
    D --> A
```

## UI Layout

```
+----------------------------+
|     KẾT QUẢ GACHA          |
|   [Item 1] [Item 2] ...    |
|                            |
|  [Gacha x1] [Gacha x10]    |
|  [×] Skip Animation        |
+----------------------------+
```
