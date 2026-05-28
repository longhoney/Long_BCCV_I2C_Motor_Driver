# Khảo sát thư viện Makerlabvn_SimpleMotor
1. Đối tượng dùng để khảo sát: L9110, MKE-Creator, (L298)
2. Quy ước chiều động cơ và cách kết nối với driver
    - Thông số tốc độ: 0-100% --> analogWrite() 0-255
    - Thông số chiều quay thuận: 1 = Quay thuận chiều kim đồng hồ - xe đi tới. --> digitalWrite(IN2,1); digitalWrite(IN1,0) 
    - Thông số chiều quay ngược: 0 = Quay ngược chiều kim đồng hồ - xe đi lùi. --> digitalWrite(IN2,0); digitalWrite(IN1,1)
    - Quy ước cho MKE-Creator
<img width="1050" height="752" alt="image" src="https://github.com/user-attachments/assets/4f182db8-b279-43d9-857e-f384226559cc" />

    - Quy ước cho L9110
<img width="1514" height="612" alt="image" src="https://github.com/user-attachments/assets/9a3d9d16-ae5a-43e8-9f6f-a0e041cd63d3" />

    - Quy ước cho L298
<img width="1056" height="484" alt="image" src="https://github.com/user-attachments/assets/12fe4215-1cb1-4d21-a8cf-980c7b258cce" />

4. Nhánh điều khiển (lấy 1 Example Test Motor làm ví dụ)
    - Người dùng Khai báo chân điều khiển --> Cấu hình đối tượng
    - Người dùng điền thông số tốc độ (0-100%) vào hàm tương ứng để đối tượng thực hiện lệnh:
<img width="1390" height="327" alt="image" src="https://github.com/user-attachments/assets/fd2a4de9-7deb-401e-854f-5f7ce7a828fd" />

<img width="1774" height="351" alt="image" src="https://github.com/user-attachments/assets/051f073a-cba6-4b6b-bf91-36772de8472d" />

<img width="747" height="259" alt="image" src="https://github.com/user-attachments/assets/fdba2dc4-a2f3-4dec-adbc-ac3d195ddf86" />

    - Thư viện chuyển đổi Tốc độ 0-100%  thành PWM 0-255 và gửi đến motor driver --> Động cơ quay theo tốc độ và chiều quay được yêu cầu
5. Dùng logic analyzer để khảo sát PWM tại OUTPUT và điền vào [Bảng giá tri](https://docs.google.com/spreadsheets/d/1pauv_eXI9WxPK2DNi59jDcf7WH-pYOTJTPTRPNfatLw/edit?gid=0#gid=0)

# Tạo thư viện kế thừa Makerlabvn_SimpleMotor_LONG
[code cơ bản --> function để làm gọn chương trình chính --> thư viện để TÁI SỬ DỤNG]
1. Gom 3 chương vào chung thư viện, viết readme HDSD define chân và setup
2. Bấm số để điều khiển
3. Bổ sung chương trình dành cho L9110
4. Kiêm tra chương trình bằng Logic analyzer
