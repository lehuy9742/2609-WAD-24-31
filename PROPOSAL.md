# PROPOSAL — CampusJob Trust

## 1. Team

| STT | Họ và tên         | MSSV     |
| --- | ----------------- | -------- |
| 1   | Lê Hoàng Hiếu     | 24120048 |
| 2   | Lê Nguyễn Gia Huy | 24120061 |
| 3   | Nguyễn Anh Sang   | 24120131 |

## 2. The problem

Sinh viên muốn đi làm thêm hoặc thực tập thường phải mở nhiều trang web khác nhau để tìm tin. Trong đó có tin bị đăng lặp lại, tin đã hết hạn từ lâu, và nhiều tin thiếu những thứ sinh viên cần biết nhất như lịch làm việc, yêu cầu kinh nghiệm hay đường dẫn để nộp hồ sơ. Sinh viên mất nhiều thời gian đọc từng tin, rồi vẫn không chắc tin đó đến từ đâu và có còn tuyển hay không. CampusJob Trust gom các tin vào một chỗ để sinh viên lọc theo nhu cầu, xem rõ mỗi tin lấy từ nguồn nào và được kiểm tra lần cuối khi nào, rồi tự quyết định có mở tin gốc để ứng tuyển hay không. Trang web không kết luận tin nào an toàn hay lừa đảo; nó chỉ cho người dùng thấy những gì đã biết và những gì nguồn chưa cung cấp.

## 3. Users

| Loại người dùng | Là ai | Muốn làm được gì |
| --- | --- | --- |
| **Chính** | Sinh viên đại học đang tìm việc làm thêm hoặc thực tập | Lọc nhanh các tin hợp với loại việc, mức lương và kinh nghiệm của mình, xem nguồn và thời điểm kiểm tra, rồi mở tin gốc để ứng tuyển |
| **Phụ** | Sinh viên chưa có nhiều kinh nghiệm | Đọc rõ yêu cầu công việc và biết thông tin nào còn thiếu trước khi quyết định ứng tuyển |

**Không phục vụ:** nhà tuyển dụng đăng tin, bộ phận tuyển dụng quản lý ứng viên, người đi làm cần hệ thống tuyển dụng chuyên sâu.

## 4. Main flow

Việc chính của người dùng: **tìm được một tin phù hợp và mở được tin gốc để ứng tuyển.**

1. Mở trang web, nhập từ khóa (ví dụ "Thực tập Marketing", "gia sư") và chọn thành phố. — *Màn hình 1*
2. Chọn bộ lọc: loại công việc (làm thêm / thực tập / toàn thời gian), địa điểm, mức lương; hoặc bấm nhanh một nhu cầu phổ biến như "Không yêu cầu kinh nghiệm", "Ca linh hoạt". — *Màn hình 1*
3. Bấm **"Tìm việc"**. — *sang Màn hình 2*
4. Xem danh sách kết quả, so sánh chức danh, công ty, loại công việc, địa điểm, mức lương, ngày đăng và trạng thái xác minh của từng tin. — *Màn hình 2*
5. Nếu chưa vừa ý, chỉnh thanh bộ lọc (loại công việc, địa điểm, mức lương, kinh nghiệm), đổi cách sắp xếp hoặc sang trang kết quả tiếp theo. — *Màn hình 2*
6. Bấm vào một tin để xem chi tiết: mô tả, yêu cầu, lịch làm, lương, và khung **Thông tin nguồn tin** (nguồn đăng, đường dẫn gốc, thời điểm kiểm tra gần nhất, những điểm cần tự kiểm tra). — *sang Màn hình 3*
7. Bấm **"Ứng tuyển tại nguồn"** để sang website nguồn, xác nhận tin còn tuyển và ứng tuyển tại đó.

Toàn bộ luồng trên không cần đăng nhập. Sinh viên có tài khoản có thể bấm **"Lưu việc"** ở Màn hình 2 hoặc 3 để xem lại tin đó sau trong **"Việc đã lưu"**.

## 5. Scope

### Sẽ làm

**Phần chính** — làm trước; chỉ cần phần này là chạy được hết main flow:

- Giao diện web dùng được trên máy tính và điện thoại, tập trung vào việc làm thêm và thực tập (có thêm lựa chọn "Toàn thời gian" cho sinh viên năm cuối).
- Tìm theo từ khóa và thành phố; bộ lọc loại công việc, địa điểm (kể cả Remote), mức lương, kinh nghiệm; sắp xếp theo ngày đăng hoặc mức lương; phân trang.
- **Crawl tin từ các trang tuyển dụng** (dự kiến bắt đầu với ITviec, TopDev rồi thêm các trang khác), chỉ ở những phần mà `robots.txt` của từng trang cho phép, chạy mỗi ngày một lần với tốc độ thấp. Tin chỉ đăng trên trang tuyển dụng riêng của doanh nghiệp thì do nhóm nhập tay. Tất cả lưu chung một cấu trúc trong cơ sở dữ liệu.
- Trang chi tiết hiển thị tên nguồn, đường dẫn tin gốc, thời điểm kiểm tra lần cuối; ghi **"Nguồn không cung cấp"** ở trường nào bị thiếu.
- Nhãn trạng thái gắn theo quy tắc cố định, không phải phán xét: mọi tin mặc định là **"Chưa xác minh độc lập"** (rút gọn thành "Chưa xác minh" trên thẻ nhỏ); tin thành **"Cần kiểm tra thêm"** khi thiếu mức lương, kỳ trả lương hoặc người liên hệ, hoặc đã hơn 7 ngày chưa được kiểm tra lại.
- Ẩn tin trùng (cùng công ty, chức danh và địa điểm) và tin đã quá hạn nhận hồ sơ.
- Nút **"Ứng tuyển tại nguồn"** mở trang tuyển dụng gốc.

**Phần cá nhân** — làm sau, khi phần chính đã chạy được:

- Tài khoản sinh viên đơn giản (email và mật khẩu); **Lưu việc** và trang **Việc đã lưu**.
- **Hồ sơ ngắn** (ngành học, lịch có thể đi làm), dùng để chọn sẵn bộ lọc ở Màn hình 1.
- **Thông báo trong trang** (biểu tượng chuông) khi một việc đã lưu đổi trạng thái hoặc còn 3 ngày là hết hạn nhận hồ sơ.
- Nút **"Báo cáo tin tuyển dụng đáng ngờ"** (sinh viên gửi lý do, nhóm dùng báo cáo để kiểm tra lại nguồn) và các trang nội dung tĩnh: hướng dẫn tìm việc an toàn, giới thiệu, trợ giúp, liên hệ, quyền riêng tư.

### Not building

- **Không có tài khoản nhà tuyển dụng:** không đăng tin, không quản lý hồ sơ ứng viên.
- **Không có giao diện quản trị:** nhóm chạy script nhập tin và xem báo cáo trực tiếp trong công cụ quản lý cơ sở dữ liệu.
- **Không nhắn tin, không đặt lịch phỏng vấn** giữa ứng viên và nhà tuyển dụng.
- **Không tự động nộp hồ sơ, không tải lên hay lưu CV:** khung "Hồ sơ sẵn sàng" chỉ nhắc sinh viên tự chuẩn bị CV.
- **Không kết luận lừa đảo:** không tuyên bố một tin là lừa đảo hay chắc chắn hợp pháp; báo cáo của người dùng không tự gắn nhãn lên tin.
- **Không gửi thông báo qua email hay SMS:** chỉ có thông báo trong trang.
- **Không đăng nhập bằng Google/Facebook, không xác minh danh tính sinh viên.**
- **Không dùng AI dự đoán khả năng được tuyển.**
- **Không thu thập dữ liệu hàng loạt:** không crawl phần nào mà `robots.txt` của nguồn không cho phép, không vượt qua đăng nhập, CAPTCHA, giới hạn truy cập hay cơ chế bảo vệ của nguồn.
- **Không làm ứng dụng di động:** chỉ làm web chạy được trên điện thoại.
- **Không thay thế TopCV:** không xây một hệ thống tuyển dụng đầy đủ như TopCV hay các trang lớn.

## 6. Screens

Ba màn hình nằm trong thư mục [`wireframes/`](wireframes/), theo đúng thứ tự của main flow. Bản vẽ theo một kịch bản: sinh viên Lan Nguyễn (đã đăng nhập) tìm việc thực tập marketing ở TP.HCM, rồi mở tin "Thực tập sinh Marketing" của Lá Creative, là tin đầu tiên ở Màn hình 2 và cũng là chủ đề của Màn hình 3.

Phần dùng chung cho cả ba màn hình:

- **Thanh trên cùng:** **Trang chủ** (về Màn hình 1), **Việc làm** (sang Màn hình 2), **Việc đã lưu**, chuông thông báo, và menu tài khoản (hồ sơ, đăng xuất). Trên trang thật, mục của trang đang mở sẽ được tô đậm (Việc làm ở Màn hình 2 và 3); trong bản vẽ, mục Trang chủ được tô ở cả ba màn hình.
- **Chân trang:** dẫn tới các trang nội dung tĩnh, gồm Giới thiệu, Hướng dẫn, Liên hệ ở trang chủ, và Trợ giúp, Quyền riêng tư ở các trang khác.
- **Dải "Dữ liệu minh họa":** chỉ để đánh dấu dữ liệu giả trong bản mẫu, không có trên trang thật.
- **Nhãn trạng thái:** "Chưa xác minh" / "Chưa xác minh độc lập" và "Cần kiểm tra thêm" được gắn theo quy tắc trong §5, không phải đánh giá tin đó tốt hay xấu.

### Màn hình 1 — Tìm kiếm và lọc

[`wireframes/01 - Job Search.png`](wireframes/01%20-%20Job%20Search.png)

Đây là màn hình đầu tiên khi sinh viên mở CampusJob Trust. Sinh viên đang muốn khoanh vùng loại việc mình cần. Các chip được tô sẵn (Làm thêm, Thực tập, TP.HCM, 25k–40k/giờ) là gợi ý chọn sẵn từ hồ sơ ngắn của Lan; khung **"Tìm việc linh hoạt"** ở góc phải giới thiệu tính năng này. Sinh viên nhập từ khóa (tên công việc hoặc tên công ty), rồi bấm chip để bật/tắt từng lựa chọn: loại công việc (làm thêm, thực tập, toàn thời gian), địa điểm (bấm chip TP.HCM / Hà Nội sẽ đổi ô thành phố bên cạnh ô tìm kiếm; chip Remote thêm việc làm từ xa), mức lương, hoặc một nhu cầu phổ biến như "Không yêu cầu kinh nghiệm", "Ca linh hoạt". Mục **Công việc nổi bật** cho xem nhanh vài tin mới, kèm nhãn trạng thái. Trong kịch bản của bản vẽ, Lan gõ "Thực tập Marketing", bỏ chọn Làm thêm và 25k–40k/giờ, chọn "Không yêu cầu kinh nghiệm", rồi bấm **"Tìm việc"** để sang Màn hình 2. **"Xem tất cả"** cũng sang Màn hình 2 (không lọc); bấm vào một thẻ công việc nổi bật (hoặc mũi tên trên thẻ) sẽ sang thẳng Màn hình 3 của tin đó.

### Màn hình 2 — Kết quả tìm kiếm

[`wireframes/02 - Search Results.png`](wireframes/02%20-%20Search%20Results.png)

Sinh viên đang so sánh các tin khớp với điều kiện vừa chọn ("Thực tập Marketing", TP.HCM, Thực tập, Không yêu cầu kinh nghiệm, hiện trên thanh tìm kiếm và thanh bộ lọc) để quyết định nên xem kỹ tin nào. Mỗi thẻ cho thấy chức danh, công ty, loại công việc, địa điểm, mức lương, ngày đăng và trạng thái **"Chưa xác minh độc lập"**, để sinh viên không mặc định tin nào cũng đáng tin. Nếu kết quả chưa hợp, sinh viên đổi từ khóa rồi bấm **"Tìm kiếm"** (cùng chức năng với nút "Tìm việc" ở Màn hình 1), chỉnh một ô trong thanh bộ lọc, đổi **Sắp xếp** (mới nhất / lương cao nhất), hoặc chuyển trang (5 tin mỗi trang). Nút **"Lưu việc"** trên mỗi thẻ thêm tin vào Việc đã lưu (cần đăng nhập). Bên phải, khung **Hồ sơ sẵn sàng** dẫn tới trang hồ sơ qua **"Hoàn thiện hồ sơ"** (điền ngành học và lịch có thể làm; việc cập nhật CV chỉ là lời nhắc), còn khung **Tìm việc an toàn** dẫn tới trang hướng dẫn qua **"Xem hướng dẫn an toàn"**. Lan bấm vào thẻ đầu tiên, "Thực tập sinh Marketing" của Lá Creative, để sang Màn hình 3 của tin đó.

### Màn hình 3 — Chi tiết công việc và kiểm tra nguồn

[`wireframes/03 - Job Details & Source Trust.png`](wireframes/03%20-%20Job%20Details%20&%20Source%20Trust.png)

Sinh viên đang quyết định có nên ứng tuyển tin này hay không. Phần đầu trang tóm tắt mức lương, địa điểm, hình thức và lịch làm, kèm số lượng tuyển và hạn nhận hồ sơ (hạn này cũng là mốc để nhắc qua chuông thông báo). Bên trái là mô tả công việc, yêu cầu ứng viên, lịch làm và địa điểm, lương và quyền lợi theo tin đăng; trường nào nguồn không ghi sẽ hiện "Nguồn không cung cấp" (tin trong bản vẽ có đủ các trường này). Bên phải là khung **Thông tin nguồn tin**: tên nguồn đăng (ở đây là website của chính doanh nghiệp, tin do nhóm nhập tay), đường dẫn tin gốc, thời điểm kiểm tra gần nhất, và trạng thái cập nhật ("Có bản tin mới" nghĩa là tin gốc đã thay đổi kể từ lần lưu trước, nên sinh viên cần mở tin gốc để xem bản mới). Mục **Dấu hiệu cần kiểm tra** liệt kê những gì tin chưa nêu (ví dụ "Tin chưa nêu hợp đồng, kỳ trả lương hoặc người phụ trách tuyển dụng"), và có lời nhắc trung lập "Trước khi ứng tuyển". Bấm **"Ứng tuyển tại nguồn"** hoặc đường dẫn nguồn sẽ mở website gốc trong tab mới để xem thông tin mới nhất và nộp hồ sơ ở đó; đây là bước cuối của main flow. **"Lưu việc làm"** thêm tin vào Việc đã lưu; **"Báo cáo tin tuyển dụng đáng ngờ"** mở một ô nhập lý do ngay trên trang này. Bấm **"← Kết quả tìm kiếm"** để quay lại Màn hình 2 xem tin khác.
