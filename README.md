# Dự án dự đoán giá vé máy bay

## Tổng quan

Dự án này thu thập, xử lý và phân tích dữ liệu chuyến bay từ các sân bay khác nhau tại Việt Nam. Nó sử dụng API Amadeus để lấy thông tin chuyến bay, xử lý dữ liệu và cung cấp các biểu đồ trực quan để có cái nhìn sâu sắc về mô hình chuyến bay, giá cả và nhiều thông tin khác. Sau đó huấn luyện mô hình để dự đoán.

## Tính năng

- Thu thập dữ liệu từ API Amadeus

- Xử lý và làm sạch dữ liệu

- Trực quan hóa dữ liệu sử dụng matplotlib

- Tích hợp cơ sở dữ liệu với MySQL

## Yêu cầu hệ thống

- Python 3.x

- Các gói Python cần thiết (cài đặt bằng cách sử dụng `pip install -r requirements.txt`):

- requests

- pandas

- matplotlib

- mysql-connector-python

- python-dotenv

- tqdm

## Cài đặt

1. Clone repository

2. Cài đặt các gói cần thiết: vào command line của thư mục nhập`pip install -r requirements.txt`

3. Tạo file `.env` trong thư mục gốc với nội dung sau:

```

API_KEY=your_amadeus_api_key

API_SECRET=your_amadeus_api_secret

DB_HOST=your_database_host

DB_USER=your_database_user

DB_PASSWORD=your_database_password

DB_NAME=your_database_name

DB_CLOUD_HOST=your_database_host

DB_CLOUD_USER=your_database_user

DB_CLOUD_PASSWORD=your_database_password

DB_CLOUD_NAME=your_database_name

```

4. Thay thế các giá trị placeholder trong file `.env` bằng thông tin đăng nhập thực tế của bạn

## Kết nối với SQL Cloud

1. Tạo SQL Cloud và kết nối với MySQL workbench, xem tại [đây](https://www.youtube.com/watch?v=_iOv1ec7tJQ)

2. Sau đó là quá trình kết nối và sử dụng SQL tương tự SQL.ipynb. Bên cạnh đó có thể làm việc trực tiếp trên SQL Google Cloud, có thể xem tại [đây](https://www.youtube.com/watch?v=jWkeFjfrCxQ)

## Sử dụng

1. Chạy `data_collect.ipynb` để lấy dữ liệu chuyến bay từ API Amadeus

2. Chạy `data_visualization.ipynb` để tạo các biểu đồ từ dữ liệu đã thu thập

3. Chạy `SQL_Cloud.ipynb` để xử lý dữ liệu và lưu trữ vào cơ sở dữ liệu MySQL

## Cấu trúc dự án

- `data_collect.ipynb`: Jupyter notebook để thu thập dữ liệu chuyến bay

- `data_visualization.ipynb`: Jupyter notebook để tạo biểu đồ dữ liệu

- `SQL_Cloud.ipynb`: Jupyter notebook cho các thao tác với cơ sở dữ liệu

- `data/`: Thư mục chứa các file CSV với dữ liệu chuyến bay đã thu thập

- `.env`: File cấu hình cho API key và thông tin đăng nhập cơ sở dữ liệu

## Nguồn dữ liệu

- API Amadeus: Được sử dụng để lấy thông tin chuyến bay theo thời gian thực

## Trực quan hóa

Dự án bao gồm nhiều biểu đồ trực quan, như:

- Giá trung bình chuyến bay theo ngày

- Tần suất chuyến bay theo hãng hàng không

- Phân phối giá trên các tuyến đường khác nhau

## Cấu trúc cơ sở dữ liệu

Dự án sử dụng cơ sở dữ liệu MySQL với bảng `flights` chứa các cột sau:

- id (Khóa chính)

- departure_airport

- departure_time

- arrival_airport

- arrival_time

- carrier_code

- flight_number

- price

- duration
