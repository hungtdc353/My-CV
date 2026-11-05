# My-CV

## Tên dự án

**My-CV – Portfolio cá nhân của Trần Đức Chí Hưng**

## Mô tả

My-CV là website tĩnh giới thiệu hồ sơ cá nhân và các dự án tiêu biểu, được xây dựng để trình bày thông tin về kỹ năng, kinh nghiệm/dự án và cách liên hệ. Trang có bố cục responsive cho màn hình di động, máy tính bảng và máy tính.

## Chức năng

- Hiển thị phần giới thiệu và vai trò nghề nghiệp.
- Trình bày danh sách kỹ năng.
- Giới thiệu các dự án qua những thẻ nội dung.
- Điều hướng nhanh tới Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hiển thị thông tin liên hệ và liên kết quay lại đầu trang.

## Công nghệ

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện responsive, Flexbox và CSS Grid.
- Không sử dụng framework, thư viện JavaScript, backend hoặc bước biên dịch.
- Docker tùy chọn: Nginx để phục vụ trang tĩnh.

## Yêu cầu môi trường

Để mở trực tiếp trang:

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.

Để chạy bằng máy chủ phát triển:

- Python 3 (đã có sẵn trên nhiều hệ thống) hoặc một HTTP server tĩnh tương đương.

Để chạy bằng Docker:

- Docker Desktop trên Windows/macOS, hoặc Docker Engine trên Linux.
- Kết nối Internet trong lần chạy đầu để tải image `nginx:alpine`.

Không cần cài Node.js, npm hay các gói phụ thuộc của dự án.

## Cài đặt

Tải hoặc clone repository về máy, sau đó mở terminal tại thư mục dự án (thư mục chứa `index.html`). Ví dụ, nếu đã clone repository:

```bash
cd My-CV
```

Không cần chạy lệnh cài đặt dependency.

## Cấu hình

Dự án hiện không có cấu hình môi trường hoặc tệp `.env`.

- Chỉnh nội dung hồ sơ, dự án và thông tin liên hệ trong `index.html`.
- Chỉnh màu sắc, bố cục và breakpoint responsive trong `assets/css/styles.css`.
- Thay ảnh đại diện tại `assets/img/avatar.jpg` hoặc cập nhật đường dẫn ảnh trong `index.html`.
- Cập nhật các liên kết dự án, GitHub và LinkedIn trước khi công khai website. Một số liên kết hiện vẫn là liên kết mẫu.

## Chạy thử

### Windows

Mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, dùng:

```powershell
python -m http.server 8000
```

### macOS

Mở Terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

### Linux

Mở terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Sau khi máy chủ khởi động, mở <http://localhost:8000> trong trình duyệt. Giữ terminal đang chạy trong lúc xem trang; nhấn `Ctrl+C` để dừng máy chủ.

Nếu cổng `8000` đang được sử dụng, thay `8000` trong lệnh bằng `8001` rồi mở <http://localhost:8001>.

### Docker

Đảm bảo Docker đang chạy và mở terminal tại thư mục dự án.

PowerShell trên Windows:

```powershell
docker run --rm -d --name my-cv -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

macOS hoặc Linux:

```bash
docker run --rm -d --name my-cv -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Mở <http://localhost:8080> để xem trang. Dừng container bằng:

```bash
docker stop my-cv
```

## Kiểm tra

Repository hiện không có bộ kiểm thử tự động hoặc lệnh build. Có thể kiểm tra thủ công bằng cách mở trang trên trình duyệt ở các kích thước màn hình khác nhau, thử các liên kết điều hướng và xem console của trình duyệt để phát hiện lỗi.

## Thông tin liên hệ

- **Tên:** Trần Đức Chí Hưng
- **Email:** hungtran92728@gmail.com
- **GitHub:** tranducchihung
- **LinkedIn:** tranducchihung

Lưu ý: hãy xác nhận địa chỉ email và cập nhật URL đầy đủ của các trang cá nhân trước khi phát hành. Liên kết email trong HTML hiện cần được hoàn thiện.
