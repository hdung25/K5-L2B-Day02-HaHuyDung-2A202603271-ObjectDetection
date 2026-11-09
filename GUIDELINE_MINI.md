# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Xe hơi chở người cỡ nhỏ (4–7 chỗ): sedan, hatchback, SUV, crossover, taxi. | Thân thấp, nắp capo rõ, chiều dài ngắn; SUV dù cao vẫn là `car` nếu không có thân hộp vuông của van. |
| `truck` | Xe chở hàng: cabin tài xế tách riêng với thùng hàng/khung chở hàng phía sau (xe tải, bán tải, xe ben, container). | Thấy rõ cabin + thùng; thùng hàng thường cao/vuông hoặc để hở. |
| `bus` | Xe khách cỡ lớn chở nhiều người: xe buýt, xe khách đường dài. | Rất dài, nhiều cửa sổ chạy dọc thân, nhiều cửa lên xuống; cao hơn hẳn `car` và `van`. |
| `van` | Xe thân hộp một khối (cabin liền khoang sau), cỡ giữa `car` và `bus`: minivan chở người hoặc van chở hàng. | Đầu xe ngắn/dốc, thân cao và vuông, không có thùng tách rời như `truck`, ngắn hơn hẳn `bus`. |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: box chạm sát mép ngoài cùng của phần thân xe nhìn thấy được (kể cả gương, cản), không lấn mặt đường, bóng xe, trời hay xe bên cạnh; mỗi xe một box riêng.
- Vật thể bị che khuất: vẫn gán nếu nhận ra được lớp; box chỉ ôm phần nhìn thấy, không đoán phần bị che. Xe bị cột/xe khác che ở giữa vẫn là một box bao cả các phần nhìn thấy.
- Vật thể bị cắt bởi rìa ảnh: vẫn gán nếu nhận ra được lớp; box chạm đúng rìa ảnh, không kéo ra ngoài.
- Vật thể rất nhỏ/mơ hồ: gán nếu còn nhận ra là xe và xác định được lớp; nếu chỉ còn một mảng màu không xác định được lớp thì không gán, ghi lại vào bảng dưới và hỏi giảng viên.
- Không gán: xe máy/mô tô, xe đạp, người đi bộ, xe trong gương/kính phản chiếu, hình xe trên biển quảng cáo.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ


| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
|---|---|---|---|
| `drive_008` | Xe buýt nối toa (hai khoang nối bằng khớp xếp) chạy chéo qua giao lộ, dễ bị hiểu là hai xe. | **`bus` – một box bao cả hai khoang** | Đây là một phương tiện duy nhất chở khách cỡ lớn, nhiều cửa sổ dọc thân. Khớp nối không tách thành hai xe, nên theo quy tắc "mỗi xe một box" chỉ vẽ một box. |
| `drive_009` | Xe buýt đỏ–trắng ở mép trái bị rìa ảnh cắt, chỉ thấy đầu xe (kính lái, đèn), phần thân bị xe buýt khác và taxi che một phần. | **`bus` – box chạm rìa trái ảnh** | Phần đầu xe còn đủ đặc điểm (kính lái lớn, bảng số tuyến) để xác định là xe buýt. Theo quy tắc xe bị cắt khung: vẫn gán, box dừng ở rìa ảnh, không đoán phần nằm ngoài khung. |
| `drive_012` | Xe khách xanh–trắng ở giữa giao lộ bị một xe trắng phía trước che mất phần thân dưới. | **`bus` – box quanh phần xe khách nhìn thấy** | Thân dài, nhiều cửa sổ chạy dọc, cao hơn hẳn các xe xung quanh nên nhận ra là `bus`. Theo quy tắc vật thể bị che: vẫn gán, box ôm phần nhìn thấy, xe phía trước được tính là một vật thể riêng. |