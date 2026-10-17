# PROPOSAL — CampusJob Trust

## 1. Team

| STT | Họ và tên đầy đủ | MSSV | Vai trò |
|-----|------------------|------|---------|
| 1 | _Lê Hoàng Hiếu_ | _24120048_| _ _ |
| 2 | _Lê Nguyễn Gia Huy_ | _24120061_ | _ _ |
| 3 | _Nguyễn Anh Sang_ | _241200131_ | _ _ |

## 2. The problem

Sinh viên muốn đi làm thêm hoặc thực tập thường phải mở nhiều trang web khác nhau để tìm tin. Trong đó có tin bị đăng lặp lại, tin đã hết hạn từ lâu, và nhiều tin thiếu những thứ sinh viên cần biết nhất như lịch làm việc, yêu cầu kinh nghiệm hay đường dẫn để nộp hồ sơ. Sinh viên mất nhiều thời gian đọc từng tin, rồi vẫn không chắc tin đó đến từ đâu và có còn tuyển hay không. CampusJob Trust gom các tin vào một chỗ để sinh viên lọc theo nhu cầu, xem rõ mỗi tin lấy từ nguồn nào và được kiểm tra lần cuối khi nào, rồi tự quyết định có mở tin gốc để ứng tuyển hay không. Trang web không kết luận tin nào an toàn hay lừa đảo; nó chỉ cho người dùng thấy những gì đã biết và những gì nguồn chưa cung cấp.

## 3. Users

| Loại người dùng | Là ai | Muốn làm được gì |
|-----------------|-------|------------------|
| **Chính** | Sinh viên đại học đang tìm việc làm thêm hoặc thực tập | Lọc nhanh các tin hợp với lịch học và kinh nghiệm của mình, xem nguồn và thời điểm kiểm tra, rồi mở tin gốc để ứng tuyển |
| **Phụ** | Sinh viên chưa có nhiều kinh nghiệm | Đọc rõ yêu cầu công việc và biết thông tin nào còn thiếu trước khi quyết định ứng tuyển |

Không thuộc phạm vi: nhà tuyển dụng đăng tin, bộ phận tuyển dụng quản lý ứng viên, người đi làm cần hệ thống tuyển dụng chuyên sâu.

## 4. Main flow

Việc chính của người dùng: **tìm được một tin phù hợp và mở được tin gốc để ứng tuyển.**

1. Người dùng mở trang web và nhập từ khóa (ví dụ "gia sư", "thực tập marketing").
2. Chọn bộ lọc: loại công việc (làm thêm / thực tập), địa điểm, lịch làm việc, mức kinh nghiệm.
3. Bấm **"Tìm việc"**.
4. Xem danh sách kết quả, so sánh chức danh, địa điểm, lịch làm, tên nguồn và thời điểm kiểm tra gần nhất của từng tin.
5. Nếu chưa vừa ý, điều chỉnh bộ lọc để danh sách thay đổi.
6. Chọn một tin để xem chi tiết: mô tả, yêu cầu, nguồn, đường dẫn gốc, thời điểm kiểm tra, các thông tin còn thiếu.
7. Bấm **"Mở tin tuyển dụng gốc"** để sang website nguồn, xác nhận tin còn tuyển và ứng tuyển tại đó.

## 5. Scope

### Sẽ làm

- Giao diện web dùng được trên máy tính và điện thoại, tập trung vào việc làm thêm và thực tập.
- Tìm kiếm theo từ khóa và các bộ lọc cơ bản: loại công việc, địa điểm, lịch làm việc, kinh nghiệm.
- Lưu danh sách công việc trong cơ sở dữ liệu với cấu trúc thống nhất.
- Hiển thị tên nguồn, đường dẫn tin gốc và thời điểm hệ thống kiểm tra tin lần cuối.
- Ghi rõ **"Nguồn không cung cấp"** khi một thông tin bị thiếu.
- Xử lý cơ bản tin trùng hoặc tin có thể đã cũ, nếu nguồn dữ liệu cho phép.
- Nút mở trang tuyển dụng gốc để xem thông tin mới nhất và ứng tuyển.

### Not building

- **No employer accounts:** không có tài khoản nhà tuyển dụng, không đăng tin, không quản lý hồ sơ ứng viên.
- **No messaging or interview scheduling:** không nhắn tin giữa ứng viên và nhà tuyển dụng, không đặt lịch phỏng vấn.
- **No auto-apply, no CV storage:** không tự động nộp hồ sơ thay người dùng, không lưu CV cá nhân.
- **No scam verdict:** không tuyên bố một tin là lừa đảo hay chắc chắn hợp pháp.
- **No AI hiring prediction:** không xây dựng mô hình AI dự đoán khả năng được tuyển.
- **No bulk scraping:** không thu thập dữ liệu hàng loạt từ nhiều website, không vượt qua đăng nhập, CAPTCHA, giới hạn truy cập hay cơ chế bảo vệ của nguồn.
- **No mobile app:** không làm ứng dụng riêng cho điện thoại, chỉ làm web chạy được trên điện thoại.
- **No TopCV replacement:** không xây một hệ thống tuyển dụng đầy đủ để thay thế TopCV hay các trang lớn.

## 6. Screens

### Màn hình 1 — Tìm kiếm và lọc

Đây là màn hình đầu tiên khi người dùng mở CampusJob Trust. Người dùng nhập từ khóa và chọn bộ lọc loại công việc, địa điểm, lịch làm việc, kinh nghiệm. Có một dòng ghi chú nhắc rằng kết quả được tổng hợp từ nguồn bên ngoài và cần kiểm tra tin gốc trước khi ứng tuyển. Khi bấm **"Tìm việc"**, người dùng được chuyển sang Màn hình 2 với danh sách kết quả.

### Màn hình 2 — Kết quả tìm kiếm

Đây là danh sách các tin phù hợp với từ khóa và bộ lọc vừa chọn. Người dùng đọc từng thẻ công việc (chức danh, công ty nếu có, địa điểm, loại công việc, lịch làm hoặc kinh nghiệm nếu nguồn có, tên nguồn, thời điểm kiểm tra gần nhất) để so sánh nhanh. Thẻ nào thiếu dữ liệu sẽ ghi "Một số thông tin chưa được nguồn cung cấp". Khi bấm vào một thẻ, người dùng đi sang Màn hình 3 của tin đó; nếu muốn đổi điều kiện, người dùng chỉnh bộ lọc ngay tại đây hoặc quay lại Màn hình 1.

### Màn hình 3 — Chi tiết công việc và kiểm tra nguồn

Đây là trang chi tiết của một tin đã chọn. Người dùng đọc mô tả, yêu cầu, địa điểm, loại công việc, lịch làm, mức lương (nếu nguồn có), và xem tên nguồn, đường dẫn gốc, thời điểm kiểm tra gần nhất. Nếu thiếu thông tin hoặc tin có thể đã cũ, trang hiện thông báo trung lập như "Nguồn chưa cung cấp lịch làm việc" hoặc "Vui lòng xác nhận tin còn tuyển trên website gốc". Khi bấm **"Mở tin tuyển dụng gốc"**, người dùng được đưa sang website nguồn để xem thông tin mới nhất và ứng tuyển; muốn xem tin khác thì quay lại Màn hình 2.
