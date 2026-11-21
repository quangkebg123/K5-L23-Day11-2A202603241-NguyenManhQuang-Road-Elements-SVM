# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): NguyenManhQuang Người kiểm (học viên): Chưa ghi  
Ngày: 2026-11-21 Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): NguyenManhQuang-front.zip và NguyenManhQuang-fisheye.zip (revision 2)  
Số ảnh kiểm: lint tự động 28 ảnh; chưa phải mẫu kiểm thủ công 6 ảnh Số nhãn đã kiểm (shape + tag): chưa thống kê theo mẫu thủ công

> Đây là các cảnh báo từ `road_check lint`, không phải kết luận QC thủ công. Cần xem ảnh để xác nhận; đặc biệt các cảnh báo QC1-02 có thể được miễn nếu coach xác nhận ảnh thật sự không thấy vạch. Chưa đưa quyết định Release / Hold / Rework.

## Tổng hợp theo mã

| Mã                                   | Loại lỗi                              | Số mục kiểm | Số lỗi | Mức          |
| ------------------------------------ | ------------------------------------- | ----------: | -----: | ------------ |
| QC1-01 tag camera                    | sai thuộc tính / bỏ sót               | lint 28 ảnh |      0 | nặng         |
| QC1-02 đủ L1, R1                     | bỏ sót                                | lint 28 ảnh |      8 | nặng         |
| QC1-03 position                      | sai thuộc tính / thừa                 | lint 28 ảnh |      0 | nặng         |
| QC1-04 tâm vạch, chiều, điểm dừng    | sai phạm vi / bỏ sót                  | lint 28 ảnh |      3 | chính        |
| QC1-05 vạch đứt, che                 | sai phạm vi / sai thuộc tính          | lint 28 ảnh |      3 | chính        |
| QC1-06 style, color, kind            | sai thuộc tính                        | lint 28 ảnh |      0 | chính        |
| QC1-07 vùng lái                      | sai phạm vi / bỏ sót / thừa           | lint 28 ảnh |      0 | chính        |
| QC1-08 đèn, màu                      | bỏ sót / sai phạm vi / sai thuộc tính | lint 28 ảnh |      0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính                        | lint 28 ảnh |      0 | chính        |
| QC1-10 hình in, đủ biển              | bỏ sót / sai phạm vi                  | lint 28 ảnh |      0 | chính        |
| QC1-11 fisheye                       | sai phạm vi / sai thuộc tính          | lint 28 ảnh |     10 | chính        |
| QC1-12 file                          | lỗi file                              | lint 28 ảnh |      3 | nhẹ          |

Lint tổng: 8 nặng, 16 chính, 3 nhẹ (27 cảnh báo).

## Danh sách lỗi (cảnh báo lint; cần xác minh bằng mắt)

|   # | Mã     | Ảnh | Nhãn (label, id) | Mức   | Mô tả ngắn                                                                |
| --: | ------ | --- | ---------------- | ----- | ------------------------------------------------------------------------- |
|   1 | QC1-04 | A01 | lane, #5         | chính | Điểm đầu cao hơn điểm cuối; kiểm tra chiều vẽ.                            |
|   2 | QC1-04 | A01 | lane, #6         | chính | Điểm đầu cao hơn điểm cuối; kiểm tra chiều vẽ.                            |
|   3 | QC1-05 | A01 | lane             | chính | Có 2 polyline cùng position L2; kiểm tra vạch đứt có bị tách không.       |
|   4 | QC1-02 | A03 | lane             | nặng  | Thiếu L1; Không nhìn thấy.                                                |
|   5 | QC1-04 | A03 | lane, #0         | chính | Điểm đầu cao hơn điểm cuối; kiểm tra chiều vẽ.                            |
|   6 | QC1-05 | A04 | lane             | chính | Có 2 polyline cùng position L1; kiểm tra vạch đứt có bị tách không.       |
|   7 | QC1-02 | A05 | lane             | nặng  | Thiếu L1; Không nhìn thấy.                                                |
|   8 | QC1-02 | A05 | lane             | nặng  | Thiếu R1; Không nhìn thấy.                                                |
|   9 | QC1-02 | A06 | lane             | nặng  | Thiếu R1; Không nhìn thấy.                                                |
|  10 | QC1-02 | A07 | lane             | nặng  | Thiếu L1; Không nhìn thấy.                                                |
|  11 | QC1-12 | A08 | lane, #4         | nhẹ   | Có 1 điểm lặp liền nhau tại (46,359); kiểm tra và xóa điểm thừa nếu cần.  |
|  12 | QC1-05 | A08 | lane             | chính | Có 2 polyline cùng position L1; kiểm tra vạch đứt có bị tách không.       |
|  13 | QC1-02 | A09 | lane             | nặng  | Thiếu R1; Không nhìn thấy.                                                |
|  14 | QC1-12 | A10 | road_curb, #3    | nhẹ   | Có 1 điểm lặp liền nhau tại (3,489); kiểm tra và xóa điểm thừa nếu cần.   |
|  15 | QC1-02 | A10 | lane             | nặng  | Thiếu R1; Không nhìn thấy.                                                |
|  16 | QC1-02 | A14 | lane             | nặng  | Thiếu R1; Không nhìn thấy.                                                |
|  17 | QC1-11 | B01 | road_curb, #3    | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  18 | QC1-11 | B02 | road_curb, #2    | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  19 | QC1-11 | B02 | road_curb, #3    | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  20 | QC1-11 | B03 | road_curb, #8    | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  21 | QC1-11 | B03 | traffic_sign, #1 | chính | Lint gợi ý bật edge_zone; xác minh vị trí box thủ công.                   |
|  22 | QC1-12 | B06 | lane, #1         | nhẹ   | Có 1 điểm lặp liền nhau tại (205,294); kiểm tra và xóa điểm thừa nếu cần. |
|  23 | QC1-11 | B07 | lane, #1         | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  24 | QC1-11 | B07 | lane, #2         | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  25 | QC1-11 | B07 | lane, #3         | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  26 | QC1-11 | B08 | lane, #1         | chính | Polyline chỉ có 3 điểm; kiểm tra đường cong fisheye.                      |
|  27 | QC1-11 | B09 | road_curb, #0    | chính | Polyline chỉ có 2 điểm; kiểm tra đường cong fisheye.                      |

## Ca mơ hồ

| Ảnh                               | Câu hỏi cho lead                                                                                                        | Lời đáp (nếu có)        |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| A03, A05, A06, A07, A09, A10, A14 | Các vị trí thiếu L1/R1 có thực sự không thấy vạch sơn không? Nếu không thấy, coach xác nhận để áp dụng ngoại lệ QC1-02. | Chờ coach xác nhận      |
| B03                               | Box traffic_sign #1 có nằm trong edge zone theo ảnh không?                                                              | Chờ người kiểm xác minh |

## Quyết định

Lỗi nặng theo lint: 8 Lỗi chính theo lint: 16 / chưa có mẫu số nhãn đã kiểm thủ công Lỗi nhẹ theo lint: 3 Ca chờ lead: 8  
Quyết định (Release / Hold / Rework): Chưa kết luận — cần kiểm ảnh thủ công và xác nhận ngoại lệ QC1-02.  
Lý do: Lint chỉ đưa cảnh báo. Quyết định chính thức cần dựa trên mẫu kiểm 6 ảnh, số nhãn đã kiểm và xác minh các ca mơ hồ theo luật của phiếu.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
