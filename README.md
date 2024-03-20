# WebProject
Petopia - Thiên đường cho thú cưng
Có những giao diện như: trang chủ, đăng nhập, liên hệ, đăng ký thông tin, đặt lịch, quản lý thú cưng, quản lý khách hàng, lịch hẹn ,...
Trang web cung cấp giao diện dễ nhìn, khiến bạn chọn ra dịch vụ cần thiết dành cho thú cưng của mình

Cụ thể:
Xây dựng cơ sở dữ liệu phục vụ cho đồ án web cuối kỳ, phân tích hệ thống web
Với ý tưởng chúng ta sẽ xây dựng một trang web phân quyền nhân viên và khách hàng, khách hàng chỉ có tính năng đk tài khoản, đk tài khoản thú cưng, xem hiển thị và đánh giá dịch vụ, đặt lịch hẹn 
với phân quyền nhân viên: sẽ có các  tính năng như cập nhật trạng thái đặt lịch hẹn, hiển thị thú cưng đang quản lý, tình trạng sức khỏe của thú cưng. Ngoài ra cần có các tính năng như tra thông tin khách hàng, tra thông tin thú cưng. 
++ cần tìm hiểu tính năng tự tạo mã cho các bảng: mã khách hàng, mã thú cưng, mã dịch vụ, mã lịch sử, mã đặt hẹn
1. Các table cần có để web vận hành:
table Khách hàng sẽ bao gồm các thông tin cá nhân 
+ mã khách hàng ( khóa chính)
+ các thông tin cá nhân như Tên, ngày sinh, địa chỉ liên lạc, số điện thoại liên lạc , email liên hệ
LƯU Ý: mỗi khách hàng chỉ được quyền tạo một tài khoản khách hàng duy nhất . Mỗi lần tạo tài khoản thì chúng ta sẽ lưu trữ lại thông tin đó, để lưu  lại và gửi các thông tin cần thiết cho khách hàng
Tạo ra thêm vấn đề là sẽ phải tự động tạo mã khách hàng hay mã tài khoản của khách hàng sau mỗi lần đăng ký, phải có một thuộc tính để xác  định nhằm đảo bảo mỗi người chỉ có thể tạo và submit một không tin khách hàng ( có thể lấy số điện thoại+email để xác định điều này ) nếu như tiếp tục đăng ký với thông tin cũ sẽ báo lỗi 
table thú cưng
sẽ có mã thú cưng ( hệ thống tự tạo )
loại con gì ( nếu là chó hay mèo thì ghi rõ giống loài ra )
nick name của thú cưng
Đặc điểm nhận biết:
Màu sắc
bao nhiêu tháng tuổi rồi
cho phép up hình ảnh: cơ sở dữ liệu sẽ lưu link src của ảnh 
số điện thoại và email của chủ ( tìm thêm tính năng tự gán mã khách hàng khi mà khớp số điện thoại và mail ) 
table các dịch vụ  ( ở web sẽ hiện ra các mục như các hình chữ nhật hiển thị hình ảnh giá tiền + đánh giá dịch vụ
+ mã dịch vụ
+ tên dịch vụ
+ thời gian phục vụ ( vd: cắt tỉa lông 30 phút )
+Thêm vào số lần dịch vụ được chọn
+ điểm trung bình đánh giá dịch vụ ( cần chú ý xem thêm sẽ thao tác như thế nào )
table đặt lịch hẹn ( mang tính chất để lưu trữ lại thông tin mà khách hàng đã sử dụng dịch vụ ) cần phải lưu thêm mã hóa đơn ( để lưu lại các dịch vụ mà người đó đã sử dụng trong lần sử dụng dịch vụ đó ) -> đã là 1 table ghi nhận lại các h hẹn 
mã đặt hẹn (chưa thấy dùng mã này trong csdl)
cho phép chọn giờ làm ( giờ  ngày tháng năm ) : đây là tính năng của web, sau khi chọn xong thì hệ thống sẽ ghi nhận thời gian, giờ + ngày + tháng + năm 
điền số điện thoại đặt lịch làm
trạng thái : Đã đến, Đợi, Hủy ( tính năng này cần cho phép nhân viên thao tác và thay đổi )

-> nó sẽ liên kết với tính năng quản lý shop của nhân viên: ví dụ như khi nhân viên tra khách hẹn giờ ngày hôm nay thì trên web sẽ hiện ra các dòng hiển thị khách đặt lịch hẹn ngày hôm nay. để nhân viên nắm thông tin và dễ dàng quản lý 
f) table Thú cưng đang sử dụng dịch vụ tại shop
mã lịch sử ( khóa chính )
thời gian bắt đầu sử dụng
mã thú cưng
tên thú cưng
tình trạng sức khỏe( tốt, khá, ổn, không tốt ) ( cho phép nhân viên thay đổi )
mã dịch vụ ( cần hiển thị ra tên dịch vụ trên giao diện)
ghi chú ( nếu có cho phép nhân viên ghi chú thêm các trường hợp đặc biệt)
mã khách hàng
tình trạng: đã xong hoặc đang tại shop ( khi nhân viên tra các thú cưng đang tại shop chỉ hiển thị các thú cưng đang tại shop, với tính năng này nhân viên sẽ có quyền cập nhật trạng thái của thú cưng là xong hay đang tại shop
g)  table này sẽ cần lưu lại lịch sử sử dụng dịch vụ ( cần xây dựng hợp lí, để khi tra tìm thông tin thú cưng, click vô lịch sử đến shop, sẽ hiển thị ra các lần đến shop ) table này sẽ giúp khách hàng cx như nhân viên xem lịch sử khách đang đến tại đây. hoặc sẽ có nút thêm lịch sử khách hàng để nhân viên tự nhập.
mã khách hàng
mã thú cưng
mã lịch sử ( sẽ lưu lại để tra cứu thời gian đến ) 

vd sẽ hiện ra : Bạn và thú cưng …(nick name). đã đến vào ….
note: phần màu xanh cần xem xét để tối ưu 
note: khi ghi chú mà nếu tại đó xuất hiện thêm các tính năng liên quan tới web hay tới cơ sở dữ liệu thì tô màu đỏ 
++++
-> tổng quan các tính năng như sau logic hệ thống
Nhân viên:
mở đầu trang web sẽ có phần phân quyền thể hiện ở tính năng đăng nhập cho nhân viên nếu nhập tài khoản đã cấp thì ta sẽ có thể vào được trang web quản lý của shop
quản lý lịch hẹn
quản lý thú cưng tại shop
quản lý lịch sử khách hàng đến shop
tra thông tin khách hàng
tra thông tin thú cưng
Khách hàng:
cho phép đăng ký thông tin khách hàng
cho phép đăng ký thông tin thú cưng
cho phép đánh giá dịch vụ
có đánh giá dịch vụ thì phải có chọn loại dịch vụ
Từ những phân tích cơ sở dữ liệu cũng như tính năng trang web ta sẽ bắt đầu thiết kế giao diện trang web, chú ý xây dựng các tính năng cho thích hợp 
Tổng cộng có bao nhiêu giao diện:
giao diện với khách hàng:
giao diện show dịch vụ cho phép đánh giá dịch vụ cho phép comment ( tích hợp với show dịch vụ)
giao diện đăng ký thông tin khách hàng ( tích hợp với thông tin liên hệ )  Đã hoàn thành
giao diện đặt lịch ( cho phép chọn giờ đặt lịch ) 
giao diện đăng ký thông tin thú cưng ( đăng ký hồ sơ thú cưng)
giao diện để xem tình trạng thú cưng của mình
giao diện với nhân viên:
giao diện chung cho nhân viên ( tận dụng cái cũ) chỉnh lại xíu là xong
giao diện quản lý lịch hẹn ( ví dụ cho phép tra ngày tháng năm thì hôm nay có ai đặt lịch hẹn )
giao diện quản lý thú cưng tại shop ( cho phép nhân viên  cập nhật thông tin sức khỏe , cập nhật tình trạng thú, cập nhật thời gian hiện ra các thẻ như cái gallery vậy đó ) - chú ý xem database để không thiếu thông tin
giao diện tra thông tin khách hàng ( hiển thị lịch sử sử dụng dịch vụ) - quản lí khách hàng- hiện ra các thông tin liên hệ của khách hàng( kèm thú cưng của họ nếu có thể)
giao diện tra thông tin thú cưng  ( hiển thị thông tin + lịch sử ) 

