# Báo cáo cá nhân — Ngày 11
Họ tên: Đinh Quang Thắng               Mã học viên: 2A202603152  
Phiên bản CVAT (Help → About): 2.82.0  
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 2  
Thời điểm export (ngày giờ trên CVAT): bản Rework tạo lúc 21/11/2026 14:23:16 +07:00    Số lần nộp lại sau Rework: 1  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng theo guideline | lane: polyline; road_curb: polyline; crosswalk: polygon; drivable: polygon; traffic_light: rectangle; traffic_sign: rectangle. |
| Thuộc tính và giá trị | Đúng theo guideline | lane có position/style/color/kind; drivable có area_type; traffic_light có color/type/facing/edge_zone; traffic_sign có group/facing/edge_zone. |
| 4 tag ảnh | Đúng theo guideline | camera, timeofday, weather, source; mỗi tag dùng thuộc tính select `value`. |
Cách kết thúc polyline trên bản CVAT này: Bấm phím **N** sau khi click các điểm theo thứ tự từ gần xe ra xa.  
Cách đặt tag ảnh trên bản CVAT này: Chọn công cụ Tag, đặt camera trước, rồi lần lượt timeofday, weather và source; mở Details để kiểm thuộc tính `value`.  

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 27 | 10 | 4 | 23 | 18 | 13 |
| front-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| fisheye | 8 | 8 | 10 | 7 | 10 | 5 | 1 |
| fisheye-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Ghi chú: số shape lấy trực tiếp từ hai ZIP và manifest revision 2. Tổng số nhãn đã kiểm theo Phiếu QC 1 là 58.

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A05_b2576c8c-2de20b8a.jpg | lane L1/R1 | Ảnh có hay không thật sự có hai vạch chủ đạo hay lint chưa ghép lane | Coach xác nhận không gán | QC1-02 ghi thiếu L1/R1; cảnh thực tế không có vạch |
| A06_b8c66e31-c8468690.jpg | lane R1 | R1 có nhìn thấy hay không tại ngã giao | Coach xác nhận không gán | QC1-02 ghi thiếu R1; cảnh thực tế không có vạch |
| A07_b41ace08-c8468690.jpg | lane L1 | L1 có thật sự xuất hiện không | Coach xác nhận không gán | QC1-02; cảnh thực tế không có vạch |
| A09_c7e6d5d1-c8af9fe3.jpg | lane R1 | R1 có thật sự xuất hiện không | Coach xác nhận không gán | QC1-02; cảnh thực tế không có vạch |
| B02_03177_FV.png | lane L1/R1 và các tag thuộc tính đèn/biển | Vạch L1/R1 có nhìn rõ ở đoạn nào; box đèn/đèn hướng có thuộc tính nào | Coach xác nhận | QC1-01 đã xác nhận tag camera sai |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: Lê Văn Trung Tính. Quyết định ban đầu: Rework. Quyết định sau Rework: **Đạt (Release).**  
Sau khi nhận phiếu: đã sửa toàn bộ lỗi được ghi nhận; bản sửa được lưu dưới revision 2. Coach xác nhận cảnh thực tế không có vạch tại A05, A06, A07, A09 và B02, nên các cảnh báo QC1-02 tại các ảnh này được miễn; không còn lỗi nặng sau Rework.  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-01 tag camera | 1 | Đồng ý | Đã sửa |
| QC1-02 đủ L1, R1 | 5 | Đồng ý | Đã sửa |
| QC1-03 position | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-04 tâm vạch, chiều, điểm dừng | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-05 vạch đứt, che | 3 | Đồng ý | Đã sửa |
| QC1-06 style, color, kind | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-07 vùng lái | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-08 đèn, màu | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-09 facing, type, group, biển phụ | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-10 hình in, đủ biển | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-11 fisheye | 0 | Đồng ý | Không có lỗi; không cần sửa |
| QC1-12 file | 5 | Đồng ý | Đã sửa |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| DinhQuangThang-front.zip | Có, revision 2 mở và parse được | A01: 12 / 12 | A02: 10 / 10 | Có; 12 ảnh đều có đủ 4 tag |
| DinhQuangThang-fisheye.zip | Có, revision 2 mở và parse được | B01: 9 / 9 | B02: 11 / 11 | Có; camera đã sửa thành `fisheye_front` |

## 6. Ảnh chụp màn hình
1. Tab Labels của project: [01-labels.png](../report-images/01-labels.png)
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển): [02-front.png](../report-images/02-front.png)
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: [03-fisheye.png](../report-images/03-fisheye.png)
4. Một đoạn XML có `<polyline label="lane">`: [04-polyline-xml.png](../report-images/04-polyline-xml.png)

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20: QC1-02 với 5 cảnh báo thiếu L1/R1. Trước khi export, so từng ảnh với quy tắc: xác nhận lane nhìn thấy; kiểm cả hai vạch chủ đạo; nếu ảnh thật sự không có vạch thì ghi ca mơ hồ và xin coach xác nhận thay vì vẽ thêm hoặc để thiếu.  
Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào: Với lỗi QC1-05, một vạch đứt bị tách thành hai polyline thay vì một polyline liên tục (có occluded qua chỗ che). Mô hình sẽ học sai cấu trúc từng mẩu riêng rời thay vì cùng một trung tâm vạch, làm dự đoán bị gián đoạn hoặc lệch vị trí. Khi sửa, ghép thành đúng một polyline và bật occluded cho đoạn bị che.  

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của chúng tôi | 710.7 | 654.4 | 598.1 | 541.8 | 485.8 |
| x của bạn kia | không có làn | không có làn | 601.4 | 543.3 | 485.1 |

Trả lời 3 câu:

1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?
   - Polyline được vẽ gần xe ra xa. Dừng 40 px trước điểm xa có thể làm các hàng xa nhất 600 và 560 mất lái; nếu điểm dừng dịch theo tọa độ y chứ không theo chiều dọc đầy đủ, cần đánh giá lại theo giao của polyline với từng hàng.
2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)?
   - Tại y=720: bạn kia không có làn nên không chênh lệch pixel định lượng; bạn của bạn chỉ có x=710.7. Tại y=560: lệch 0.7 px (485.8 − 485.1). Lệch gần xe tại y=720 ảnh hưởng LKA nhiều hơn vì sai số gần xe quyết định hướng lái hiện tại.
3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?
   - Giá trị x tại cùng một hàng y về lý thuyết không đổi nếu script vẫn nội suy theo đúng tập điểm; cách tính đổi về thứ tự dữ liệu. `rowanchor` và mọi script giả định điểm đầu là gần xe/dừng đúng đầu xa gần có thể gặp khó khi polyline đảo chiều, dẫn tới nội suy hoặc xác định điểm đầu sai.
