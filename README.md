# OSI
# Tổng quan mô hình OSI
Mô hình OSI (Open System Interconnection): là mô hình được tổ chức ISO đề xuất từ 1977 và công bố lần đầu vào 1984. Quy định những quy tắc để các PC và thiết bị mạng có thể liên lạc được với nhau theo một chuẩn nhất định. Mô hình OSI là một khuôn mẫu giúp chúng ta hiểu dữ liệu đi xuyên qua mạng như thế nào, đồng thời cũng giúp chúng ta hiểu được các chức năng mạng diễn ra tại mỗi lớp. Trong mô hình OSI có bảy lớp, mỗi lớp mô tả một phần chức năng độc lập:

![alt](https://www.9tut.com/images/ccna_self_study/OSI/OSI_Model.jpg)

Khi một thiết bị muốn gửi thông tin cho thiết bị khác, dữ liệu của nó phải đi từ lớp trên xuống lớp dưới cùng. Nhưng khi một thiết bị nhận thông tin này, nó phải đi từ dưới lên trên để "decapsulate(mở gói)". Trong thực tế, các hành động ngược lại ở đầu kia là rất tự nhiên trong cuộc sống của chúng ta. Nó tương tự như khi hai người liên lạc qua email. Đầu tiên, người viết phải viết chữ, chèn nó vào một phong bì khi người nhận đầu tiên phải mở phong bì và sau đó đọc email. Hình ảnh dưới đây cho thấy toàn bộ quá trình gửi và nhận thông tin:

![alt](https://www.9tut.com/images/ccna_self_study/OSI/OSI_Model_sending_receiving.jpg)



# Chi tiết các lớp
## Lớp Vật Lý

![alt](https://i.imgur.com/9zCAwWe.png)

1. Nhiệm vụ
- Là tầng dưới cùng của mô hình OSI, tương ứng với phần cứng mạng cơ bản, có nhiệm vụ truyền chuỗi các bit 0, 1 trên đường truyền vật lý.
- Tầng Vật lý chỉ làm việc với tín hiệu và môi trường truyền.
  - Định nghĩa các dạng dây cáp, card mạng, và các thiết bị vật lý khác.
  - Định nghĩa việc NIC ghép nối với phần cứng và cáp ghép nối với NIC.
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
   Ví dụ: chuẩn RS-232C/EIA-232-D

## Lớp Liên kết dữ liệu
1. Nhiệm vụ
- Tầng liên kết dữ liệu đảm bảo việc truyền tải dữ liệu một cách tin cậy giữa hai hệ thống có đường truyền vật lý nối trực tiếp với nhau. Đối với tầng mạng việc truyền dữ liệu giữa hai tầng vật lý coi như không có lỗi.
  - Tạo khung dữ liệu (frame)
  - Đồng bộ hóa
  - Kiểm soát lỗi
  - Kiểm soát luồng dữ liệu
2. Dịch vụ
- Tách hợp dữ liệu: Chia các gói tin tầng trên thành frame, và kết hợp các bit thành frame.
  - Mỗi khung chứa phần tiêu đề (Header), thông tin cần truyền đi (Data) và thông tin theo dõi khác (Trailer)
- Kiểm soát truy nhập
- Kiểm soát lỗi: Cung cấp cách phát hiện và sửa lỗi cơ bản để đảm bảo cho dữ liệu nhận được giống hoàn toàn với dữ liệu gửi đi.
  - Dò lỗi trên từng khung tin
  - Gửi khung báo nhận (nhận tốt, có lỗi)
- Kiểm soát luồng dữ liệu: Đảm bảo rằng bên truyền nhanh không làm tràn bộ đệm của bên nhận chậm dựa trên hai cơ
chế
  - Phản hồi
  - Giới hạn tần suất
3. Giao thức
- Giao thức truyền thông đồng bộ: Sử dụng ký tự đồng bộ, cho phép phân biệt dữ liệu của người dùng với các cờ và các vùng thông tin điều khiển khác.
- Giao thức truyền thông dị bộ: Sử dụng các bit đặc biệt (START, STOP) để gói dữ liệu truyền
  - Hướng ký tự
  - Hướng bit
4. Các tầng con
Trong LAN, IEEE chia tầng này thành 2 tầng phụ
- Tầng con điều khiển truy nhập đường truyền (Media Access Control _ MAC)
  - Giao tiếp với NIC
  - Quản lý các dạng đường truyền (media)
  - GT: 802.3 CSMA/CD (Ethernet), 802.4 Token Bus (ARCnet), 802.5 Token Ring…
- Tầng con điều khiển liên kết logic (Logical Link Control _ LLC).
  - Kiểm tra lỗi của các khung dữ liệu, quản lý kết nối giữa hai thiết bị truyền thông với nhau trên cùng một mạng con, điều khiển luồng và báo nhận việc truyền khung.
  - GT: 802.1 OSI Model 802.2 Logical Link Control

## Lớp Mạng 

![alt](https://vsolutions.vn/wp-content/uploads/2015/12/Network-layer-trong-mo-hinh-OSI-2.jpg)

1. Nhiệm vụ:
- Kết nối các mạng với nhau
- Xác định các địa chỉ mạng để quyết định việc chuyển gói tin
- Tìm đường (routing) và chuyển tiếp (switching) giúp các gói tin đi từ một mạng này đến một mạng khác. Router/ Relay hoạt động ở tầng này.
- Kiểm soát luồng dữ liệu và cắt hợp dữ liệu khi môt gói tin lớn muốn đi ngang một mạng con có kích thước gói tin tối đa quá nhỏ.
2. Dịch vụ
- 2 dạng dịch vụ:
  - Dịch vụ không liên kết: Các gói tin được đưa vào mạng con (subnet) một cách riêng lẻ và được vạch đường một cách độc lập nhau. Các gói tin gọi là Datagram và mạng con được gọi là Datagram Subnet.
  - Dịch vụ định hướng liên kết: Một đường nối kết giữa bên gởi và bên nhận phải được thiết lập trước khi các gói tin có thể được gởi đi. Nối kết này được gọi là mạch ảo (Virtual Circuit). Mạng con trong trường hợp này được gọi là VirtualCircuit Subnet. 
3. Giao thức 
- X25PLP (CCITT và ISO) phát triển từ Khuyến nghị về họ giao thức X25 (CCITT) phục vụ cho trường hợp hướng liên kết.
- IP (ISO 8473) phục vụ cho trường hợp không liên kết.
  - ARP; RARP, ICMP; RIP…
  - IPX
  - DECnet
 
## Lớp giao vận
1. Nhiệm vụ
- Thiết lập, duy trì và huỷ bỏ việc truyền dữ liệu giữa hai nút mạng.
- Thực hiện việc kiểm soát lỗi và kiểm soát luồng dữ liệu đảm bảo dữ liệu truyền giống hệt dữ liệu nhận.
- Nhận dữ liệu từ tầng phiên và phân đoạn dữ liệu.
2. Giao thức
- Giao thức tầng giao vận phụ thuộc rất nhiều vào bản chất của mạng.
  - Mạng loại A: Có tỷ suất lỗi và sự cố có báo hiệu chấp nhận được (tức là chất lượng chấp nhận được). Các gói tin được giả thiết là không bị mất. Tầng giao vận không cần cung cấp các dịch vụ phục hồi hoặc sắp xếp thứ tự lại.
  - Mạng loại B: Có tỷ suất lỗi chấp nhận được nhưng tỷ suất sự cố có báo hiệu lại không chấp nhận được. Tầng giao vận phải có khả năng phục hồi lại khi xảy ra lỗi hoặc sự cố.
  - Mạng loại C: Có tỷ suất lỗi không chấp nhận được (không tin cậy) hay là giao thức không liên kết. Tầng giao vận phải có khả năng phục hồi lại khi xảy ra lỗi và sắp xếp lại thứ tự các gói tin
- Giao thức lớp 0 (Simple Class - lớp đơn giản): Cung cấp các khả năng rất đơn giản để thiết lập liên kết, truyền dữ liệu và hủy bỏ liên kết trên mạng “có liên kết” loại A. GT có khả năng phát hiện, báo hiệu các lỗi nhưng không có khả năng phục hồi dẫn đến hủy bỏ liên kết nếu có lỗi.
- Giao thức lớp 1 (Basic Error RecoveryClass - Lớp phục hồi lỗi cơ bản) dùng với các mạngloại B. TPDU được đánh số. GT có khả năng báo nhận, truyền dữ liệu khẩn và phục hồi lỗi.
- Giao thức lớp 2 (Multiplexing Class - Lớp dồn kênh) là một cải tiến của lớp 0 cho phép dồn một số liên kết giao vận vào một liên kết mạng duy nhất, đồng thời có thể kiểm soát luồng dữ liệu để tránh tắc nghẽn. GT không có khả năng phát hiện và phục hồi lỗi. Do vậy nó cần đặt trên một nền tin cậy loại A.
- Giao thức lớp 3 (Error Recovery and MultiplexingClass - Lớp phục hồi lớp cơ bản và dồn kênh) là sự mở rộng giao thức lớp 2 với khả năng phát hiện, phục hồi lỗi và truyền lại dữ liệu theo “time-out”, nó cần đặt trên nền mạng loại B.
- Giao thức lớp 4 (Error Detection and RecoveryClass - Lớp phát hiện và phục hồi lỗi) có hầu hết các chức năng của các lớp trước và còn bổ sung thêm một số khả năng khác để kiểm soát việc truyền dữ liệu
- TCP, ARP, RARP; SPX
3. Dịch vụ
- 2 dạng dịch vụ
  - Hướng liên kết
  - Không liên kết
- Tại các điểm truy nhập dịch vụ tầng giao vận cung cấp các tham số của chất lượng dịch vụ để tầng trên có thể chỉ định loại dịch vụ mong muốn.

## Lớp Phiên
1. Nhiệm vụ
- Thiết lập, duy trì, đồng bộ hóa và hủy bỏ các phiên truyền thông (hội thoại) giữa các ứng dụng.
2. Dịch vụ
- Thiết lập một liên kết với một SS-User khác, trao đổi dữ liệu với người sử dụng đó một cách đồng bộ, và hủy bỏ liên kết một cách có trật tự khi không dùng đến nữa.
- Thiết lập các điểm đồng bộ hóa trong các hội thoại và khi xẩy ra sự cố có thể khôi phục lại việc hội thoại bắt đầu từ một điểm đồng bộ hóa đã thỏa thuận.
- Thương lượng hóa về việc dùng các thẻ bài (token) để trao đổi dữ liệu, đồng bộ hóa và hủy bỏ liên kết, sắp xếp phương thức trao đổi dữ liệu
3. Giao thức
- Được sử dụng trong một số trường hợp:
  - Cần kết hợp dữ liệu từ nhiều luồng dữ liệu
  - Cần có sự đồng bộ dữ liệu
  - Việc kết hợp, đồng bộ trong suốt với người sử dụng
  - NetBIOS Names Pipes, Mail Slots, RPC

## Lớp Trình Diễn
1. Nhiệm vụ
- Lớp này lấy dữ liệu đã được cung cấp bởi lớp ứng dụng, biến đổi chúng thành một định dạng chuẩn để lớp khác có thể hiểu được định dạng này. Tương tự như vậy lớp này cũng biến đổi dữ liệu mà nó nhận được từ lớp Phiên (lớp dưới) thành dữ liệu mà lớp Ứng dụng có thể hiểu được
- Lý do lớp này cần thiết đến vậy là vì các ứng dụng khác nhau có dữ liệu khác nhau. Để việc truyền thông mạng được thực hiện đúng cách thì dữ liệu cần phải được cấu trúc theo một chuẩn nào đó.
2. Dịch vụ và giao thức
- Dịch vụ
  - Mã hoá
  - Nén dữ liệu
  - Giải mã
  - Giải nén
- Giao thức
  - Giao thức tầng trình diễn thường được gói luôn trong các giao thức của tầng ứng dụng.

## Lớp Ứng dụng
1. Nhiệm vụ
- Cung cấp các phương tiện để người sử dụng có thể truy nhập được vào môi trường mạng.
2. Dịch vụ
- Không cung cấp các dịch vụ cho một tầng trên giống như các tầng khác mà cung cấp các dịch vụ cho các tiến trình của các ứng dụng trong tầng.
3. Giao thức
- Các giao thức bao quát tất cả các mục đích truy nhập mạng của ứng dụng của người sử dụng như truyền file, duyệt web, đọc thư,...
- DNS; FTP; TFTP; BOOTP; SNMP;RLOGIN; SMTP; MIME; NFS; FINGER; TELNET; NCP; APPC; AFP; SMB