# SS6-Ex1: Viết Acceptance Criteria và Definition of Done

## 1. Giả định chung

- Thư viện giữ sách đã đặt trong **48 giờ**.
- Một độc giả được mượn tối đa **5 cuốn cùng lúc**.
- Nếu sách hết, độc giả không thể đặt mượn trực tiếp nhưng có thể chờ thông báo khi sách có lại.

## 2. Acceptance Criteria

### Story 1

Là một độc giả, tôi muốn đặt mượn online một cuốn sách đang có sẵn để không phải đến thư viện rồi mới biết sách đã có người mượn.

| AC# | Loại | Given | When | Then |
|---|---|---|---|---|
| 1.1 | Happy | Độc giả đã đăng nhập và sách còn ít nhất 1 bản có sẵn | Độc giả bấm “Đặt mượn” | Hệ thống tạo phiếu đặt mượn, giảm số bản có sẵn và hiện hạn giữ sách 48 giờ. |
| 1.2 | Negative | Sách không còn bản có sẵn | Độc giả bấm “Đặt mượn” | Hệ thống không tạo phiếu và thông báo “Sách hiện đã hết”. |
| 1.3 | Edge | Sách chỉ còn đúng 1 bản | Hai độc giả cùng bấm “Đặt mượn” gần như cùng lúc | Chỉ một người nhận được phiếu thành công; người còn lại nhận thông báo sách đã hết. |

**Câu hỏi làm rõ cho PO:** Khi độc giả không đến nhận trong 48 giờ, phiếu có tự hủy và trả sách về trạng thái có sẵn không?

### Story 2

Là một độc giả, tôi muốn nhận thông báo khi sách đã đặt trước có sẵn để kịp đến nhận trước khi hết thời gian giữ chỗ.

| AC# | Loại | Given | When | Then |
|---|---|---|---|---|
| 2.1 | Happy | Độc giả đang chờ một cuốn sách hết hàng và đã đăng ký nhận thông báo | Thủ thư cập nhật cuốn sách thành có sẵn | Hệ thống gửi thông báo cho độc giả và hiển thị thời hạn giữ sách 48 giờ. |
| 2.2 | Negative | Độc giả chưa đăng ký nhận thông báo cho cuốn sách | Thủ thư cập nhật sách thành có sẵn | Hệ thống không gửi thông báo cho độc giả đó. |
| 2.3 | Edge | Có nhiều độc giả cùng chờ một cuốn sách và chỉ có 1 bản được trả | Sách chuyển sang trạng thái có sẵn | Hệ thống thông báo theo thứ tự đăng ký và chỉ giữ bản sách cho người đầu tiên xác nhận. |

**Câu hỏi làm rõ cho PO:** Thông báo được gửi bằng email, thông báo trong hệ thống, hay cả hai?

### Story 3

Là một thủ thư, tôi muốn giới hạn số sách một độc giả được mượn cùng lúc để tránh một người giữ hết sách.

| AC# | Loại | Given | When | Then |
|---|---|---|---|---|
| 3.1 | Happy / Ràng buộc nghiệp vụ | Độc giả đang mượn 4 cuốn và chưa có khoản phạt | Độc giả đặt thêm 1 cuốn có sẵn | Hệ thống cho phép đặt và tổng số sách đang mượn là 5 cuốn. |
| 3.2 | Negative / Ràng buộc nghiệp vụ | Độc giả đang mượn đủ 5 cuốn | Độc giả đặt thêm một cuốn | Hệ thống từ chối, không tạo phiếu và hiện thông báo “Bạn đã đạt giới hạn 5 cuốn”. |
| 3.3 | Edge | Độc giả đang mượn 5 cuốn nhưng một cuốn đã quá hạn | Độc giả cố đặt thêm sách | Hệ thống vẫn từ chối và hướng dẫn độc giả trả sách quá hạn trước. |

**Câu hỏi làm rõ cho PO:** Sách đang chờ nhận có được tính vào giới hạn 5 cuốn hay chỉ tính các sách đã nhận tại quầy?

## 3. Definition of Done chung

Definition of Done này áp dụng cho cả ba story, không phải tiêu chí riêng của từng story.

- Acceptance Criteria đã được Product Owner và Developers thống nhất.
- Code đã được một thành viên khác review.
- Có test cho luồng chính, trường hợp lỗi và trường hợp biên quan trọng.
- Test tự động và test thủ công đều đạt.
- Không còn lỗi nghiêm trọng liên quan đến story.
- Nội dung hiển thị và thông báo đã được kiểm tra trên giao diện.
- Tài liệu hướng dẫn hoặc ghi chú cần thiết đã được cập nhật.
- Product Owner đã xem Increment và chấp nhận kết quả.
- Tính năng đã được đưa lên môi trường kiểm thử để có thể dùng thử.

## 4. Story 1 đã Done chưa?

Chưa. Story 1 đã đạt các Acceptance Criteria nhưng code chưa được review theo Definition of Done chung. Vì DoD là điều kiện bắt buộc cho mọi Product Backlog Item, story chỉ được coi là Done sau khi review và các tiêu chí còn lại cũng hoàn thành.
