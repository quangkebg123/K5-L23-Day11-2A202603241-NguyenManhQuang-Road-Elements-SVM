# Báo cáo cá nhân — Ngày 11

Họ tên: NguyenManhQuang Mã học viên: 2A202603241
Phiên bản CVAT (Help → About): 2.81
Guideline: Road v1.0 Lần nộp (`revision` trong manifest): 2  
Thời điểm export (ngày giờ trên CVAT): Chưa ghi nhận; manifest được tạo 2026-11-21 11:15:53 (+07) Số lần nộp lại sau Rework: 1

## 1. Kiểm project

| Mục                   | Đúng như guideline Road v1.0? | Ghi chú                                                                                                                                  |
| --------------------- | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| 6 label, đúng kiểu    | Có theo XML export            | lane/road_curb: polyline; crosswalk/drivable: polygon; traffic_light/traffic_sign: rectangle. Chưa xác minh trực tiếp trên project CVAT. |
| Thuộc tính và giá trị | Chưa đối chiếu đầy đủ         | Cần so metadata với guideline và xác nhận trong project.                                                                                 |
| 4 tag ảnh             | Có theo XML export            | camera, timeofday, weather, source; manifest báo đủ tag trên 28/28 ảnh.                                                                  |

Cách kết thúc polyline trên bản CVAT này: Chưa ghi nhận.  
Cách đặt tag ảnh trên bản CVAT này: Chưa ghi nhận.

## 2. Số lượng đã gán

Số liệu shape dưới đây được đếm từ ZIP revision 2; tag ảnh không tính là shape.

| Task                         | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| ---------------------------- | --: | ---: | --------: | --------: | -------: | ------------: | -----------: |
| front                        |  12 |   34 |        10 |         4 |       32 |            17 |            6 |
| front-extra (đã làm 4 / 4)   |   4 |   10 |         2 |         4 |       11 |             5 |            8 |
| fisheye                      |   8 |   10 |         8 |         9 |        8 |             1 |            4 |
| fisheye-extra (đã làm 4 / 4) |   4 |    0 |         3 |         4 |        2 |             0 |            0 |

## 3. Bảng ca khó

| Ảnh           | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| ------------- | ---- | ------------- | ------- | ----- |
| Chưa ghi nhận |      |               |         |       |

## 4. Phiếu QC 1 nhận được

Phiếu QC1 làm căn cứ: Phiếu tự kiểm từ lint revision 2 tại `NguyenManhQuang-qc1-for-NguyenManhQuang.md`; chưa có phiếu QC từ bạn kiểm.  
Lỗi đã sửa theo mã QC1: Chưa xác định mã nào đã sửa; lint revision 2 vẫn báo 27 cảnh báo.  
Lần nộp mới: `NguyenManhQuang-manifest.json`, revision 2 (tạo ngày 2026-11-21).  
Bạn kiểm lô của tôi: Chưa ghi nhận Quyết định nhận được: Chưa ghi nhận  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-02 | 8 | Chờ kiểm ảnh/coach xác nhận | Chưa xác nhận |
| QC1-04 | 3 | Chờ kiểm ảnh | Chưa xác nhận |
| QC1-05 | 3 | Chờ kiểm ảnh | Chưa xác nhận |
| QC1-11 | 10 | Chờ kiểm ảnh | Chưa xác nhận |
| QC1-12 | 3 | Chờ kiểm ảnh | Chưa xác nhận |

## 5. Kiểm file export

Đã mở và đọc được cả hai ZIP. Shape trong job CVAT chưa được đối chiếu. Cột camera xác nhận từ XML export.

| File                        | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --------------------------- | ------------ | --------------------------- | --------------------------- | ------------------------ |
| NguyenManhQuang-front.zip   | Có           | Chưa đối chiếu / 10         | Chưa đối chiếu / 7          | Có                       |
| NguyenManhQuang-fisheye.zip | Có           | Chưa đối chiếu / 4          | Chưa đối chiếu / 4          | Có                       |

## 6. Ảnh chụp màn hình

1. Tab Labels của project: [Cần chèn ảnh chụp]
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển): [Cần chèn ảnh chụp]
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: [Cần chèn ảnh chụp]
4. Một đoạn XML có `<polyline label="lane">`: submissions/images/xlm.png

## 7. Tự đánh giá

Theo lint revision 2, mã có nhiều cảnh báo nhất là QC1-11 (10 cảnh báo fisheye). Cần kiểm tra các đường cong và thêm điểm theo cung khi ảnh yêu cầu; đây là gợi ý tự đánh giá từ lint, chưa thay cho xác nhận của người gán nhãn.  
Ví dụ ảnh hưởng tới model: polyline fisheye không bám theo cung có thể làm model học sai vị trí/độ cong ranh giới làn, dẫn đến dự đoán làn lệch. Chưa xác nhận lỗi này đã được sửa.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor

| y               | 720 | 680 | 640 | 600 | 560 |
| --------------- | --: | --: | --: | --: | --: |
| x của chúng tôi |     |     |     |     |     |
| x của bạn kia   |     |     |     |     |     |

Trả lời 3 câu:

1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?
2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)?
3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?
