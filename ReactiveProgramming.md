Rx**Java, RxAndroid Complete Beginner Course**

Khoá RxJava beginnger này là tập những khái niệm và ví dụ về RxJava. Mục tiêu là hướng dẫn nhugnwx khái niệm cơ bản bề RxJava cho bạn từ người mới học đến trình độ trung cấp.
Mỗi một khái niệm được giải thích chi tiết với các ví dụ mẫu. Tất cả ví dụ được cung cấp mô phỏng các tình huống sử dụng Android app trong thực tế đời sống.
Theo dõi khóa học này theo thứ tự giúp bạn hiểu vấn đề dễ dàng hơn.

**1. Basics**
Giới thiệu về Reactive Programming và RxJava cũng như RxAndroid
Giới thiệu ngắn gọn về lập trình Reactive, các ví dụ đơn giản về RxJava và RxAndroid. Bài viết này là nền tảng cho cả khóa học. Hiểu rõ xuyên suốt bài là cần thiết để tiếp tục các bài phía sau.
Giới thiệu về Operators
Giới thiệu RxJava Operators, các thể loại của nó và danh sách các operator hiện có của RxJava.
- From, Just, Range và Repeat. Các thao tác cơ bản để tạo ra 1 Observable, hữu dụng khi thực hành với RxJava.
- Hiểu về Observables. Giải thích chi tiết về các loại Observables và Observers có trong RxJava.
**2. Operators**
- Hiểu về  Map, FlatMap, SwitchMap và ConcatMap. Các operator hay dùng trong RxJava và các trường hợp sử dụng của operator đó
- Buffer, Bounce là gì
- Concat, Merge là gì
- Toán học và tập hợp. Các operator toán học và tập hợp thường dùng trong việc xử lý các thao tác tính toán trong Observables
- Các thể loại operator khác. Giới thiệu về các operator khác trong RxJava
**3. Networking**
- Ứng dụng mẫu Notes App. RxJava sử dụng thư viện Retrofit để thực hiện thao tác dữ liệu mạng. Ví dụ thực tế về ứng dụng viết ghi chú sẽ chi tiết trong bài này.
**4. Ví dụ về Android**
- RxJava Instant Search - sử dụng database từ local và remote, dùng Retrofit. Viết một ứng dụng Android về việc tìm nhanh vào app Danh bạ. Sẽ hướng dẫn cách dùng của Debounce, SwitchMap, Observables và Retrofit chung với nhau ntn.
- Flight Tickets App. Sử dụng FlatMap và Concat Map ntn (bằng Retrofit). Ví dụ đơn giản việc danh sách giá vé máy bay cụ thể theo từng chuyến bay. 
**5. Lộ trình**
- Đây là lộ trình dự định xuất bản các bài viết cho các khái niệm tiếp theo trong tương lai gần. Hãy theo dõi các bài viết mới dc xuất bản tại blog này. AndroidHive.info.
- RxBinding
- Rxjava Subjects
- RxJava Event Bus
- Marble Diagrams
- Data Storage (SQLite, Room Persistence)
- Flowable Backpressure Example
- Hot and Cold Observables
- Side Effect Operators
- Volley Networking
- Form Validation
- Rx Runtime Permissions
- Timer and Intervals
- Clean Architecture
- Các kiến trúc MVP và MVVM
- Ứng dụng RxJava hoàn chỉnh

**Giới thiệu lập trình Reactive - RxJava, RxAndroid**

**1. Reactive Programming là gì?**
Lập trình Reactive về cơ bản là lập trình dựa trên sự kiện không đồng bộ (event-base asynchronous). 
Mọi thứ bạn thấy là dòng dữ liệu không đồng bộ có thể quan sát được và một hành động sẽ được thực hiện khi nó (dòng dữ liệu) phát ra (emit) các giá trị. Ta có thể tạo ra dòng dữ liệu bằng bất cứ thứ gì: thay đổi biến, sự kiện click, gọi HTTP, lưu trữ dữ liệu, lỗi và nhiều nhiều nữa. Khi nó nói không đồng bộ, điều đó có nghĩa là mọi mô-đun code chạy trên thread riêng của nó, do đó thực thi nhiều khối code cùng một lúc. 

Một lợi thế của cách tiếp cận không đồng bộ là, khi mọi nhiệm vụ chạy trên luồng riêng của nó, tất cả nhiệm vụ có thể bắt đầu đồng thời và lượng thời gian hoàn thành tất cả các nhiệm vụ tương đương với nhiệm vụ dài nhất trong danh sách. Khi nói đến ứng dụng dành cho thiết bị di động, khi các tác vụ chạy trên background thread, bạn có thể đạt được trải nghiệm người dùng liền mạch mà không bị ảnh hưởng hiệu năng tác động  giao diện trên main thread.
* Một ví dụ đơn giản (từ Wikipedia) là x= y+z; trong đó tổng của y và z được gán cho x. Trong reactive programming, thì khi giá trị y thay đổi, giá trị x sẽ được cập nhật tự động mà không cần thực hiện lại câu lệnh x = y + z; Điều này có thể đạt được bằng cách quan sát (observe) giá trị của y hoặc z.
* Một mảng có thể là 1 dòng dữ liệu và 1 action dc thực hiện khi mỗi item mà nó (mảng đó) phát ra. Có thể bạn muốn lọc ra các số chẵn và bỏ qua các số lẻ. Điều này có thể được thực hiện bằng cách dùng các vòng lặp thông thường cùng với các câu lệnh điều kiện, nhưng trong reactive thì ta có thể đạt được điều này theo cách tiếp cận hoàn toàn khác.
Khi bắt đầu lập trình reactive, cách thiết kế kiến trúc và cách viết code hoàn toàn thay đổi. Sự thay đổi này còn mạnh mẽ hơn khi bạn chuyển sang các kiến trúc mô hình như Clean Architecture, MVP, MVVM, hay các design pattern khác.
**2. Reactive Extensions**
Reactive Extensions (hay là ReactiveX hay Rx) là một thư viện tuân theo các nguyên tắc của lập trình reactive, tức là soạn các chương trình dựa trên sự không đồng bộ và hướng sự kiện bằng cách sử dụng các trình tự có thể quan sát được (observable sequence). Các thư viện này cung cấp tập hợp các giao diện và phương thức giúp cho nhà phát triển viết mã code sạch sẽ và đơn giản hơn.

Reactive Extension có mặt trên nhiều ngôn ngữ lập trình như C++, C#, Java, Kotlin, Swift… Chúng ta sẽ đặc biệt quan tâm đến RxJava và RxAndroid làm mục tiêu tập trung trong phần này.
**3. RxJava là gì**
RxJava là việc triển khai Reactive Extension trên ngôn ngữ lập trình Java (từ Netflix). Về cơ bản nó là một thư viện tạo ra dòng dữ không đồng bộ trên bất kì thread nào, chuyển đổi dữ liệu và sử dụng chúng bằng một đối tượng quan sát (Observer) trên bất kì thread nào. Thư viện cung cấp nhiều thao tác rất tuyệt như map, combine, merge, filter và nhiều operator nữa áp dụng trên dòng dữ liệu.
Chúng ta sẽ hiểu hơn về operator và transformation khi bắt đầu với các ví dụ cụ thể.
**4. RxAndroid là gì, có ăn được không?**
RxAndroid dành riêng cho nền tảng Android với một số class bổ sung trên nền RxJava. Cụ thể hơn, Schedulers được giới thiệu trong RxAndroid - AndroidSchedulers.mainThread() - đóng một vai trò chủ yếu trong việc hỗ trợ khái niệm đa luồng trong các ứng dụng android. Schedulers về cơ bản là quyết đinh chạy khối mã code nào chạy trên main thread hay background thread. Phần còn lại thì thực thi chỉ từ thư viện RxJava.
Mặc dù có nhiều Schedulers, Schedulers.io() và AndroidSchedulers.mainThread() được sử dụng rộng rãi trong lập trình Android. Dưới đây là danh sách các Schedulers có sẵn và một phần giới thiệu ngắn gọn.
- Schedulers.io() - được dùng để thực hiện các hoạt động không tốn nhiều tài nguyên CPU như network call, đọc ghi file, ổ đĩa, thao tác trên database… Nó duy trì các nhóm threads (maintains pool of threads).
- AndroidSchedulers.mainThread() - Nó cung cấp tru cập vào Main Thread/UI Thread. Như các thao tác như cập nhật lên giao diện, các tương tác của người dùng. Ta không nên thực hiện bất kì thao tác chuyên sâu nào trên thread này vì nó làm cho ứng dụng bị lỗi hoặc quăng ra ANR (Application Not Responding) - app bị treo.
- Schedulers.newThread() - Sử dụng Schedulers.newThread, một đối tượng scheduler sẽ được tạo tương ứng với 1 task. Thường chỉ dùng cho 1 task chạy trong 1 thời gian dài. Thread tạo ra bằng newThread() sẽ không sử dụng lại được.
- Schedulers.computation() - được dùng để thực hiện các hoạt động chuyên sâu như xử lý trên lượng dữ liệu lớn, xử lý ảnh bitmap,… Số lượng thread được tạo ra bằng scheduler này phục thuộc vào số lượng core của CPU.
- Schedulers.single() - sẽ thực thi tất cả các tác vụ theo thứ tự tuần tự mà chúng được thêm vào. Khi cần thực hiện các tác vụ tuần tự thì dùng scheduler này là hợp lý.
- Schedulers.immediate() - thực hiện nhiệm vụ ngay lập tức theo cách không đồng bộ bằng cách chặn thực thi trên main thread.
- Schedulers.trampoline() - thực hiện nhiệm vụ theo cách First In - First Out. Các task theo scheduler sẽ được thực hiện từng cái một bằng cách giới hạn số lượng số lượng background thread là một.
- Schedulers.from() - cho phép chúng ta tạo ra một scheduler từ đối tượng thực thi bằng cách giới hạn số lượng thread dc tạo ra. Khi thread pool bị chiếm lấy thì các task sẽ được sắp xếp theo hàng đợi.

Bây giờ chúng ta có những khái niệm cơ bản cần thiết. Hãy bắt đầu với một số khái niệm chính về RxJava mà mọi người nên biết.

4. RxJava Cơ bản: Observable, Observer
RxJava xoay quanh 2 thành phần chính là Observable và Observer. Thêm nữa còn một vài thứ khác như là Schedulers, Operators và Subscription.
- Observable là 1 dòng dữ liệu thực hiện công việc và phát ra dữ liệu.
- Observer là phần truy cập của Observable. Nó nhận dữ liệu được phát ra bởi Observable.
- Subscription. Sự liên kết giữa Observable và Obsever được gọi là Subscription. Có thể có nhiều Observer đăng kí cho một đối tượng Observable.
- Operator/Transformation. (Toán tử/Chuyển đổi) toán tử chuyển đổi dữ liệu được phát ra bởi Observable truocs khi một Observer nhận chúng. Nói chung nó là 1 thao tác thay đổi, xử lý trên dữ liệu.
- Schedulers quyết đinh thread mà Observable sẽ phát ra dữ liệu và trên Observer nào sẽ nhận dữ liệu trên thread nào main hay là background.