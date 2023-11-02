---
type: LVTN
---
# Bài luận văn
---
[[LVTN_NguyenGiaThinh.pdf]]

# Nội dung chính
---
1. Thiết kế cấu hình cho thân, cánh và đuôi
2. Phân tích đặc tính khí động lực học qua phần mềm XFLR5
3. Lập trình các phần mềm xử lý dữ liệu thí nghiệm lực đẩy
4. Phân tích đặc tính ổn định, điều kiện trim ở các chế độ bay 
5. Xây dựng mô hình động lực học
6. Xây dựng và phát triển bộ điều khiển PID, thử nghiệm đặc tính bộ điều khiển qua Simulink

**Các phần mình có thể sử dụng**: 2, 4, 5, 6

# Thiết kế cấu hình và kích thước cánh
---
- Phương pháp: Đi khảo sát thực tế các máy bay cùng loại -> đưa ra mối liên hệ về thông số thiết kế.
![](https://i.imgur.com/BlhULuv.png)

- Khối lượng của máy bay 6.5kg:
  ![](https://i.imgur.com/8K3qFSA.png)

- Thông số của cánh:
![](https://i.imgur.com/sgrPJMR.png)
>Note: Nếu có dự tính thay đổi góc tấn của cánh thì chỉ được tới tối đa ~6 để maximize cái Cl/Cd

- Cl = 0.5074 (this is at 35m above sea level and 25C)
