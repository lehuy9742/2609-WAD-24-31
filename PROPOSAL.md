# PROPOSAL — CampusJob Trust

## 1. Team

| STT | Họ và tên         | MSSV      |
| --- | ----------------- | --------- |
| 1   | Lê Hoàng Hiếu     | 24120048  |
| 2   | Lê Nguyễn Gia Huy | 24120061  |
| 3   | Nguyễn Anh Sang   | 24120131 |

## 2. The problem

Sinh viên muốn đi làm thêm hoặc thực tập thường phải mở nhiều trang web khác nhau để tìm tin. Trong đó có tin bị đăng lặp lại, tin đã hết hạn từ lâu, và nhiều tin thiếu những thứ sinh viên cần biết nhất như lịch làm việc, yêu cầu kinh nghiệm hay đường dẫn để nộp hồ sơ. Sinh viên mất nhiều thời gian đọc từng tin, rồi vẫn không chắc tin đó đến từ đâu và có còn tuyển hay không. CampusJob Trust gom các tin vào một chỗ để sinh viên lọc theo nhu cầu, xem rõ mỗi tin lấy từ nguồn nào và được kiểm tra lần cuối khi nào, rồi tự quyết định có mở tin gốc để ứng tuyển hay không. Trang web không kết luận tin nào an toàn hay lừa đảo; nó chỉ cho người dùng thấy những gì đã biết và những gì nguồn chưa cung cấp.

## 3. Users

| Loại người dùng | Là ai | Muốn làm được gì |
| --- | --- | --- |
| **Chính** | Sinh viên đại học đang tìm việc làm thêm hoặc thực tập | Lọc nhanh các tin hợp với lịch học và kinh nghiệm của mình, xem nguồn và thời điểm kiểm tra, rồi mở tin gốc để ứng tuyển |
| **Phụ** | Sinh viên chưa có nhiều kinh nghiệm | Đọc rõ yêu cầu công việc và biết thông tin nào còn thiếu trước khi quyết định ứng tuyển |

**Không phục vụ:** nhà tuyển dụng đăng tin, bộ phận tuyển dụng quản lý ứng viên, người đi làm cần hệ thống tuyển dụng chuyên sâu.

## 4. Main flow

Việc chính của người dùng: **tìm được một tin phù hợp và mở được tin gốc để ứng tuyển.**

1. Mở trang web, nhập từ khóa (ví dụ "gia sư", "thực tập marketing") và chọn thành phố. — *Màn hình 1*
2. Chọn bộ lọc: loại công việc (làm thêm / thực tập), địa điểm, mức lương; hoặc bấm nhanh một nhu cầu phổ biến như "Không yêu cầu kinh nghiệm", "Ca linh hoạt". — *Màn hình 1*
3. Bấm **"Tìm việc"**. — *sang Màn hình 2*
4. Xem danh sách kết quả, so sánh chức danh, công ty, loại công việc, địa điểm, mức lương, ngày đăng và trạng thái xác minh của từng tin. — *Màn hình 2*
5. Nếu chưa vừa ý, chỉnh thanh bộ lọc (loại công việc, địa điểm, mức lương, kinh nghiệm), đổi cách sắp xếp hoặc sang trang kết quả tiếp theo. — *Màn hình 2*
6. Bấm vào một tin để xem chi tiết: mô tả, yêu cầu, lịch làm, lương, và khung **Thông tin nguồn tin** (nguồn đăng, đường dẫn gốc, thời điểm kiểm tra gần nhất, những điểm cần tự kiểm tra). — *sang Màn hình 3*
7. Bấm **"Ứng tuyển tại nguồn"** để sang website nguồn, xác nhận tin còn tuyển và ứng tuyển tại đó.

## 5. Scope

### Sẽ làm

- Giao diện web dùng được trên máy tính và điện thoại, chỉ tập trung vào việc làm thêm và thực tập.
- Tìm kiếm theo từ khóa và thành phố, cùng các bộ lọc cơ bản: loại công việc, địa điểm, mức lương, kinh nghiệm.
- Lưu danh sách công việc trong cơ sở dữ liệu với cấu trúc thống nhất.
- Trang chi tiết hiển thị tên nguồn, đường dẫn tin gốc và thời điểm hệ thống kiểm tra tin lần cuối.
- Ghi rõ **"Nguồn không cung cấp"** khi một thông tin bị thiếu.
- Xử lý cơ bản tin trùng hoặc tin có thể đã cũ, nếu nguồn dữ liệu cho phép.
- Nút **"Ứng tuyển tại nguồn"** mở trang tuyển dụng gốc để xem thông tin mới nhất và ứng tuyển.

### Not building

- **Không có tài khoản nhà tuyển dụng:** không đăng tin, không quản lý hồ sơ ứng viên.
- **Không nhắn tin, không đặt lịch phỏng vấn** giữa ứng viên và nhà tuyển dụng.
- **Không tự động nộp hồ sơ, không lưu CV** của người dùng.
- **Không kết luận lừa đảo:** không tuyên bố một tin là lừa đảo hay chắc chắn hợp pháp.
- **Không dùng AI dự đoán khả năng được tuyển.**
- **Không thu thập dữ liệu hàng loạt:** không cào dữ liệu từ nhiều website, không vượt qua đăng nhập, CAPTCHA, giới hạn truy cập hay cơ chế bảo vệ của nguồn.
- **Không làm ứng dụng di động:** chỉ làm web chạy được trên điện thoại.
- **Không thay thế TopCV:** không xây một hệ thống tuyển dụng đầy đủ như TopCV hay các trang lớn.

## 6. Screens

Ba màn hình nằm trong thư mục [`wireframes/`](wireframes/), theo đúng thứ tự của main flow.

### Màn hình 1 — Tìm kiếm và lọc

[`wireframes/01 - Job Search.png`](wireframes/01%20-%20Job%20Search.png)

Đây là màn hình đầu tiên khi sinh viên mở CampusJob Trust. Sinh viên đang muốn khoanh vùng loại việc mình cần: nhập từ khóa (tên công việc hoặc tên công ty), chọn thành phố, rồi bấm các nhóm lọc loại công việc, địa điểm, mức lương hoặc một nhu cầu phổ biến như "Không yêu cầu kinh nghiệm", "Ca linh hoạt". Phía dưới có mục **Công việc nổi bật** để xem nhanh vài tin; chân trang nhắc "kiểm tra nguồn trước khi ứng tuyển". Bấm **"Tìm việc"** (hoặc **"Xem tất cả"**) sẽ sang Màn hình 2; bấm thẳng vào một thẻ công việc nổi bật sẽ sang Màn hình 3 của tin đó.

### Màn hình 2 — Kết quả tìm kiếm

[`wireframes/02 - Search Results.png`](wireframes/02%20-%20Search%20Results.png)

Sinh viên đang so sánh các tin khớp với điều kiện vừa chọn để quyết định nên xem kỹ tin nào. Mỗi thẻ cho thấy chức danh, công ty, loại công việc, địa điểm, mức lương, ngày đăng và trạng thái **"Chưa xác minh độc lập"**, để sinh viên không mặc định tin nào cũng đáng tin. Nếu kết quả chưa hợp, sinh viên đổi từ khóa hoặc thanh bộ lọc ngay trên đầu trang (loại công việc, địa điểm, mức lương, kinh nghiệm), đổi sắp xếp, hoặc chuyển trang. Khung **Tìm việc an toàn** bên phải nhắc những điều cần cẩn thận khi ứng tuyển. Bấm vào một thẻ sẽ sang Màn hình 3 của tin đó.

### Màn hình 3 — Chi tiết công việc và kiểm tra nguồn

[`wireframes/03 - Job Details & Source Trust.png`](wireframes/03%20-%20Job%20Details%20&%20Source%20Trust.png)

Sinh viên đang quyết định có nên ứng tuyển tin này hay không. Bên trái là mô tả công việc, yêu cầu ứng viên, lịch làm và địa điểm, lương và quyền lợi theo tin đăng. Bên phải là khung **Thông tin nguồn tin**: tên nguồn đăng, đường dẫn tin gốc, thời điểm kiểm tra gần nhất và trạng thái cập nhật, cùng mục **Dấu hiệu cần kiểm tra** liệt kê những gì tin chưa nêu (ví dụ "Tin chưa nêu hợp đồng, kỳ trả lương hoặc người phụ trách tuyển dụng") và lời nhắc trung lập "Trước khi ứng tuyển". Bấm **"Ứng tuyển tại nguồn"** sẽ mở website gốc để xem thông tin mới nhất và nộp hồ sơ ở đó; bấm **"← Kết quả tìm kiếm"** để quay lại Màn hình 2 xem tin khác.
