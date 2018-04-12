Semantic Versioning 2.0.0
==============================

Đặc tả phiên bản Semantic (SemVer)
------------------------------------------

Các từ khóa như "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", và "OPTIONAL" trong tài liệu này được hiểu như mô tả trong [RFC 2119](http://tools.ietf.org/html/rfc2119).

1. Phần mềm đang sử dụng Semantic Versioning MUST khai báo một API public. API này
cần phải được khai báo trong code của chính nó hoặc tồn tại nghiêm ngặt trong tài liệu.
Tuy nhiên nó được thực hiện, nó cần phải chính xác và toàn diện.

2. Một số phiên bản bình thường PHẢI ~~mang hình thức~~ **có dạng** X.Y.Z ~~nơi mà~~ **trong đó** X, Y, và Z là
số ~~nguyên dương~~ **không âm**, và KHÔNG ĐƯỢC ~~chứa số~~ bắt đầu là 0. X là phiên bản chính, Y là phiên bản nhỏ, và Z là phiên bản vá.
mỗi phần tử phải là số tự tăng. Ví dụ: 1.9.0 -> 1.10.0 -> 1.11.0.

3. Một khi các gói phiên bản đã được phát hành, nội dung của phiên bản đó không thể chỉnh sửa. Bất kỳ sửa đổi nào Phải được công bố như phiên bản mới.

4. Phiên bản chính số 0  (0.y.z) là để phát triển ban đầu. Mọi thứ CÓ THỂ sửa đổi ở mọi lục. API công cộng KHÔNG NÊN coi là ổn định.

5. Phiên bản 1.0.0 định nghĩa API công cộng. Cách thức tăng số phiên bản sau khi ra mắt phụ thuộc vào API công cộng này và nó thay đổi như thế nào.

6. Phiên bản vá Z (x.y.Z | x > 0) Phải được tăng lên nếu một bản sửa lỗi tương thích ngược lại với bản cũ được giới thiệu. Một lỗi được sửa được định nghĩa như thay đổi bên trong để sửa chữa những hành vi không chính xác.

7. Phiên bản nhỏ Y (x.Y.z | x > 0) Phải được tăng, nếu có 1 chức năng mới nhưng vẫn tương thích được giới thiệu đến API công khai.Nó phải được tăng nếu bất kỳ chưc năng API công khai nào được đánh dấu yêu cầu.Nó có thể được tăng lên nếu các tính năng hoặc cải tiến đáng kể mới được giới thiệu trong mã riêng.Nó CÓ THỂ bao gồm các thay đổi mức vá. Phiên bản vá PHẢI được đặt lại thành 0 khi phiên bản nhỏ được tăng lên.

8. Phiên bản chính X (X.y.z | X > 0) Phải được tăng lên nếu có bất kỳ thay đổi tương thích ngược nào được giới thiệu với API công khai. Nó cũng có thể bao gồm các thay đổi mức độ nhỏ và vá. Bản vá lỗi và phiên bản phụ PHẢI được đặt lại thành 0 khi phiên bản chính được tăng lên.

9. Một phiên bản tiền phát hành có thể được ký hiệu bằng cách thêm dấu nối và một chuỗi số nhận dạng dấu chấm ngay sau phiên bản vá lỗi. Các số nhận dạng PHẢI chỉ bao gồm alphanumerics và dấu gạch nối ASCII [0-9A-Za-z-]. Số nhận dạng PHẢI KHÔNG trống. Các số nhận dạng số không được bao gồm các số 0 trước. Các phiên bản tiền phát hành có mức ưu tiên thấp hơn phiên bản bình thường liên quan. Một phiên bản tiền phát hành cho thấy rằng phiên bản không ổn định và có thể không đáp ứng các yêu cầu về tính tương thích dự định được biểu thị bằng phiên bản bình thường liên quan của nó. Ví dụ: 1.0.0-alpha, 1.0.0-alpha.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

10. Xây dựng siêu dữ liệu CÓ THỂ được biểu thị bằng cách nối thêm dấu cộng và một loạt các ký hiệu nhận dạng dấu chấm ngay lập tức sau bản vá hoặc phiên bản tiền phát hành. Các số nhận dạng PHẢI chỉ bao gồm alphanumerics và dấu gạch nối ASCII [0-9A-Za-z-]. Số nhận dạng PHẢI KHÔNG trống. Xây dựng siêu dữ liệu PHẢI được bỏ qua khi xác định ưu tiên của phiên bản. Vì vậy, hai phiên bản khác nhau chỉ trong xây dựng siêu dữ liệu, có cùng ~~một~~ **mức độ** ưu tiên. Ví dụ: 1.0.0-alpha + 001, 1.0.0 + 20130313144700, 1.0.0-beta + exp.sha.5114f85.

11. Sự ưu tiên đề cập đến cách các phiên bản được so sánh với nhau khi được yêu cầu. Ưu tiên phải được tính bằng cách tách phiên bản thành các số nhận diện chính, nhỏ, vá và tiền phát hành theo thứ tự đó (Xây dựng siêu dữ liệu không được ưu tiên). Ưu tiên được xác định bởi sự khác biệt đầu tiên khi so sánh mỗi số nhận diện từ trái sang phải như sau: Các phiên bản chính, nhỏ và vá thường được so sánh về số lượng. Ví dụ: 1.0.0 <2.0.0 <2.1.0 <2.1.1. Khi **phiên bản chính**~~lớn~~, nhỏ, và vá bằng nhau, một phiên bản ~~trước khi~~ **tiền** phát hành có mức độ ưu tiên thấp hơn so với một phiên bản bình thường. Ví dụ: 1.0.0-alpha <1.0.0. Ưu tiên cho hai phiên bản trước khi phát hành với cùng một phiên bản chính, nhỏ và vá lỗi phải được xác định bằng cách so sánh từng mã nhận dạng được phân tách từ trái sang phải cho đến khi tìm thấy một sự khác biệt như sau: chỉ số xác định bao gồm các chữ số được so sánh số và số nhận dạng với chữ cái hoặc dấu gạch ngang được so sánh lexically theo thứ tự sắp xếp ASCII. Các số nhận dạng số luôn luôn có thứ tự ưu tiên thấp hơn số nhận diện không phải là số. Một tập hợp các trường tiền phát hành lớn hơn có độ ưu tiên cao hơn tập nhỏ hơn, nếu tất cả các số nhận dạng trước đó đều bằng nhau. Ví dụ: 1.0.0-alpha <1.0.0-alpha.1 <1.0.0-alpha.beta <1.0.0-beta <1.0.0-beta.2 <1.0.0-beta.11 <1.0.0- rc.1 <1.0.0.


Tại sao lại sử dụng Semantic Versioning?
----------------------------

Đây không phải là một ý tưởng mới hay cách mạng. Trên thực tế, có thể bạn đã làm gì đó gần đây. Vấn đề là "gần" không đủ tốt. Nếu không tuân thủ một số loại đặc tả chính thức, số phiên bản chủ yếu không có ích cho quản lý phụ thuộc. Bằng cách đặt tên và định nghĩa rõ ràng cho những ý tưởng trên, sẽ dễ dàng truyền đạt ý định của bạn cho người dùng phần mềm của bạn. Một khi các ý định này là rõ ràng, cuối cùng có thể được tạo ra đặc điểm phụ thuộc (nhưng không quá linh hoạt).

Một ví dụ đơn giản sẽ cho thấy Làm thế nào Semantic Versioning có thể làm cho sự phụ thuộc địa ngục là một điều của quá khứ. Xem xét một thư viện có tên "Firetruck". Nó đòi hỏi một gói có phiên bản có tính ngữ nghĩa có tên "Ladder". Vào thời điểm Firetruck được tạo ra, Ladder ở phiên bản 3.1.0. Vì Firetruck sử dụng một số tính năng đã được giới thiệu lần đầu tiên trong 3.1.0, bạn có thể xác định một cách an toàn sự phụ thuộc Ladder là lớn hơn hoặc bằng 3.1.0 nhưng ít hơn 4.0.0. Bây giờ, khi Ladder phiên bản 3.1.1 và 3.2.0 trở nên có sẵn, bạn có thể ~~giải phóng~~ **thêm**chúng vào hệ thống quản lý gói và biết rằng chúng sẽ tương thích với phần mềm phụ thuộc hiện có.

Với tư cách là một nhà phát triển có trách nhiệm, bạn sẽ muốn xác minh rằng bất kỳ chức năng nâng cấp gói nào được quảng cáo. Thế giới thực là một nơi lộn xộn; không có gì chúng ta có thể làm được về điều đó nhưng phải thận trọng. Những gì bạn có thể làm là để cho phiên bản ngữ nghĩa cung cấp cho bạn một cách lành mạnh để phát hành và nâng cấp gói mà không cần phải cuộn phiên bản mới của gói phụ thuộc, tiết kiệm thời gian và rắc rối.~~ng to roll new versions of dependent packages, saving you
time and hassle~~.

Nếu tất cả điều này là mong muốn, tất cả những gì bạn cần làm để bắt đầu sử dụng Semantic Versioning là tuyên bố rằng bạn đang làm như vậy và sau đó làm theo các quy tắc. Liên kết tới trang web này từ README của bạn để những người khác biết các quy tắc và có thể hưởng lợi từ họ.


