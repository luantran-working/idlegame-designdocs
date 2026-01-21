# Thiết kế âm thanh

Tài liệu này quy bản sắc âm thanh của trò chơi, bao gồm Nhạc nền (BGM), Âm thanh môi trường và Hiệu ứng âm thanh (SFX).

---

## 1. Bảng tóm tắt Âm thanh (Audio & Voice)

| Phân loại     | Mục tiêu       | Đặc tả âm thanh                                 | Vibe âm nhạc         |
| :------------ | :------------- | :---------------------------------------------- | :------------------- |
| **BGM**       | Màn hình chính | Đàn bầu mix Lo-fi beat.                         | Chill, thư giãn.     |
|               | Chiến đấu      | Sáo trúc mix Bass/Trap beat.                    | Hào hùng, hài hước.  |
| **Ambient**   | Chương 1       | Tiếng còi xe, tiếng rao hàng, chó sủa xa.       | Đời thường Việt Nam. |
|               | Chương 2       | Tiếng chợ xôn xao, tiếng dao thớt băm chặt.     | Xô bồ, náo nhiệt.    |
| **Voice Off** | Nhân vật       | Cụm từ ngắn: "Đỡ nè!", "Hú hồn chưa!", "Á đù!". | Hài hước, gần gũi.   |
| **UI SFX**    | Tương tác      | Tiếng phím cơ (Click), tiếng chuông (Success).  | Hiện đại, rõ ràng.   |

---

## 2. Định hướng chung (Audio Style Guide)

- **Vibe:** Hài hước, gần gũi, mang đậm hơi thở đời sống Việt Nam.
- **Chất liệu:** Kết hợp giữa nhạc cụ truyền thống (Đàn bầu, Sáo trúc, Đờn ca tài tử) với nhịp điệu hiện đại (Lo-fi, Hip-hop, Trap).

---

## 2. Nhạc nền (BGM)

| Khu vực                | Mood / Tâm trạng                                  | Nhạc cụ chủ đạo                           |
| :--------------------- | :------------------------------------------------ | :---------------------------------------- |
| **Màn hình chính**     | Thư giãn, nhẹ nhàng, "chill".                     | Đàn bầu (đi giai điệu) + Beat Lo-fi chậm. |
| **Chiến đấu (Thường)** | Hào hùng nhưng vui nhộn, nhịp nhanh.              | Sáo trúc + Trống da + Bass mạnh.          |
| **Đánh Boss**          | Kịch tính, dồn dập, có phần "nguy hiểm" hài hước. | Đàn nhị (kéo gắt) + Dubstep/Trap beat.    |
| **Gacha / Mở thưởng**  | Hồi hộp, lung linh.                               | Tiếng chuông (Chimes) + Harp.             |

---

## 3. Âm thanh môi trường (Ambient)

Mỗi chương có một bộ âm thanh nền đặc trưng (Layered Audio):

- **Chương 1 (Phố):** Tiếng còi xe xa xa, tiếng rao "Ai... bánh mì đây", tiếng chó sủa lầu bầu.
- **Chương 2 (Chợ):** Tiếng xì xào đám đông, tiếng dao băm thớt, tiếng mặc cả ("Bớt cho em đi chị").
- **Chương 3 (Công viên):** Tiếng chim hót, tiếng gió thổi qua lá cây, tiếng loa phường rè rè phát nhạc cổ điển.

---

## 4. Hiệu ứng âm thanh UI (UI SFX)

- **Click General:** Tiếng "Tách" nhẹ, thanh thoát (mô phỏng tiếng phím cơ hoặc bật nắp lon).
- **Confirm/Success:** Tiếng "Keng" vang, tươi sáng.
- **Cancel/Error:** Tiếng "Bộp" trầm, đục.
- **Tab Switch:** Tiếng "Soạt" (mô phỏng tiếng lật trang sách giấy).

---

## 5. Giọng nói nhân vật (Voice Off)

Sử dụng các câu thoại ngắn (Voice cues) mang đậm phong cách vùng miền:

- **Nhân vật chính:** "Zô nè!", "Đỡ nè con!", "Hú hồn chưa?".
- **Đồng đội:** (Theo đặc trưng từng người như đã mô tả trong tài liệu nhân vật).
- **Kẻ địch khi chết:** "Á đù!", "Tha em đại ca!", "Thôi xong...".
