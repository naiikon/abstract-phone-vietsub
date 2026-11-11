# Abstract外置手机 – bản Việt hóa (dùng riêng)

Bản Việt hóa **giao diện + prompt AI** của *Abstract外置手机* (【文中穿插消息 V6.0】), phone script cho SillyTavern (cần Tavern Helper / 酒馆助手).

- Tác giả gốc: **Abstract**, đăng trên Discord 类脑/旅程. Mọi công sức thiết kế thuộc về tác giả.
- Theo điều khoản của tác giả: bản sửa không dùng thương mại. Repo này chỉ để tự dùng.
- Dựa trên bản `phone-ctn.pages.dev/index.js` (V6.0, bản cuối tác giả cập nhật tháng 1–2/2026).

## Cài đặt
Import file `Abstract-phone-vietsub.json` vào Tavern Helper → Script, hoặc tạo script mới với nội dung:

```js
import 'https://naiikon.github.io/abstract-phone-vietsub/index.js'
```

Tắt script gốc (bản tiếng Trung) để tránh chạy 2 phone cùng lúc.

## Những chỗ cố ý giữ tiếng Trung
Code phân tích output của AI bằng các chữ này, nên phải giữ nguyên:
- Định dạng ngày `X年X月X日` và thứ `星期一…`
- Cú pháp nhãn world book: `<前置>`, `<后置>`, `<人物|…>`, `<页面|…>`
- Tên các mục world book / regex script phone tự tạo (`[auto_message]主动发消息指令`, `手机-消息美化`…) để không tạo trùng với mục cũ
- Tiền tố `群:` khi chèn tin nhắn nhóm trong truyện, tên dự phòng `用户`

## Thay đổi riêng so với bản gốc
- Thông báo ước tính số token mỗi lần điện thoại gọi AI.
- Ẩn app Âm nhạc, Máy ảnh, Lịch, Nhật ký khỏi màn hình chính.
- Thêm 2 app (ý tưởng từ 兔k机 EPhone, code viết lại): **Xem điện thoại** (tin nhắn NPC, giỏ hàng, ghi chú, trình duyệt, album, ví, dấu chân, nhật ký sử dụng, nhật ký) và **Không gian tình nhân** (lời nhắn, album, thư). Dữ liệu lưu trong biến chat `ab_tuk` (riêng từng đoạn chat).
