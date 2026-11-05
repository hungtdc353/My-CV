# BÁO CÁO KIỂM THỬ PHẦN MỀM

## 1. Thông tin chung

| Trường thông tin | Nội dung |
|---|---|
| Tên dự án | My-CV – Portfolio cá nhân |
| Phiên bản | v1.0 (theo `docs/RELEASENOTE.md`) |
| Ngày kiểm thử | 05/11/2026 |
| Người thực hiện/đánh giá | Rà soát QA có hỗ trợ AI; chưa có người kiểm thử độc lập xác nhận |
| Phạm vi | Rà soát mã nguồn HTML/CSS, tài liệu bàn giao và cấu trúc repository hiện có |
| Phương pháp | Rà soát tĩnh và chụp ảnh viewport trang bằng Microsoft Edge headless; chưa kiểm thử tương tác hoặc trên thiết bị vật lý |
| Môi trường kiểm thử | Microsoft Edge headless, mở trang cục bộ bằng `file://`; viewport 390×844, 768×1024 và 1440×900 |

### Quy ước trạng thái

- **Đạt:** Có thể xác nhận hạng mục đáp ứng qua minh chứng hiện có.
- **Chưa đạt:** Có lỗi hoặc thiếu sót đã xác định, cần xử lý trước khi nghiệm thu.
- **Cần cải thiện:** Chưa có đủ minh chứng để kết luận đạt, hoặc còn phần cần hoàn thiện.

> Báo cáo này phản ánh rà soát tĩnh, không phải kết quả kiểm thử runtime. Các hạng mục chưa chạy cần được thực hiện lại trên trình duyệt/môi trường bàn giao trước khi chốt nghiệm thu.

## 2. Bảng tổng quan trạng thái

| # | Nhóm tiêu chí | Trạng thái | Tóm tắt |
|---|---|---|---|
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | Cần cải thiện | Các khu vực nội dung và điều hướng chính có trong mã nguồn; liên kết dự án/liên hệ còn mẫu hoặc sai markup. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | Chưa đạt | Có CSS responsive, nhưng markup ảnh đại diện lỗi và chưa kiểm thử hiển thị trên trình duyệt/kích thước màn hình. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | Đây là trang tĩnh; chưa có kết quả chạy thử, xử lý lỗi hoặc đo hiệu năng. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Cần cải thiện | Không thấy backend hay cấu hình bí mật trong phạm vi rà soát; chưa thực hiện kiểm thử bảo mật. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Chưa đạt | Repository có tài liệu cơ bản, nhưng HTML có lỗi cấu trúc và tiêu đề trang không khớp tên hồ sơ. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Chưa đạt | Có thể phục vụ dưới dạng trang tĩnh, nhưng chưa chạy kiểm thử; thư mục minh chứng ảnh hiện trống. |

## 3. Nội dung chi tiết theo tiêu chí

### 3.1 Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Có các khu vực Giới thiệu, Kỹ năng, Dự án và Liên hệ | Đạt | Các section và liên kết điều hướng tương ứng có trong `index.html`. |
| Điều hướng nội bộ tới các section | Cần cải thiện | Các `href` điều hướng khớp với ID section trong mã nguồn; chưa xác nhận thao tác thực tế trên trình duyệt. |
| Nút xem dự án và liên kết chi tiết dự án | Chưa đạt | Các thẻ dự án dùng `href="#"`, chưa dẫn tới trang/dự án thật. |
| Thông tin liên hệ | Chưa đạt | Thẻ email trong `index.html` có thuộc tính `href` không hoàn chỉnh; GitHub và LinkedIn đang dùng `href="#"`. |
| Nội dung dự án nhất quán với chức năng thật | Cần cải thiện | Trang giới thiệu Todo List và Weather Dashboard, nhưng repository hiện chỉ thể hiện website portfolio tĩnh; chưa có bằng chứng về các ứng dụng được liên kết. |

### 3.2 Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Có thiết lập viewport và ngôn ngữ tài liệu | Đạt | `index.html` khai báo `lang="vi"` và thẻ viewport. |
| Bố cục responsive trên mobile, tablet và desktop | Chưa đạt | Đã chụp và kiểm tra ảnh viewport tại `docs/screenshots/`. Ở 390×844, một số dòng chữ bị cắt theo chiều ngang; cần xử lý tràn nội dung. Tablet và desktop được ghi nhận bằng ảnh, chưa kiểm tra trên thiết bị vật lý. |
| Ảnh đại diện hiển thị và có văn bản thay thế hợp lệ | Chưa đạt | Tệp `assets/img/avatar.jpg` tồn tại, nhưng thẻ `img` trong `index.html` thiếu dấu nháy đóng ở giá trị `alt`, khiến markup bị lỗi. |
| Nhận diện và tiêu đề trang nhất quán | Chưa đạt | Nội dung trang giới thiệu Trần Đức Chí Hưng nhưng phần tử `<title>` ghi “Trần Đức Chí Hưng · Frontend Developer”. |
| Khả năng sử dụng bằng bàn phím và công nghệ hỗ trợ | Cần cải thiện | Có nhãn điều hướng và một số nội dung ngữ nghĩa; chưa thực hiện kiểm tra bàn phím, screen reader, độ tương phản hoặc focus. |
| Tương thích đa trình duyệt | Cần cải thiện | Chưa có kết quả kiểm tra trên Chrome, Firefox, Edge hoặc Safari. |

#### Minh chứng ảnh chụp responsive

Ảnh được chụp bằng Edge headless từ trang hiện tại; đây là ảnh viewport, không phải ảnh chụp từ thiết bị vật lý.

| Thiết bị đại diện | Viewport | Minh chứng | Quan sát |
|---|---:|---|---|
| Mobile | 390×844 | [responsive-mobile.png](screenshots/responsive-mobile.png) | Trang hiển thị; một số đoạn văn vượt khỏi vùng nhìn thấy theo chiều ngang và bị cắt. |
| Tablet | 768×1024 | [responsive-tablet.png](screenshots/responsive-tablet.png) | Ảnh hero và nội dung chính hiển thị trong viewport; cần kiểm tra tương tác và cuộn trên thiết bị thật. |
| Desktop | 1440×900 | [responsive-desktop.png](screenshots/responsive-desktop.png) | Bố cục nhiều cột hiển thị trong viewport; cần kiểm tra các kích thước desktop khác. |

### 3.3 Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Trang có thể được phục vụ như nội dung tĩnh | Cần cải thiện | README hướng dẫn chạy bằng Python HTTP server hoặc Nginx/Docker; chưa thực thi các lệnh để xác nhận. |
| Có trạng thái xử lý khi tài nguyên không tải được | Cần cải thiện | Chưa có kiểm tra hoặc phương án dự phòng được ghi nhận cho lỗi tải ảnh/CSS. |
| Đo tốc độ tải và hiệu năng cơ bản | Cần cải thiện | Chưa đo thời gian tải, kích thước tài nguyên, Lighthouse hoặc Web Vitals. |
| Xử lý lỗi phía client | Cần cải thiện | Chưa có kết quả kiểm tra console/network của trình duyệt; dự án không có bộ kiểm thử tự động. |

### 3.4 Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Kiểm tra bí mật/credentials trong cấu hình | Cần cải thiện | Không thấy backend hoặc tệp `.env` được mô tả trong README; chưa thực hiện quét secrets trên toàn bộ repository. |
| Xử lý dữ liệu cá nhân | Cần cải thiện | Trang hiển thị email và thông tin hồ sơ công khai; chủ sở hữu cần xác nhận đồng ý công khai trước khi triển khai. |
| Bề mặt tấn công phía server | Đạt | Theo phạm vi mã nguồn được rà soát, dự án là trang tĩnh và không có API/backend ứng dụng. Hạ tầng hosting chưa được đánh giá. |
| Cấu hình môi trường | Đạt | README ghi nhận không có cấu hình môi trường hoặc `.env`; chưa có cấu hình runtime phức tạp. |
| Kiểm thử bảo mật | Cần cải thiện | Chưa thực hiện quét lỗ hổng, kiểm tra header bảo mật, HTTPS hoặc cấu hình máy chủ triển khai. |

### 3.5 Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Cấu trúc tệp dự án rõ ràng | Đạt | Có `index.html`, `assets/css/styles.css`, ảnh trong `assets/img/` và tài liệu trong `docs/`. |
| HTML hợp lệ và nhất quán | Chưa đạt | `index.html` có thuộc tính `alt` chưa đóng đúng và liên kết email không hoàn chỉnh. Cần chạy HTML validator sau khi sửa. |
| Tên trang khớp với nội dung hồ sơ | Chưa đạt | `<title>` đang ghi tên khác với tên trong nội dung trang. |
| README hướng dẫn sử dụng | Đạt | `README.md` có mô tả, công nghệ, yêu cầu, cấu hình và hướng dẫn chạy Windows/macOS/Linux/Docker. Các lệnh chưa được xác minh bằng thực thi trong báo cáo này. |
| Release note và nhật ký thay đổi | Đạt | Có `docs/RELEASENOTE.md` và `docs/AI_LOG.md`; release note ghi các hạn chế markup/liên kết. |

### 3.6 Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Hướng dẫn triển khai/chạy thử | Cần cải thiện | README có lệnh Python và Docker; chưa xác nhận hoạt động thực tế trên từng hệ điều hành. Repository không có Dockerfile, hướng dẫn Docker dùng image Nginx trực tiếp. |
| Bộ kiểm thử tự động | Chưa đạt | Không tìm thấy cấu hình hoặc bộ kiểm thử tự động trong cấu trúc repository được cung cấp. |
| Kiểm thử thủ công trên trình duyệt | Chưa đạt | Chưa có biên bản chạy trên browser/device. |
| Cung cấp ảnh chụp và minh chứng | Chưa đạt | `docs/screenshots/` hiện chưa có tệp ảnh. |
| Lưu kết quả kiểm thử có thể tái lập | Cần cải thiện | Báo cáo này ghi nhận kết quả rà soát tĩnh; cần bổ sung trình duyệt, hệ điều hành, kích thước viewport và kết quả runtime khi kiểm thử thực tế. |

## 4. Đánh giá tổng kết và đề xuất

### Nhận định chung

Sản phẩm đã có cấu trúc portfolio tĩnh, các khu vực nội dung chính, CSS responsive và tài liệu hướng dẫn cơ bản. Tuy nhiên, theo rà soát hiện tại, **chưa khuyến nghị bàn giao/phát hành chính thức** vì có lỗi markup ảnh đại diện và liên kết email, tiêu đề trang không khớp tên hồ sơ, các liên kết dự án/mạng xã hội chưa hoàn thiện, đồng thời chưa có kết quả kiểm thử runtime hoặc minh chứng.

### Các vấn đề cần khắc phục trước khi bàn giao

1. Sửa markup thẻ ảnh đại diện và liên kết email trong `index.html`; chạy HTML validator để xác nhận tài liệu hợp lệ.
2. Đồng bộ phần tử `<title>` với tên và vai trò thực tế của chủ hồ sơ.
3. Thay các liên kết `href="#"` bằng URL thật hoặc bỏ liên kết nếu chưa có đích đến; xác nhận email và các URL liên hệ.
4. Chạy thử trang bằng HTTP server và Docker theo README; kiểm tra điều hướng, tải CSS/ảnh và console trình duyệt.
5. Kiểm tra giao diện tối thiểu ở mobile, tablet và desktop; bổ sung kết quả đa trình duyệt nếu là yêu cầu bàn giao.
6. Chụp ảnh minh chứng và lưu trong `docs/screenshots/`; ghi môi trường, ngày chạy và kết quả đạt/không đạt.
7. Xác nhận nội dung thông tin cá nhân được phép công khai; thực hiện rà soát bảo mật hạ tầng hosting trước khi triển khai công khai.

### Điều kiện đề xuất để nghiệm thu lại

- Không còn lỗi HTML validator và các liên kết quan trọng hoạt động đúng.
- Các kiểm tra thủ công trên viewport mục tiêu hoàn tất, không có lỗi nghiêm trọng ảnh hưởng nội dung hoặc điều hướng.
- README và lệnh triển khai được xác nhận trên môi trường bàn giao.
- Báo cáo được cập nhật bằng kết quả kiểm thử runtime và minh chứng tương ứng.
