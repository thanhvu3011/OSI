# OSI
# Tổng quan mô hình OSI
Mô hình OSI (Open System Interconnection): là mô hình được tổ chức ISO đề xuất từ 1977 và công bố lần đầu vào 1984. Quy định những quy tắc để các PC và thiết bị mạng có thể liên lạc được với nhau theo một chuẩn nhất định. Mô hình OSI là một khuôn mẫu giúp chúng ta hiểu dữ liệu đi xuyên qua mạng như thế nào, đồng thời cũng giúp chúng ta hiểu được các chức năng mạng diễn ra tại mỗi lớp. Trong mô hình OSI có bảy lớp, mỗi lớp mô tả một phần chức năng độc lập:

![alt](https://www.9tut.com/images/ccna_self_study/OSI/OSI_Model.jpg)

Khi một thiết bị muốn gửi thông tin cho thiết bị khác, dữ liệu của nó phải đi từ lớp trên xuống lớp dưới cùng. Nhưng khi một thiết bị nhận thông tin này, nó phải đi từ dưới lên trên để "decapsulate(mở gói)". Trong thực tế, các hành động ngược lại ở đầu kia là rất tự nhiên trong cuộc sống của chúng ta. Nó tương tự như khi hai người liên lạc qua email. Đầu tiên, người viết phải viết chữ, chèn nó vào một phong bì khi người nhận đầu tiên phải mở phong bì và sau đó đọc email. Hình ảnh dưới đây cho thấy toàn bộ quá trình gửi và nhận thông tin:

![alt](https://www.9tut.com/images/ccna_self_study/OSI/OSI_Model_sending_receiving.jpg)



# Chi tiết các lớp
## Lớp Vật Lý

![alt](C:\Users\admin\Pictures\Screenshots)

1. Nhiệm vụ
- Là tầng dưới cùng của mô hình OSI, tương ứng với phần cứng mạng cơ bản, có nhiệm vụ truyền chuỗi các bit 0, 1 trên đường truyền vật lý.
- Tầng Vật lý chỉ làm việc với tín hiệu và môi trường truyền.
  - Định nghĩa các dạng dây cáp, card mạng, và các thiết bị
vật lý khác.
  - Định nghĩa việc NIC ghép nối với phần cứng và cáp
ghép nối với NIC.
  - Định nghĩa các kỹ thuật để truyền các tín hiệu (dòng bit)
trên cáp.
2. Dịch vụ và giao thức
- Dịch vụ
  - Truyền dữ liệu giữa hai hệ thống trong một đường truyền vật lý.
- Giao thức
  - Dữ liệu được truyền đi theo dòng bit nên giao thức không có ý nghĩa giống như các tầng khác.
  - Không có PDU và PCI cho tầng Vật lý
  - Quy định về phương thức truyền (đồng bộ, dị bộ), tốc độ truyền …
  - IEEE 802, ISO 2110,ISDN …
3. Chuẩn giao diện với đường truyền
- Đặc tả đặc trưng về cơ, điện, chức năng, thủ tục của giao diện/đầu nối nối kết giữa các thiết bị DTE và DCE
  - DTE: Thiết bị đầu cuối dữ liệu (Data Terminal Equipment) ví dụ như máy tính
  - DCE: Thiết bị cuối kênh dữ liệu (Data Circuit –Terminating Equipement) ví dụ như modem chuyển đổi tín hiệu biểu diễn dữ liệu của ngườisử dụng thành dạng tín hiệu chấp nhận được bởi đường truyền và ngược lại.
   Ví dụ: chuẩn RS-232C/EIA-232-D (tk)
