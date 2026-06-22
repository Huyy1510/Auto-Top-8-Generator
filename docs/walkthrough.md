# Kết quả tự động hóa bảng xếp hạng & đội hình Pokemon VGC Top 8

Tài liệu này ghi lại kết quả kiểm thử và hướng dẫn vận hành hệ thống tự động hóa trích xuất danh sách đội hình Top 8, tạo PokePaste, và kết xuất hình ảnh bảng xếp hạng.

## Danh sách tệp tin đã triển khai

1. **[generate_top8.py](file:///Users/huy/Code/test/private/src/generate_top8.py)**: Script Python tự động hóa tạo ảnh bảng xếp hạng Top 8 và PokePastes.
2. **[fetch_usage.py](file:///Users/huy/Code/test/private/src/fetch_usage.py)**: Script Python thống kê tỷ lệ sử dụng (Usage Statistics) của Pokemon và build chi tiết.
3. **[compare_usage.py](file:///Users/huy/Code/test/private/src/compare_usage.py)**: Script Python so sánh biến động metagame giữa 2 tuần giải đấu.
4. **[pokemon_name_mapping.json](file:///Users/huy/Code/test/private/data/pokemon_name_mapping.json)**: Dữ liệu ánh xạ tên Pokemon để tránh lỗi và đồng bộ hóa với generator.
5. **[item_name_mapping.json](file:///Users/huy/Code/test/private/data/item_name_mapping.json)**: Dữ liệu ánh xạ vật phẩm.

## Cách chạy lệnh

### Tạo bảng xếp hạng Top 8:
```bash
python3 src/generate_top8.py "https://play.limitlesstcg.com/tournament/6a17f60e0f6c1f0899862863/standings"
```

### Thu thập dữ liệu chỉ số sử dụng (Usage Statistics):
```bash
python3 src/fetch_usage.py "https://play.limitlesstcg.com/tournament/6a17f60e0f6c1f0899862863/standings"
```

### So sánh biến động metagame:
```bash
python3 src/compare_usage.py <đường_dẫn_json_cũ> <đường_dẫn_json_mới>
```

## Báo cáo chạy thử nghiệm (Giải UmbreNews #17)

Kết quả in ra từ dòng lệnh:

| Hạng | Tên người chơi | Quốc gia | Record | PokePaste Link |
| :---: | :--- | :---: | :---: | :--- |
| 1 | Kevmetal | 🇺🇸 (US) | 8-1 | [https://pokepast.es/e6e83a73449bb07d](https://pokepast.es/e6e83a73449bb07d) |
| 2 | Itachi | (IT) | 6-2 | [https://pokepast.es/f691802d9635c343](https://pokepast.es/f691802d9635c343) |
| 3 | Etrale | - | 6-2 | [https://pokepast.es/1d470dbca73f0e12](https://pokepast.es/1d470dbca73f0e12) |
| 4 | Steady96 | (GB) | 6-2 | [https://pokepast.es/8c64a226568d9275](https://pokepast.es/8c64a226568d9275) |
| 5 | hyperellipsoid | (TH) | 4-3 | [https://pokepast.es/ac491e1e26686cb8](https://pokepast.es/ac491e1e26686cb8) |
| 6 | TitanoPigro3 | (IT) | 4-3 | [https://pokepast.es/609bdb1096238532](https://pokepast.es/609bdb1096238532) |
| 7 | Hunter S | 🇺🇸 (US) | 4-3 | [https://pokepast.es/2928b746225b5e70](https://pokepast.es/2928b746225b5e70) |
| 8 | Mattpode3 | (IT) | 4-3 | [https://pokepast.es/48f5884717dd7dc2](https://pokepast.es/48f5884717dd7dc2) |

Hình ảnh bảng xếp hạng đã được tạo tự động và lưu tại thư mục cục bộ dưới tên `Pokemon_VGC_UmbreNews_02_06_2026__17_-_Champion_top8.png`.
