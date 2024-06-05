# Note
Note From Prev Lesson:

1. What is the internet -> Inter: Among | Net: Network -> Internet ->
2. What is a domain -> Domain: Tên miền = "địa chỉ nhà" của web. Thời chưa có Domain thì để access vô web nào thì phải gõ IP của nó ra. VD: 113.161.(...) -> www.thpt-lehongphong-tphcm.edu.vn (.vn ở đây gọi là TLD: Top Level Domain. Có nhiều loại như .com, .us, .uk,...) (.edu ở đây gọi là SLD: Second Level Domain, cũng giống TLD những nằm ở dưới) (.thpt-lehongphong-tphcm là Third Level Domain) (www là subdomain, không lúc nào cũng là www, VD như: "meet" là subdomain trong meet.google.com)
3. URL vs domain
4. 

Note:
Switch là cục để cắm máy tính vô để chuyển đổi mạng 
(VD có 10 cái máy thì 1 cái máy phải nối với 9 cái máy còn lại để kết nối. Switch khiến cho đổi 1 Input -> 1 Output nên mỗi máy chỉ cần 1 cổng LAN để kết nối với Switch và Output ra 9 máy khác)

Router là cục Switch gắn thêm cục phát Wifi

ISO - OSI model (mô hình Internet) (Open System Interconnection)

Layer 1: Application -> Function: Cung cấp giao diện để thao tác với mạng. EX: HTTP, FTP, SMTP, DNS

Layer 2: Presentation -> Function: Encrypt, xử lý dât khi được gửi lên mạng

Layer 3: Session (Phiên đăng nhập) -> Function: Quản lý kết nối VD: Kết nối Google Meet thì trên Google Meet sẽ có cái session của mình, Cookie.  

Layer 4: Transport -> Function: Thiết lập các Protocol cao hơn

Layer 5: Network (Đáy Virtually) -> Nói ngắn gọn: là IP của mình. VD: Cung cấp IP cho Layer 4

Layer 6: Data Link -> Function: Có IP rồi thì dùng Data Link để đi. VD: Là Switch, Ethernet (MAC Address: Địa chỉ THỰC TẾ của thiết bị chứ không phải ĐỊA CHỈ trên mạng (IP))

Layer 7: Physical (Dây nhợi ngoài đời) (Đáy của Internet)


Ethernet 

>DNS : Domain Name Server

VD: nhập www.thpt-lehongphong-tphcm.edu.vn và search. Khi này Browser sẽ "hỏi" cache có ip nào tương ứng với domain đó ko. Hỏi không có-> hỏi hệ điều hành -> biết thì nhả ip -> ko biết thì hỏi cái server là DNS resolver hay DNS server. thg này có nhiệm vụ là khi thg OS nhả cho nó cái string domain rồi cái thg resolver đi kiểm tra cái cache của nó -> có thì nhả ip cho OS r OS nhả lại cho browser. không có thì thg DNS sẽ đi hỏi thg ISP (Internet Service Provider)-> Có thì nhả về cho DNS Resolver -> ko có thì ISP tìm cache -> ko có thì nó đi hỏi TLD server của nó (ở đây là .vn), để làm thế thì nó sẽ đi đem cái .vn cho thằng Root Name Server xong nó trả lại cho mình cái địa chỉ IP của thg TLD server, mình đưa lại cái này cho thằng TLD tuy thg TLD ko biết cái domain đó là gì nhưng biết ai (server nào) là người giữ nó xong nó cho mình cái địa chỉ của thg authoritative name server (là thg giữ hết tất cả mọi thông tin lên quan đến cái domain đó), thg ANS này sẽ đưa cho nhà mạng (ISP) cái IP của Domain cần tìm rồi từ đó, ISP sẽ trả lại cho DNS Resolver/Server (và bỏ vô cache luôn để sau này đỡ tìm), sau đó DNS Resolver/Server trả về OS (và bỏ vô cache luôn), sau đó OS trả về browser (và bỏ vô cache luôn) rồi browser cx bỏ vô cache của nó.


Q: Vì sao TLD biết được thg ANS nào quản lý IP của cái Domain nào nhưng lại không biết IP của chính cái Domain đó?

A: Lúc đăng kí Domain thì nó có một cái list những ANS (glue record) trong một cái zone riêng với các ANS khác được gửi cho thg TLD để nó quản lý chứ nó ko biết cái domain đó là gì

>HTTP: HyperText Transfer Protocol

Protocol: -> (Thủ tục) VD: Để hỏi giờ một người lạ thì:

Mình: Hi
Ngta: Hi
(Hi-Hi = Protocol)
Mình: Mấy giờ r bri
Ngta: 10h20

(Hi-Hi-Mấy giờ r bri-10h20 = Protocol)

TCP: Mình gửi tính hiệu SYN(Synchronize) đến Server, xong nó gửi SYN-ACK(Synchronize-Acknowledge) để mình biết nó nhận rồi, rồi mình gửi lại ACK cho nó để nó biết đã thiết lập kết nối 2 chiều, giờ m muốn gửi data qua lại gì thì cứ thoải mái.
Sau TCP thì mình sẽ bắt đầu gửi cái string yêu cầu gì đó, sau đó server sẽ gửi lại cái string có cái answer.	

HTTPS > HTTP vì HTTPS: HyperText Transfer Protocol Secure. Vì HTTP gửi plain text nên ko secure, một bên third party sú sú có thể nhảy vô đọc và lấy một bản copy để lấy thông tin nên ko secure. Còn HTTPS thì sẽ có một cái bước là TLS (Transport Layer Secure) để encrypt cái plain text đó và cái này chỉ có bên nhận và bên gửi biết cách decrypt, bên ngoài CÓ THỂ try to decrypt nma REALLY lâu nên nuh uh.
