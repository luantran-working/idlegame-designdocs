# Game Design

Đây là bộ tài liệu thiết kế game (Game Design Document - GDD) cho dự án game mobile Idle/AFK "Bảo vệ khu phố".

---

## Thông tin dự án

| Hạng mục               | Mô tả                                   |
| :--------------------- | :-------------------------------------- |
| **Tên game**           | Bảo vệ khu phố                          |
| **Thể loại**           | Idle/AFK RPG                            |
| **Nền tảng**           | Mobile (Android, iOS)                   |
| **Định dạng**          | Portrait (màn hình dọc), tỉ lệ 9:16     |
| **Art style**          | Cartoon 2D, hài hước, bối cảnh Việt Nam |
| **Phiên bản tài liệu** | 1.0                                     |
| **Cập nhật lần cuối**  | 20/01/2026                              |

---

## Danh sách tài liệu

### Tài liệu tổng quan

| Tài liệu                                         | Nội dung chính                                              |
| :----------------------------------------------- | :---------------------------------------------------------- |
| [Kế hoạch tổng thể](./ke-hoach-tong-the.md)      | Tổng quan dự án, storyline, core mechanics, layout overview |
| [Kế hoạch phát triển (Roadmap)](./roadmap.md)    | Roadmap, task breakdown, gantt chart, QA checklist          |

### Tài liệu thiết kế giao diện (UI/UX)

| Tài liệu                                                | Nội dung chính                                     |
| :------------------------------------------------------ | :------------------------------------------------- |
| [Các chức năng chính và bố cục](./cac-chuc-nang-chinh-va-bo-cuc.md) | Tổng quan layout, 5 tab chức năng, navigation flow |
| [Chi tiết màn hình chiến đấu](./chi-tiet-man-hinh-chien-dau.md)        | Battle screen design, HUD, VFX, art style          |
| [Chi tiết màn hình điều khiển](./chi-tiet-man-hinh-dieu-khien.md)                  | 5 tabs chi tiết, popup, interaction design         |

### Tài liệu gameplay

| Tài liệu                                                         | Nội dung chính                                           |
| :--------------------------------------------------------------- | :------------------------------------------------------- |
| [Chi tiết cơ chế gameplay](./chi-tiet-co-che-gameplay.md)                                                         | Core loop, combat system, stage structure, AFK mechanics |
| [Hệ thống chỉ số và tăng trưởng](./he-thong-chi-so-va-tang-truong.md) | Stats classification, formulas, balancing                |

### Tài liệu hệ thống

| Tài liệu                                                                         | Nội dung chính                                    |
| :------------------------------------------------------------------------------- | :------------------------------------------------ |
| [Hệ thống trang bị](./he-thong-trang-bi.md)     | Equipment types, rarity, upgrade mechanics, merge |
| [Hệ thống kỹ năng](./he-thong-ky-nang.md)           | Skill categories, skill list, deck building       |
| [Hệ thống đồng đội](./he-thong-dong-doi.md)      | Character classes, roster, bond system            |
| [Hệ thống kinh tế và tài nguyên](./he-thong-kinh-te-va-tai-nguyen.md) | Currencies, economy flow, monetization            |
| [Hệ thống gacha](./he-thong-gacha.md)                  | Banners, drop rates, pity system                  |

### Tài liệu thiết kế Assets (Art Specifications)

| Tài liệu                                                                    | Nội dung chính                                     |
| :-------------------------------------------------------------------------- | :------------------------------------------------- | --- |
| [Thiết kế nhân vật](./assets-design-spec/nhan-vat.md)               | Character concepts, animations, size specs         |
| [Thiết kế trang bị](./assets-design-spec/trang-bi.md)               | Weapon/Armor visuals, rarity borders, icons        |
| [Thiết kế vật phẩm & UI](./assets-design-spec/vat-pham-ui.md)       | Currency icons, UI elements, button styles         |
| [Thiết kế môi trường & VFX](./assets-design-spec/moi-truong-vfx.md) | Backgrounds per chapter, skill effects, UI effects |     |

---

## Hướng dẫn đọc tài liệu

### Cho lập trình viên (Developers)

1. Bắt đầu với **Kế hoạch tổng thể** để hiểu vision
2. Đọc **Chi tiết cơ chế gameplay** cho core loop
3. Đọc các **Hệ thống** liên quan đến feature đang làm
4. Tham khảo **Roadmap** để biết task breakdown

### Cho họa sĩ (Artists)

1. Đọc **Kế hoạch tổng thể** phần bối cảnh và art style
2. Đọc **Chi tiết màn hình chiến đấu** cho battle visuals
3. Đọc từng **Hệ thống** để biết asset cần làm

### Cho sound designer

1. Đọc **Chi tiết màn hình chiến đấu** cho combat SFX
2. Đọc **Hệ thống kỹ năng** cho skill SFX
3. Đọc **Hệ thống gacha** cho gacha SFX

### Cho game designer (Balancing)

1. Đọc **Hệ thống chỉ số và tăng trưởng** cho formulas
2. Đọc **Hệ thống kinh tế** cho economy balancing
3. Đọc **Hệ thống gacha** cho drop rates

---

## Quy ước tài liệu

### Định dạng

- Tất cả tài liệu sử dụng Markdown
- Biểu đồ sử dụng Mermaid (compatible với Mermaid 10.7.0+)
- Không sử dụng emoji trong nội dung
- Không sử dụng titlecase (viết "Phân loại phẩm chất" thay vì "Phân Loại Phẩm Chất")

### Cấu trúc mỗi tài liệu

1. **Tiêu đề** - Tên hệ thống/chức năng
2. **Tổng quan** - Mô tả ngắn gọn
3. **Chi tiết** - Bảng biểu, sơ đồ, thông số
4. **Hướng dẫn cho đội phát triển** - Ghi chú cụ thể cho dev/artist/sound

---

## Liên hệ

Nếu có câu hỏi về tài liệu, vui lòng liên hệ team lead hoặc tạo issue trên repository.
