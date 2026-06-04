# Kết quả tự động hóa bảng xếp hạng & đội hình Pokemon VGC Top 8

Tài liệu này ghi lại kết quả kiểm thử và hướng dẫn vận hành hệ thống tự động hóa trích xuất danh sách đội hình Top 8, tạo PokePaste, và kết xuất hình ảnh bảng xếp hạng.

## Danh sách tệp tin đã triển khai

1. **[generate_top8.py](file:///Users/huy/Code/test/private/generate_top8.py)**: Script Python chính tự động hóa toàn bộ quy trình.
2. **[pokemon_name_mapping.json](file:///Users/huy/Code/test/private/pokemon_name_mapping.json)**: Dữ liệu ánh xạ tên Pokemon tương thích với generator.joaoabel.pt.
3. **[item_name_mapping.json](file:///Users/huy/Code/test/private/item_name_mapping.json)**: Dữ liệu ánh xạ vật phẩm tương thích.

## Cách chạy lệnh

Chạy script với URL của giải đấu hoặc ID giải đấu từ Limitless:

```bash
python3 generate_top8.py "https://play.limitlesstcg.com/tournament/6a17f60e0f6c1f0899862863/standings"
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
