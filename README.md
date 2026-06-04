# Limitless VGC Top 8 Standings & PokePaste Generator

Một công cụ bằng Python tự động hóa 100% quy trình xử lý sau giải đấu Pokemon VGC trên Limitless. Công cụ sẽ tự động lấy danh sách Top 8 người chơi từ Limitless, tạo các liên kết PokePaste riêng biệt và kết xuất hình ảnh bảng xếp hạng Top 8 chuyên nghiệp chỉ bằng một dòng lệnh.

## Tính năng nổi bật

- **Zero-Dependency (Không cần cài đặt thư viện)**: Chỉ sử dụng các thư viện tích hợp sẵn của Python 3 (`urllib`, `json`, `re`, `ssl`, v.v.), chạy được ngay mà không cần `pip install`.
- **Tự động trích xuất ID**: Hỗ trợ nhập trực tiếp URL giải đấu của Limitless hoặc ID hex 24 ký tự.
- **Tự động tạo PokePaste**: Tự động dịch dữ liệu đội hình JSON trên Limitless sang định dạng Showdown và tải lên `pokepast.es`.
- **Ánh xạ tên thông minh**: Tự động chuyển đổi các dạng Pokemon vùng miền (ví dụ: `Hisuian Arcanine` -> `Arcanine-Hisui`, `Galarian Slowbro` -> `Slowbro-Galar`) và các dạng đặc biệt (ví dụ: `Wash Rotom` -> `Rotom-wash`, `Eternal Flower Floette` -> `Floette-eternal`) để tránh lỗi khi tạo ảnh.
- **Kết xuất hình ảnh tự động**: Gửi dữ liệu Top 8 đến API của `generator.joaoabel.pt` để tạo và lưu hình ảnh bảng xếp hạng chất lượng cao về máy.

## Cấu trúc dự án

- `generate_top8.py`: File script Python chạy chính.
- `pokemon_name_mapping.json`: Dữ liệu ánh xạ tên Pokemon tương thích API generator.
- `item_name_mapping.json`: Dữ liệu ánh xạ tên vật phẩm tương thích API generator.
- `README.md`: Hướng dẫn sử dụng này.

## Yêu cầu hệ thống

- Đã cài đặt **Python 3.x** trên máy.

## Hướng dẫn sử dụng

1. Mở Terminal hoặc Command Prompt tại thư mục dự án.
2. Chạy lệnh sau:

```bash
python3 generate_top8.py "<URL hoặc ID giải đấu trên Limitless>"
```

### Ví dụ:

Sử dụng URL giải đấu:
```bash
python3 generate_top8.py "https://play.limitlesstcg.com/tournament/6a17f60e0f6c1f0899862863/standings"
```

Sử dụng ID giải đấu trực tiếp:
```bash
python3 generate_top8.py "6a17f60e0f6c1f0899862863"
```

### Kết quả đầu ra:
- **Ảnh bảng xếp hạng**: File ảnh `.png` (ví dụ: `Pokemon_VGC_UmbreNews_top8.png`) sẽ được lưu trực tiếp tại thư mục bạn đang đứng.
- **Báo cáo trên Terminal**: In ra một bảng Markdown tóm tắt thứ hạng, tên, quốc gia, kết quả trận đấu, và link PokePaste của từng người chơi trong Top 8.

## Đóng góp ý kiến

Nếu bạn gặp bất kỳ vấn đề nào liên quan đến việc ánh xạ tên Pokemon hoặc lỗi kết nối API, vui lòng gửi phản hồi hoặc tự cập nhật trực tiếp vào hai file `pokemon_name_mapping.json` và `item_name_mapping.json`.

---
*Dự án sử dụng API công khai của [Limitless TCG/VGC](https://play.limitlesstcg.com) và dịch vụ tạo ảnh của [VGC Standings Generator](https://generator.joaoabel.pt) của tác giả João Costa.*
