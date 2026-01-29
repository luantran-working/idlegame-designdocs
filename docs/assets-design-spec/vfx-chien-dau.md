# Thiết kế hiệu ứng chiến đấu

Tài liệu này quy định chi tiết về các hiệu ứng thị giác xảy ra trong quá trình chiến đấu (Hành động, Sát thương, Hiệu ứng trạng thái).

---

## 1. Bảng tóm tắt VFX Chiến đấu

| Loại VFX            | Hiệu ứng cụ thể | Mô tả hình ảnh nhanh                            | Cảm giác (Game Feel) | Ghi chú            |
| :------------------ | :-------------- | :---------------------------------------------- | :------------------- | :----------------- |
| **Tác động (Hit)**  | Đánh thường     | Tia lửa trắng/vàng bắn ra, vệt cắt mờ.          | Gọn, dứt khoát.      | Làm trước bản demo |
|                     | Chí mạng (Crit) | Nổ cam đỏ rực rỡ, rung màn hình nhẹ, chữ "BÙM". | Uy lực, phấn khích.  | Làm trước bản demo |
| **Trạng thái (CC)** | Choáng (Stun)   | Vòng xoáy vàng và sao bay quanh đầu.            | Bị động, đứng im.    | Làm trước bản demo |
|                     | Độc/Cháy        | Bong bóng xanh lá / Lửa bốc lên trên người.     | Sát thương duy trì.  | Làm trước bản demo |
| **Tầm xa**          | Đạn bay         | Vệt sáng (Trail) kéo dài theo quỹ đạo đạn.      | Tốc độ, định hướng.  | Làm trước bản demo |
| **Phòng thủ**       | Khiên chặn      | Vòng tròn năng lượng mờ hiện lên khi bị đánh.   | Vững chãi, an toàn.  | Làm trước bản demo |

---

## 2. Hiệu ứng va chạm (Hit Impact)

Đây là hiệu ứng quan trọng nhất để tạo cảm giác "lực" (Game Feel).

| Loại hit                     | Visual                                                                                        | Decal / Hiệu ứng phụ                                                              | Ghi chú            |
| :--------------------------- | :-------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------- | :----------------- |
| **Normal Hit (Đánh thường)** | Tia lửa (Sparks) màu trắng xanh hoặc vàng sáng tóe ra. Hình dạng tia chớp nhọn, kéo dài 0.2s. | Xuất hiện một vệt cắt (Slash) hoặc vết lõm mờ trên người mục tiêu trong tích tắc. | Làm trước bản demo |
| **Critical Hit (Chí mạng)**  | Nổ lớn màu vàng cam rực rỡ (Explosion).                                                       | Chữ "BÙM" hoặc số lớn, màn hình rung nhẹ (Screen Shake) trong 0.1s.               | Làm trước bản demo |

---

## 2. Hiệu ứng trạng thái (Status VFX)

Áp dụng khi kẻ địch hoặc nhân vật chính dính debuff/buff.

### 2.1. Gây hại (Debuffs)

| Trạng thái          | Mô tả hình ảnh                                                                                    | Ghi chú            |
| :------------------ | :------------------------------------------------------------------------------------------------ | :----------------- |
| **Choáng (Stun)**   | Vòng tròn xoắn ốc màu vàng quay trên đầu. Các ngôi sao nhỏ bay quanh.                             | Làm trước bản demo |
| **Độc (Poison)**    | Bong bóng màu xanh lục bốc lên từ kẽ chân. Nhân vật nhấp nháy màu xanh lá nhạt theo nhịp mất máu. | Làm trước bản demo |
| **Cháy (Burn)**     | Ngọn lửa nhỏ bốc lên từ người nhân vật. Màu cam đỏ chủ đạo.                                       | Làm trước bản demo |
| **Làm chậm (Slow)** | Hào quang màu xanh dương nhạt bao phủ, có các vệt băng giá mờ dưới chân.                          | Làm trước bản demo |

### 2.2. Có lợi (Buffs)

| Trạng thái              | Mô tả hình ảnh                                                                                              | Ghi chú            |
| :---------------------- | :---------------------------------------------------------------------------------------------------------- | :----------------- |
| **Hồi máu (Heal)**      | Hào quang xanh lá bốc lên từ dưới chân. Có các dấu cộng (+) và trái tim nhỏ bay lên rồi mờ dần.             | Làm trước bản demo |
| **Gồng sức (Power Up)** | Aura lửa màu xanh dương hoặc vàng bùng lên phía sau lưng (theo phong cách Super Saiyan nhưng hài hước hơn). | Làm trước bản demo |

---

## 3. Hiệu ứng kết liễu (Death VFX)

Khi quái vật HP về 0.

| Loại Death          | Mô tả hiệu ứng                                                                   | Ghi chú            |
| :------------------ | :------------------------------------------------------------------------------- | :----------------- |
| **VFX 1 (Default)** | Quái vật biến thành một đám khói trắng "Bụpppp" rồi biến mất.                    | Làm trước bản demo |
| **VFX 2 (Rich)**    | Quái vật vỡ tung thành các đồng xu vàng bay về phía người chơi.                  |                    |
| **VFX 3 (Boss)**    | Một vụ nổ lớn, màn hình chuyển trắng trong 0.5s, sau đó các rương báu xuất hiện. | Làm trước bản demo |

---

## 4. Hệ thống số sát thương (Damage Numbers)

| Loại sát thương       | Visual Style                                                   |
| :-------------------- | :------------------------------------------------------------- |
| **Sát thương vật lý** | Màu trắng, font chữ dày, có viền đen.                          |
| **Sát thương phép**   | Màu xanh tím, có hiệu ứng phát sáng (Glow).                    |
| **Hồi máu**           | Màu xanh lá cây, di chuyển từ dưới lên trên và lướt sang phải. |
| **Miss/Né tránh**     | Chữ "XỊT" màu xám, bay lướt ngang nhanh.                       |

---

## 5. Hiệu ứng đạn & tầm xa (Projectile VFX)

| Thành phần          | Mô tả                                                                                                                        | Ghi chú            |
| :------------------ | :--------------------------------------------------------------------------------------------------------------------------- | :----------------- |
| **Vệt đạn (Trail)** | Một dải màu mờ ảo kéo dài sau vật thể bay (ví dụ: dép lào, gạch, bi). Màu sắc: Lưu huỳnh/trắng cho vật lý, neon cho kỹ năng. | Làm trước bản demo |
| **Muzzle Flash**    | Một đốm sáng nhỏ nơi bắt đầu phát bắn để báo hiệu đòn tấn công từ xa.                                                        | Làm trước bản demo |

## 6. Hiệu ứng vùng (AOE & Indicator VFX)

| Loại hiệu ứng                        | Mô tả                                                                                                 | Ghi chú            |
| :----------------------------------- | :---------------------------------------------------------------------------------------------------- | :----------------- |
| **Vòng cảnh báo (Danger Zone)**      | Vòng tròn hoặc hình chữ nhật màu đỏ nhấp nháy trên mặt sàn 0.5s trước khi kỹ năng của quái dội xuống. | Làm trước bản demo |
| **Vòng hiệu ứng (Buff/Debuff Aura)** | Vòng hào quang nét đứt bao quanh dưới chân nhân vật đang chịu ảnh hưởng của Aura.                     | Làm trước bản demo |

## 7. Hiệu ứng phòng thủ & đặc biệt (Special VFX)

| Loại hiệu ứng                 | Mô tả                                                                                                |
| :---------------------------- | :--------------------------------------------------------------------------------------------------- |
| **Đỡ đòn (Parry/Block)**      | Hiệu ứng "Keng" kèm theo các mảnh vỡ kim loại bắn ra, nhân vật hơi lùi lại 1px để tạo cảm giác nặng. |
| **Hút máu (Lifesteal/Drain)** | Một tia sáng đỏ từ kẻ địch bay về phía nhân vật hiện tại.                                            |
| **Vỡ giáp (Shield Break)**    | Hiệu ứng các mảnh kính vỡ vụn bay ra kèm theo icon [Giáp gạch chéo] trên đầu địch.                   |
