#  Bài Tập buổi 4: Books API Web ASP.NET Core 

##  **Giới thiệu Dự Án**

Dự án này xây dựng một API RESTful sử dụng **ASP.NET Core**, cho phép người dùng quản lý thông tin sách thông qua các thao tác CRUD. **MongoDB** đóng vai trò là cơ sở dữ liệu, cung cấp khả năng lưu trữ dữ liệu sách với các chức năng tạo, đọc, cập nhật và xóa thông tin sách.

---

##  **Cấu Trúc Dự Án**

### 1. **Controllers**
   - **BooksController**: Chứa các API endpoints phục vụ cho việc quản lý sách.
   - **Các Phương Thức API**:
     - `GET /api/books`: Truy xuất tất cả các sách có trong cơ sở dữ liệu.
     - `GET /api/books/{id}`: Lấy thông tin chi tiết của sách theo **ID**.
     - `POST /api/books`: Thêm một sách mới vào cơ sở dữ liệu.
     - `PUT /api/books/{id}`: Cập nhật thông tin của một sách theo **ID**.
     - `DELETE /api/books/{id}`: Xóa một sách khỏi cơ sở dữ liệu.

### 2. **Models**
   - **Book**: Mô hình dữ liệu đại diện cho một cuốn sách, với các thuộc tính như:
     - `Id`: ID duy nhất của sách (do MongoDB tự động tạo).
     - `Name`: Tên sách.
     - `Price`: Giá sách.
     - `Category`: Thể loại sách.
     - `Author`: Tác giả của sách.
   - **BookStoreDatabaseSettings**: Lưu trữ các thông tin cấu hình kết nối với MongoDB:
     - `ConnectionString`: Địa chỉ kết nối MongoDB.
     - `DatabaseName`: Tên cơ sở dữ liệu.
     - `BooksCollectionName`: Tên collection chứa sách trong cơ sở dữ liệu.

### 3. **Services**
   - **BooksService**: Chứa các chức năng xử lý logic nghiệp vụ liên quan đến sách, bao gồm:
     - Lấy danh sách sách hoặc sách theo ID.
     - Thêm, cập nhật và xóa sách khỏi cơ sở dữ liệu.
     - Sử dụng thư viện **MongoDB.Driver** để tương tác với MongoDB.

---

##  **Các Tính Năng Chính**

| Chức năng                     | Phương thức HTTP | Endpoint              | Mô tả                                                         |
|-------------------------------|------------------|-----------------------|---------------------------------------------------------------|
| **Lấy danh sách sách**         | GET              | `/api/books`          | Lấy tất cả sách từ cơ sở dữ liệu.                              |
| **Lấy chi tiết sách**          | GET              | `/api/books/{id}`     | Lấy thông tin chi tiết của một sách dựa trên ID.              |
| **Thêm sách mới**              | POST             | `/api/books`          | Thêm một sách mới vào hệ thống với thông tin tên, giá, tác giả.|
| **Cập nhật sách**              | PUT              | `/api/books/{id}`     | Cập nhật thông tin sách dựa trên ID và dữ liệu mới.           |
| **Xóa sách**                   | DELETE           | `/api/books/{id}`     | Xóa sách khỏi cơ sở dữ liệu theo ID.                           |

---

##  **Kết Quả Đạt Được**

- **API RESTful hoàn chỉnh**: Triển khai các thao tác CRUD cho việc quản lý sách thông qua API rõ ràng và dễ sử dụng.
- **Kết nối MongoDB**: Sử dụng MongoDB làm cơ sở dữ liệu chính, với cấu hình kết nối dễ dàng trong tệp `appsettings.json`.
- **Tích hợp Swagger**: Cung cấp giao diện Swagger UI để thử nghiệm và kiểm tra API một cách trực quan.
- **Cấu trúc dự án rõ ràng**: Dự án được chia thành các thành phần riêng biệt: Controller, Service, và Model, giúp dễ dàng bảo trì và mở rộng.
- **Dữ liệu mẫu**: Hệ thống hỗ trợ khởi tạo và thao tác với dữ liệu mẫu, giúp việc kiểm tra và phát triển trở nên nhanh chóng và hiệu quả.

---

##  **Hướng Dẫn Cài Đặt và Sử Dụng**

1. **Cài đặt MongoDB**: Đảm bảo bạn đã cài đặt MongoDB và kết nối thành công với cơ sở dữ liệu.
2. **Cấu hình kết nối MongoDB**: Trong tệp `appsettings.json`, cập nhật chuỗi kết nối MongoDB và tên cơ sở dữ liệu phù hợp.
3. **Chạy Dự Án**: Mở dự án trong Visual Studio hoặc Visual Studio Code và chạy ứng dụng.
4. **Truy Cập API**: Sử dụng Swagger UI hoặc công cụ như Postman để thử nghiệm các API.
   

