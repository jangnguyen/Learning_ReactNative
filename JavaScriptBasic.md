# KIẾN THỨC JAVASCRIPT CƠ BẢN

LINK THAM KHẢO(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types)

Những kiến thức mà mình được học từ lúc làm sample đến production sẽ chia sẻ ở đây. Cùng với những link tham khảo hữu ích để mọi người có thêm kiến thức.

- JavaScript:
+ var Fruh = 'foobar';
- phân biệt hoa thường
ko cần chấm cuối câu lệnh nếu xuống dòng.
khuyến cáo ; khi xuống dòng tránh hiệu ứng phụ
mấy cái dấu space, tab và newline thì gọi là whitespace
// ghi chú
/* block ghi chú bình thường thôi*/

var
khai báo 1 biến, ko phải khởi tạo cũng dc

let, biến cục bộ trong block code, khỏi khởi tạo giá trị ban đầu cũng dc

const: khai báo 1 block, ko cho đổi tên
JS đặt tên bắt đầu bằng kí tự, gạch dưới, đô la, con số, phân biệt hoa thường.
Ko cho đặt số ở đầu tên biến
Khai báo biến:
var x = 42 dùng cho cục bộ lẫn toàn cục
x = 42 ko nên dùng mặc dù ko sai, khai báo biến toàn cục bên ngoài 1 function. Sẽ có warning
let y = 13 dùng trong block-scope cục bộ. Xem thêm bên dưới

khai báo biến mà ko gán giá trị thì mặc định là undefined.
lỗi truy cập vào giá trị indefined là ReferenceError
giống null vs quăng lỗi NullPointerException bên Java

Scope của biến
- định nghĩa biến nào bên ngoài của 1 function thì nó gọi là biến toàn cục. global var
giống biến trong Java.
định nghĩa biến bên trong hàm function thì là biến cục bộ.
ECMAScript 2015 có block statement.

- Toán tử điều kiện: varName=(varA=="VALUE")?"Hello":"Konnichiwa";
-