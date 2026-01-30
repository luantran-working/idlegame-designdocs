# Game Design Document

Đây là bộ tài liệu thiết kế game (Game Design Document - GDD) cho dự án game mobile Idle/AFK "Bảo vệ khu phố".

---

## Thông tin dự án

| Hạng mục               | Mô tả                                                  |
| :--------------------- | :----------------------------------------------------- |
| **Tên game**           | Bảo vệ khu phố                                         |
| **Thể loại**           | Idle/AFK RPG                                           |
| **Nền tảng**           | Mobile (Android, iOS)                                  |
| **Định dạng**          | Portrait (màn hình dọc), tỉ lệ 9:16                    |
| **Art style**          | Cartoon 2D, hài hước, bối cảnh Việt Nam                |
| **Phiên bản tài liệu** | 2.0                                                    |
| **Cập nhật lần cuối**  | 30/01/2026                                             |
| **Bản chơi thử**       | [idle-game.test.iit.vn](https://idle-game.test.iit.vn) |

---

## Trải nghiệm game mẫu

Bạn có thể trải nghiệm trực tiếp bản game mẫu để hiểu rõ hơn về core loop và mechanic tại: **[https://idle-game.test.iit.vn](https://idle-game.test.iit.vn)**

---

## Danh sách tài liệu

### Tài liệu tổng quan

| Tài liệu                                                            | Nội dung chính                                                                   |
| :------------------------------------------------------------------ | :------------------------------------------------------------------------------- |
| [Kế hoạch tổng thể](./ke-hoach-tong-the.md)                         | Tổng quan dự án, cốt truyện, cơ chế cốt lõi, bố cục tổng quan, lộ trình thực thi |
| [Kế hoạch sản xuất chi tiết](./plan-timelines/ke-hoach-san-xuat.md) | Timeline, công việc theo bộ phận (Dev, Artist, VFX, Sound, Game Designer)        |
| [Quản lý dự án](./plan-timelines/quan-ly-du-an.md)                  | Milestones, QA checklists, rủi ro, quy trình quản lý                             |

### Tài liệu thiết kế giao diện

| Tài liệu                                                            | Nội dung chính                                      |
| :------------------------------------------------------------------ | :-------------------------------------------------- |
| [Các chức năng chính và bố cục](./cac-chuc-nang-chinh-va-bo-cuc.md) | Tổng quan layout, 5 tab chức năng, luồng điều hướng |
| [Chi tiết màn hình chiến đấu](./chi-tiet-man-hinh-chien-dau.md)     | Thiết kế visual chiến đấu, HUD, VFX, art style      |
| [Chi tiết màn hình điều khiển](./chi-tiet-man-hinh-dieu-khien.md)   | 5 tabs chi tiết, popup, thiết kế tương tác          |

### Tài liệu gameplay

| Tài liệu                                                              | Nội dung chính                                                      |
| :-------------------------------------------------------------------- | :------------------------------------------------------------------ |
| [Chi tiết cơ chế gameplay](./chi-tiet-co-che-gameplay.md)             | Vòng lặp cốt lõi, hệ thống chiến đấu, cấu trúc màn chơi, cơ chế AFK |
| [Hướng dẫn người chơi mới](./huong-dan-nguoi-choi-moi.md)             | Luồng tutorial, FTUE, quà tân thủ, hệ thống nhắc nhở                |
| [Hệ thống chỉ số và tăng trưởng](./he-thong-chi-so-va-tang-truong.md) | Phân loại chỉ số, công thức, cân bằng game                          |

### Tài liệu hệ thống

| Tài liệu                                                                  | Nội dung chính                                            |
| :------------------------------------------------------------------------ | :-------------------------------------------------------- |
| [Hệ thống trang bị](./he-thong-trang-bi.md)                               | Loại trang bị, phẩm chất, cơ chế nâng cấp, ghép đồ        |
| [Hệ thống kỹ năng](./he-thong-ky-nang.md)                                 | Phân loại kỹ năng, danh sách mẫu, xây dựng bộ kỹ năng     |
| [Hệ thống đồng đội](./he-thong-dong-doi.md)                               | Vai trò nhân vật, danh sách đồng đội, hệ thống duyên phận |
| [Hệ thống quái vật](./he-thong-quai-vat.md)                               | Phân loại Minion/Elite/Boss, AI hành vi và danh sách quái |
| [Hệ thống kinh tế và tài nguyên](./he-thong-kinh-te-va-tai-nguyen.md)     | Tiền tệ, dòng chảy kinh tế, chiến lược monetization       |
| [Hệ thống gacha](./he-thong-gacha.md)                                     | Các loại banner, tỉ lệ rơi, cơ chế bảo hiểm               |
| [Hệ thống nhiệm vụ và thành tựu](./he-thong-nhiem-vu.md)                  | Nhiệm vụ ngày/tuần, thành tựu, phần thưởng                |
| [Hệ thống Prestige](./he-thong-prestige.md)                               | Cơ chế tái sinh, cây kỹ năng prestige, bonus vĩnh viễn    |
| [Hệ thống Event](./he-thong-event.md)                                     | Sự kiện theo mùa, event thường xuyên, currency event      |
| [Hệ thống PvP/Arena](./he-thong-pvp-arena.md)                             | Đấu trường, xếp hạng, phần thưởng Arena                   |
| [Hệ thống Guild](./he-thong-guild.md)                                     | Bang hội, Guild Boss, Guild War, Guild perks              |
| [Hệ thống Battle Pass](./he-thong-battle-pass.md)                         | Thẻ chiến đấu, track miễn phí/premium, phần thưởng mùa    |
| [Hệ thống VIP](./he-thong-vip.md)                                         | Cấp độ VIP, đặc quyền, quà VIP hàng ngày                  |
| [Hệ thống công thức toán học](./he-thong-cong-thuc-toan-hoc/tong-quan.md) | Tổng hợp các công thức damage, scaling, gacha (chi tiết)  |

### Tài liệu kỹ thuật và cân bằng

| Tài liệu                                           | Nội dung chính                                    |
| :------------------------------------------------- | :------------------------------------------------ |
| [Bảng cân bằng kinh tế](./bang-can-bang-kinh-te.md) | Data tables, scaling formulas, economy simulation |
| [Kiến trúc kỹ thuật](./kien-truc-ky-thuat.md)       | Client/Server architecture, Save/Load, Anti-cheat |
| [Nội dung mở rộng](./noi-dung-mo-rong.md)           | Content roadmap, chương mới, tính năng tương lai  |

### Tài liệu thiết kế assets

| Tài liệu                                                              | Nội dung chính                                   |
| :-------------------------------------------------------------------- | :----------------------------------------------- |
| [Thiết kế nhân vật](./assets-design-spec/nhan-vat.md)                 | Concept nhân vật, animation, thông số kích thước |
| [Thiết kế quái vật](./assets-design-spec/quai-vat.md)                 | Concept kẻ địch (Humanoid), animation, hành vi   |
| [Thiết kế kỹ năng chính](./assets-design-spec/ky-nang.md)             | VFX/SFX cho kỹ năng nhân vật chính               |
| [Thiết kế kỹ năng đồng đội](./assets-design-spec/ky-nang-dong-doi.md) | VFX/SFX cho kỹ năng của 30 nhân vật đồng đội     |
| [Thiết kế trang bị](./assets-design-spec/trang-bi.md)                 | Hình ảnh vũ khí/giáp, khung phẩm chất, icon      |
| [Thiết kế môi trường](./assets-design-spec/moi-truong.md)             | Background theo chương, hệ thống Parallax        |
| [Thiết kế VFX chiến đấu](./assets-design-spec/vfx-chien-dau.md)       | Hiệu ứng sát thương, tình trạng nhân vật         |
| [Thiết kế VFX hệ thống](./assets-design-spec/vfx-ui-he-thong.md)      | Hiệu ứng Gacha, nâng cấp, luồng tiền tệ          |
| [Thiết kế âm thanh](./assets-design-spec/am-thanh.md)                 | BGM, Ambient, UI SFX và Voice Cues               |

---

## Hướng dẫn đọc tài liệu

### Cho lập trình viên (Developers)

1. Bắt đầu với **Kế hoạch tổng thể** để hiểu vision
2. Đọc **Chi tiết cơ chế gameplay** cho core loop
3. Đọc **Kiến trúc kỹ thuật** cho architecture và save/load
4. Đọc các **Hệ thống** liên quan đến feature đang làm
5. Tham khảo **Bảng cân bằng kinh tế** cho data tables

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
2. Đọc **Bảng cân bằng kinh tế** cho economy data tables
3. Đọc **Hệ thống kinh tế** cho economy flow
4. Đọc **Hệ thống gacha** cho drop rates
5. Đọc **Nội dung mở rộng** cho content roadmap

### Cho product manager

1. Đọc **Kế hoạch tổng thể** cho vision và target audience
2. Đọc **Hệ thống VIP** và **Battle Pass** cho monetization
3. Đọc **Bảng cân bằng kinh tế** cho revenue targets
4. Đọc **Nội dung mở rộng** cho feature roadmap

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
