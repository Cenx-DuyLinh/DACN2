---
type: LVTN
---
# Bài luận văn
---
![[Nguyễn-Xuân-Thành-Đạt_1610667_213700 (1).pdf]]
# Nội dung luận văn
---
>Thiết kế một hệ thống MAV (Micro Air Vehicle) để có thể bay được hết một đoạn đường mòn.

>Xây dựng mô hình AI phù hợp

>Thiết kế giải thuật bay tự động

# Bộ điều khiển PID
---
>Sử dụng bộ điều khiển PID rời rạc

>Tham khảo bộ PID điều khiển từ góc sang motor power của Ardupilot

>Tham khảo bộ điều khiển để di chuyển ngang (XY):
>- Sai số vị trí -> vân tốc cần phải đạt được (P)
>- Sai số vận tốc -> gia tốc + góc bay tương ứng (PID)-> input cho góc sang motor power

>Tham khảo bộ điều khiển để di chuyển dọc (Z):
>- Sai số độ cao-> vân tốc leo cần phải đạt được (P)
>- Sai số vận tốc leo -> gia tốc leo (PID)
>- Sai số gia tốc leo -> giá trị cần ga (PID)

*Sử dụng phần này nếu mình được giao phần điều khiển máy bay*

# AI
---
>Tạm thời bỏ qua

# Triển khai hệ thống dẫn hướng
---
> Anh Đạt cũng kết nối từ máy tính nhúng sang mạnh controller bằng giao tiếp UART 

# Phần cứng
---
>Phần này anh đạt chủ yếu chỉ nói về các lý thuyết của thiết bị chứ không có thông tin gì nhiều
## 1. Động cơ
>Từ các bảng thống số thử nghiệm của cặp động cơ lấy được trên mạng ảnh tính:
>- Đồ thị Throttle -Thrust 
>- Đồ thị Thrust - Amps - Watt
>**Công dụng**: Xài thrust để tính ra watt ở phần sau

## 2. Flight controller
>Phân tích về:
>- Thông số cơ bản của thằng Durandal 
>- 

…

# Tính toán khối lương, khả năng, thời gian bay
---
1. Liệt kê hết các thông số về khối lượng của từng thiết bị -> lực nâng cần có của máy bay lúc bay bằng 
2. Từ lực nâng của mỗi motor -> watt cần thiết (cộng thêm khoảng 20% vì các lí do này nọ)
3. Lấy lượng pin chia ra rồi xem là có đủ thời gian bay không

![](https://i.imgur.com/HJyhOhE.png)

# Bay thử và đánh giá số liệu
---
1. Anh Đạt phân tích là lần đó ảnh thực hiện các chế độ gì, nói chung chủ yếu là ghi lại quá trình ảnh thử nghiệm 
2. Phân tích cái đáp ứng giữa phần điều khiển và phần thực tế (khalachackeo ảnh lấy ở trong log ra)
3. Các phần PID ảnh điều chỉnh thông qua thằng điều chỉnh của mission planner 
**Những thứ mình áp dụng được**: Thử nghiệm -> đánh giá xem nó ntn -> điều chỉnh -> thử lại và so sánh với lần thử nghiệm trước 

# Phần thử nghiệm cho AI
---
>Tạm chưa xem đánh giá