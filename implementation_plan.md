# Kế hoạch tự động hóa bảng xếp hạng & đội hình Pokemon VGC Top 8

Tài liệu này chi tiết kế hoạch tự động hóa quy trình lấy danh sách đội hình của Top 8 người chơi từ giải đấu trên Limitless TCG/VGC, tạo liên kết PokePaste cho từng người, và kết xuất hình ảnh bảng xếp hạng Top 8 thông qua API của trang web generator.joaoabel.pt.

## Các thay đổi đề xuất

Chúng ta sẽ tạo một script Python để tự động hóa toàn bộ quy trình này từ dòng lệnh.

### Script & Dữ liệu

#### [NEW] [generate_top8.py](file:///Users/huy/Code/test/private/generate_top8.py)
Đây là script Python chính mà người dùng sẽ chạy để tự động hóa quy trình. Nó sẽ:
1. Nhận URL giải đấu Limitless hoặc ID giải đấu từ người dùng.
2. Tự động trích xuất ID giải đấu dạng hex 24 ký tự.
3. Lấy thông tin chi tiết giải đấu (tên, ngày, thể thức, số lượng người chơi) và bảng xếp hạng thông qua API công khai của Limitless.
4. Lọc ra top 8 người chơi dựa trên bảng xếp hạng cuối cùng.
5. Đối với mỗi người chơi:
   - Chuyển đổi dữ liệu đội hình JSON sang định dạng văn bản Pokemon Showdown tiêu chuẩn.
   - Tải văn bản đội hình lên `pokepast.es` để tạo liên kết PokePaste.
   - Ánh xạ tên Pokemon và tên vật phẩm (item) khớp chính xác với định dạng được generator.joaoabel.pt hỗ trợ bằng cách sử dụng các từ điển JSON cục bộ.
6. Đóng gói dữ liệu giải đấu và thông tin top 8 người chơi để gửi yêu cầu POST đến `https://api.generator.joaoabel.pt/topcut/png` nhằm tạo ảnh bảng xếp hạng.
7. Lưu ảnh PNG bảng xếp hạng được tạo về máy (ví dụ: `[ten-giai-dau]-top8.png`).
8. In ra một báo cáo Markdown tuyệt đẹp chứa:
   - Tóm tắt giải đấu (Tên, Ngày, Thể thức, Tổng số người chơi).
   - Bảng xếp hạng Top 8 hiển thị thứ hạng, tên người chơi, cờ quốc gia, kỷ lục trận đấu (record), và URL PokePaste vừa được tạo.

#### [NEW] [pokemon_name_mapping.json](file:///Users/huy/Code/test/private/pokemon_name_mapping.json)
File JSON này ánh xạ tên các Pokemon từ Limitless sang định dạng case-insensitive được chấp nhận bởi API joaoabel (ví dụ: `"Wash Rotom"` -> `"Rotom-wash"`, `"Eternal Flower Floette"` -> `"Floette-eternal"`). Dữ liệu này được trích xuất trực tiếp từ trang web của joaoabel.

#### [NEW] [item_name_mapping.json](file:///Users/huy/Code/test/private/item_name_mapping.json)
File JSON này ánh xạ tên vật phẩm từ Limitless sang định dạng case-insensitive được chấp nhận bởi API joaoabel.

## Kế hoạch xác minh

### Kiểm thử tự động
- Chạy script Python với ID giải đấu đã hoàn thành (ví dụ: `6a17f60e0f6c1f0899862863` cho giải UmbreNews #17 hoặc `6a1c34ce47f3797bf6ba851d` cho giải Drywalls Series #7) và kiểm tra:
  1. Chương trình lấy thành công bảng xếp hạng và chi tiết giải đấu.
  2. Chương trình tải thành công đội hình lên Pokepaste và trả về URL `pokepast.es` hợp lệ.
  3. Chương trình tạo thành công ảnh bảng xếp hạng `top8.png`.
  4. Chương trình in ra báo cáo Markdown đúng định dạng.

### Xác minh thủ công
- Mở ảnh `top_8.png` được tạo để đảm bảo các sprite Pokemon, sprite vật phẩm, tên, kỷ lục, và cờ quốc gia hiển thị chính xác.
- Mở các liên kết `pokepast.es` được tạo để đảm bảo chúng chứa đầy đủ thông tin đội hình Showdown.
