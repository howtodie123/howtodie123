---
title: Ôn tập An toàn mạng máy tính - Cấp cứu 2 tờ A4
date: 2023-12-30 13:00:00 +0700
author: thu4n
categories: [Learning]
image: /assets/img/other/tet-cuu.png
tags: [computer network, network security, sysadmin]
---

Xin chào các bạn, trong bài viết lần này mình sẽ cố gắng tóm tắt về môn học NT101 - An toàn mạng máy tính theo chương trình giảng dạy cho lớp Mạng tại UIT. Nội dung khá là dài nhưng thầy đã rộng lượng cho tận **2 tờ A4** thì có vẻ sẽ đủ, thời gian làm bài nếu mình nhớ không lầm thì đâu đó khoảng **75 phút**. Nôm na là thế, chúng ta sẽ có **8 chương** tổng cộng cần phải ôn tập nên mình vô thẳng nội dung chính luôn thôi.

Note: Cần bổ sung các hình ảnh minh họa.
## I. Tổng quan

### A. Một số khái niệm

#### Dữ liệu

Dữ liệu là một tập hợp các dữ kiện, chẳng hạn như số, từ, hình ảnh, nhằm đo lường, quan sát hoặc chỉ là mô tả về sự vật. Dữ liệu gồm có 2 trạng thái:
- Transmission state (Dữ liệu đang được trao đổi, truyền tải)
- Storage state (Dữ liệu đang được lưu trữ)

Khi trao đổi dữ liệu, có 4 yêu cầu như sau:
1. **Tính bí mật** (Confidentiality) - Khả năng chỉ cho phép những người có quyền truy cập vào thông tin đó
2. **Tính toàn vẹn** (Integrity) - Khả năng đảm bảo rằng thông tin không bị thay đổi hoặc sửa đổi mà không được phép. 
3. **Tính không thể từ chối** (Non-repudiation) - Khả năng xác định người gửi hoặc người nhận một thông điệp.
4. **Tính sẵn sàng (Availability)** - Khả năng đảm bảo rằng thông tin hoặc hệ thống có sẵn khi cần thiết.

#### Một số khái niệm khác

- Tam giác bảo mật bao gồm 3 thành phần là **Security** (Restrictions), **Functionality**(Features) và **Usability**(GUI). Khi ta thiên về một thành phần nào thì 2 thành phần còn lại trong tam giác sẽ bị yếu đi. VD: Tăng tính bảo mật thì sẽ hạn chế hơn về tính năng và giao diện ít thân thiện người dùng hơn, ngược lại, nếu thêm nhiều tính năng mới thì dễ có lỗ hỏng bảo mật và người dùng sẽ gặp khó khăn hơn khi mới sử dụng lần đầu.

### B. Các kỹ thuật tấn công phổ biến và cơ chế phòng thủ

#### 1. Eavesdropping (Nghe trộm)

- Cách thức tấn công: Sử dụng một thiết bị mạng (router, card mạng…) và một ứng dụng (Tcpdump, Ethereal, Wireshark…) để giám sát lưu lượng mạng, bắt các gói tin đi qua thiết bị này. Từ đó, "nghe trộm" được thông tin từ các phiên trao đổi dữ liệu.
- Nhận xét: Thực hiện dễ dàng hơn với mạng không dây. **Không** có cách nào ngăn chận việc nghe trộm trong một mạng công cộng.
- Cách phòng chống: Mã hoá dữ liệu trước khi truyền chúng trên mạng.

#### 2. Cryptanalysis

- Cách thức tấn công: Sử dụng một hoặc nhiều phương pháp khác nhau để tìm kiếm thông tin hữu ích từ dữ liệu đã mã hoá mà không cần biết khoá giải mã. Điển hình là phương pháp giải mã thông qua thống kê **tần suất xuất hiện** của các ký tự.
- Nhận xét: Khi sử dụng phương pháp phân tích thông kê tần suất, cần phải sử dụng các công cụ toán học và máy tính có hiệu suất cao khi cipher text có kích thước lớn dần.
- Cách phòng chống: Sử dụng những giải thuật mã hoá không thể hiện cấu trúc thống kê trong chuỗi mật mã; Sử dụng khoá có độ dài lớn để chống Brute-force attacks.

#### 3. Password Pilfering

Cơ chế chứng thực được sử dụng rộng rãi nhất là dùng username - tên người dùng và password - mật khẩu.

Password Pilfering là một hình thức tấn công nhằm đánh cắp mật khẩu của người dùng, có nhiều phương pháp khác nhau để thực hiện điều này.

**3.1. Guessing**

- Đúng như tên của nó, đây là đoán mật khẩu, hiệu quả khi đối phương có mật khẩu ngắn hoặc đang sử dụng mật khẩu mặc định.
- 10 mật khẩu phổ biến nhất trên Internet (bảng xếp hạng này tương đối cũ, không phải của hiện nay):
    1. Password
    2. 123456
    3. qwerty
    4. abc123
    5. letmein
    6. monkey
    7. myspace1
    8. password1
    9. blink182
    10. <"Tên của người dùng"> 

**3.2. Social engineering**

- Là phương pháp sử dụng các kỹ năng xã hội để ăn cắp thông tin mật của người khác thông qua các thủ thuật như Mạo danh, Lừa đảo qua email, Thu thập thông tin từ giấy tờ bị loại bỏ, Tạo trang web đăng nhập giả hoặc chỉ đơn giản là Kết bạn làm quen rồi lấy cắp thông tin cá nhân của mục tiêu.
- Ý kiến cá nhân: Đây có thể được xem là phương pháp nguy hiểm nhất khi nó tấn công vào yếu tố con người nhiều hơn là hệ thống.

**3.3. Dictionary Attacks**

- Tên tiếng Việt là tấn công từ điển, thực hiện bằng cách duyệt tìm từ một từ điển (thu được từ các file SAM của Window, /etc/passwd trong Linux) các username và password đã được mã hoá.

**3.4. Password Sniffing**

- Là một phần mềm dùng để bắt các thông tin đăng nhập từ xa như username và password đối với các ứng dụng mạng phổ biến như Telnet, FTP, SMTP, POP3.
- Cách phòng chống Password Sniffing là sử dụng các giao thức như HTTPS, SSH để mã hóa toàn bộ thông điệp truyền đi.

**3.5. Một số quy tắc bảo vệ mật khẩu**

1. Sử dụng mật khẩu dài kết hợp giữa chữ thường, chữ hoa, số và các ký tự đặc biệt. Không dùng các từ có trong từ điển, các tên và mật khẩu thông dụng => gây khó khăn cho việc đoán mật khẩu và tấn công sử dụng từ điển.
2. Không tiết lộ mật khẩu với những người không có thẩm quyền hoặc qua điện thoại, thư điện tử hoặc bất kỳ phương tiện truyền thông nào => chống lại social engineering.
3. Thay đổi mật khẩu định kỳ và không sử dụng trở lại những mật khẩu cũ => Chống tấn công sử dụng từ điển.
4. Không sử dụng cùng một mật khẩu cho các tài khoản khác nhau.
5. Không sử dụng những phần mềm đăng nhập từ xa mà không có cơ chế mã hoá như là Telnet.
6. Huỷ hoàn toàn các tài liệu có lưu các thông tin quan trọng sau khi sử dụng xong mục đích ban đầu.
7. Tránh nhập các thông tin trong các cửa sổ popup và Không click vào các đường liên kết lạ, không rõ nguồn gốc.

#### 4. Identity Spoofing

- Là phương pháp tấn công cho phép kẻ tấn công mạo nhận nạn nhân mà không cần sử dụng mật khẩu của nạn nhân.
- Các phương pháp phổ biến bao gồm:
    - Man-in-the-middle attacks
    - Message replays attacks
    - Network spoofing attacks
    - Software exploitation attacks

**4.1. Man-in-the-middle**

– Kẻ tấn công cố gắng dàn xếp với thiết bị mạng (hoặc cài đặt một thiết bị của riêng mình) giữa hai hoặc nhiều người sử dụng, sau đó chặn và sửa đổi hay làm giả dữ liệu truyền giữa những người sử dụng rồi tiếp tục truyền chúng tới địa chỉ đích như chưa từng bị tác động bởi kẻ tấn công.
- Mã hoá và chứng thực các gói IP là biện pháp chính để ngăn chận các cuộc tấn công Man-in-the-midle.

**4.2. Messeage Replays**

- Trong một số giao thức xác thực, sau khi người dùng A chứng thực mình với hệ thống là một người dùng hợp pháp, A sẽ được cấp một chứng thực (giấy phép) thông qua. Với giấy phép này, A sẽ nhận được những dịch vụ cung cấp bởi hệ thống.
- Những kẻ tấn công có thể ngăn chặn gói tin chứa chứng thực đó, giữ một bản sao, và sử dụng nó sau này để mạo nhận (đóng vai) người dùng A.

**4.3. Network spoofing**
- **SYN flooding** là khi kẻ tấn công lấp đầy bộ đệm TCP của máy tính mục tiêu với một khối lượng lớn các gói SYN, làm cho máy tính mục tiêu không thể thiết lập các thông tin liên lạc với các máy tính khác.
- **TCP hijacking** là một kỹ thuật sử dụng các gói tin giả mạo để chiếm đoạt một kết nối giữa máy tính nạn nhân và máy đích. Để ngăn chặn kỹ thuật tấn công này, có thể sử dụng phần mềm như TCP Wrappers để kiểm tra địa chỉ IP tại tầng Transport.
- **ARP spoofing** hoặc ARP Poisoning diễn ra khi  kẻ tấn công thay đổi địa chỉ MAC đích hợp pháp của một địa chỉ IP đến một địa chỉ MAC khác được lựa chọn bởi những kẻ tấn công. Nói ngắn gọn, là thay đổi địa chỉ MAC đích thành địa chỉ mong muốn của kẻ tấn công. Để ngăn chặn các cuộc tấn công ARP spoofing, cần phải tăng cường kiểm tra các tên miền, và chắc chắn rằng địa chỉ nguồn và địa chỉ đích trong một gói tin không được thay đổi trong khi truyền.

#### 5. Buffer-Overflow Exploitations

- Buffer-Overflow là lỗi xảy ra khi quá trình ghi dữ liệu vào bộ đệm nhiều hơn kích thước khả dụng của nó.
- Các hàm `strcat()`, `strcpy()`, `sprintf()`, `vsprintf()`, `bcopy()`, `get()`, `scanf()`… trong ngôn ngữ C có thể bị khai thác bằng lỗi này vì không kiểm tra xem liệu bộ đệm có đủ lớn để dữ liệu được sao chép vào mà không gây ra tràn bộ đệm hay không.

#### 6. Repudiation

- Trong một số trường hợp chủ sở hữu của dữ liệu có thể không thừa nhận quyền sở hữu của dữ liệu để tránh hậu quả pháp lý. Người này có thể cho rằng chưa bao giờ gửi hoặc nhận các dữ liệu đó. Ngay cả khi dữ liệu đã được chứng thực, chủ sở hữu của dữ liệu xác thực có thể thuyết phục quan tòa rằng vì những sơ hở, bất cứ ai cũng có thể dễ dàng chế tạo tin nhắn và làm cho nó trông giống như thật.

> "Cháu nó ở nhà vô phá máy tính em, lỡ leak hết thông tin công ty cho bên đối thủ chứ em có biết gì đâu"

- Sử dụng các thuật toán mã hóa và xác thực có thể 
giúp ngăn ngừa các cuộc tấn công bác bỏ.

#### 7. Intrusion

- Tấn công xâm nhập bất hợp pháp vào một mạng với mục đích truy cập vào hệ thống máy tính của người khác, đánh cắp thông tin và tài nguyên máy tính hoặc băng thông của nạn nhân.
- Phòng chống bằng cách đóng các cổng UDP hoặc TCP không cần thiết, sử dụng IP scan và Port scan để kiểm tra các lỗ hỏng trong hệ thống.

#### 8. Denial of Service Attacks

- Tấn công từ chối dịch vụ nhằm ngăn chặn người dùng hợp pháp sử dụng những dịch vụ mà họ thường nhận được từ các máy chủ. Thường buộc máy tính mục tiêu phải xử lý một số lượng lớn những thứ vô dụng nhằm tiêu hao tài nguyên máy, dẫn đến không hoạt động được nữa. Nếu cuộc tấn công được phát sinh từ một nhóm các máy tính phân bố khắp nơi thì sẽ trở thành **DDoS - Distributed Denial of Serivce Attack**.

- DoS có các hình thức cơ bản sau:
    - Smurf
    - Buffer Overflow Attack
### C. Lý lịch của những kẻ tấn công

### D. Mô hình bảo mật cơ bản

## II. Malware

### A. Trojan

### B. Phòng chống Trojan

### C. Virus và các kỹ thuật của Virus

### D. Phòng chống Virus

## III. Các giải thuật mã hóa

### A. Giới thiệu về mã hóa

### B. Giải thuật mã hóa cổ điển

### C. Giải thuật mã hóa hiện đại

### D. Bẻ gãy một hệ thống mật mã

## IV. Mã hóa công khai và quản lý khóa

### A. Hệ mã hoá khoá công khai

### B. Giao thức trao đổi khoá Diffie-Hellman

### C. Hệ RSA

### D. Quản lý khoá

## V. Chứng thực dữ liệu

### A. Mã chứng thực thông điệp 

### B. Hàm băm

### C. Chữ ký số

## VI. Giao thức bảo mật mạng

### A. Vị trí của mật mã trong mạng máy tính
- **Các giao thức bảo mật mạng:**
    + Mã hóa khóa đối xứng
    + Mã hóa khóa công khai
    + Sinh khóa và trao đổi khóa
    + Hàm băm
    + Giải thuật chứng thực
    + Chữ ký số
    + Cơ sở hạ tầng khóa công khai
- **Các giao thức bảo mật mạng ứng dụng trong thực tế:**
    + Tầng mạng: Cơ sở hạ tầng khóa công khai (PKI) X.509, giao thức IP security (IPsec)
    + Tầng vận chuyển: Giao thức Secure Sockets Layer/Transport Layer Security (SSL/TLS)
    + Tầng ứng dụng: Pretty Good Privacy (PGP), Secure/Multipurpose Internet Mail Extension (S/MIME), Kerberos, Secure Shell (SSH)

| Các loại kết nối                                       | Riêng Tư/Mã hóa                                  | Chứng thực                                       | Ký/Toàn vẹn dữ liệu                              |
| :--------------------------------------------------- | :---------------------------------------------- | :----------------------------------------------- | :------------------------------------------------ |
| Nhân viên nội bộ hoặc từ xa truy cập đến server       | SSL 2.0 hoặc 3.0 (cung cấp bởi secure Server ID) | - Server chứng thực bởi Server ID <br>- Ký vào văn bản, S/MIME sử dụng Client ID| Client chứng thực bởi mật khẩu hoặc bởi SSL 3.0 với Client ID |
| Khách hàng truy cập đến server | SSL 2.0 hoặc 3.0 (cung cấp bởi secure Server ID)  |  Như trên  | Không cần thiết|
| Nhân viên từ xa sử dụng  e-mail | SSL trên POP3 hoặc IMAP mail server <br> -S/MIME Client ID hoặc VPN sử dụng Ipsec | Server chứng thực bởi mật khẩu của Server ID | S/MIME sử dụng Client ID |
| Truyền thông với chi nhánh |  -SSL<br>-VPN sử dụng IPsec | -Server chứng thực bởi Server ID<br> - Router/tường lửa chứng thực bởi Ipsec ID<br>- Client chứng thực bởi mật khẩu hoặc SLL 3.0 với Client ID |Ký vào văn bản, S/MIME|

#### Sự Tương Ứng giữa kiến trúc TCP/IP và mô hình OSI:
link1

#### Mô hình đóng gói và mã hóa dữ liệu tại các lớp mạng:
link 2

- **Mã hóa tại lớp ứng dụng:**
    + Bảo mật end-to-end
    + Dữ liệu được mã hóa sẽ tiếp tục đi qua các lớp khác như bình thường.
    + Khi đến TCP Header và IP Header sẽ không mã hóa (do việc mã hóa nằm ở các lớp dưới) -> vì thế attacker có thể phân tích và sửa chữa nội dung.
    + Ví dụ: có thể thay đồi IP đích trong IP header để phân phối gói tin đến nơi khác.

- **Mã hoá tại lớp vận chuyển(Transport Layer):**
    + Cung cấp sự an toàn cho gói TCP
    + Có thể mã hóa phần payload hoặc cả gói tin (header và payload)
    + không ảnh hưởng đến dữ liệu trước đó
    + Tuy nhiên IP header không được mã hóa -> attacker có thể thu được sequence number để tấn công.

- **Mã hoá tại lớp mạng (Network Layer):**
    + Bảo mật link-to-link
    + Mã hóa cả gói tin( payload + header)
    + Không ảnh hưởng định tuyến
    + Được xem như ứng dụng của tunnel - mode

- **Mã hoá tại lớp liên kết dữ liệu (Data-Link Layer):**
    + Cung cấp bảo mật cho các frames
    + mã hóa payload của frame
    + Việc mã hoá tại lớp liên kết dữ liệu( xem thêm bài 7)

- **Công nghệ vi mạch tích hợp ứng dụng(ASIC):**
    + Áp dụng các giải thuật lên ASIC:
    + Tầng ứng dụng: Thực hiện bởi phần mềm
    + Tầng Data-link: Thực hiện bởi phần cứng
    + Tại các tầng khác: một trong 2 hoặc cả 2
    + Mã hóa sử dụng phần cứng sẽ tiêu hao tài nguyên nhiều hơn nhưng hiệu suất sẽ tốt hơn so với phần mềm


### B. Cơ sở hạ tầng khoá công khai
- **Tổng quan:**
    + Sử dụng Mật mã khóa công khai là cách tốt nhất để triển khai các giải thuật mã hóa trong các ứng dụng mạng.
    + cần xây dựng hạ Tầng khoá công khai (Public-key infrastructure - PKI)
    + PKI cho phép người tham gia xác thực lẫn nhau và sử dụng khóa công khai để mã hóa và giải mã trong quá trình trao đổi

- **Các tính chất của PKI:**
    + Riêng tư
    + Toàn vẹn
    + Không thể phủ nhận
    + Dễ dàng sử dụng
    + Xác thực

- **Khái quát về PKI:**
    + PKI gồm phần mềm (client và server) và phần cứng(thẻ thông minh) và các quy trình hoạt động khác
    + Người dùng có thể sử dụng khóa bí mật để ký các văn bản điện tử và người khác có thể sử dụng khóa công khai để xác thực
    + Được hệ điều hành window hỗ trợ 

- **PKI thực hiện các chức năng sau:**
    + Xác định tính hợp pháp của người dùng
    + Phát hành chứng chỉ khóa công khai
    + Gia hạn thời gian chứng chỉ
    + Thu hồi khóa công khai
    + Lưu trữ và quản lí khóa công khai
    + Ngăn chặn người kí phủ nhận
    + Hỗ trợ các CA khác chứng thực chứng chỉ của khóa công khai được phát hành bởi CA này.

- **Danh sách một số hệ thống PKI:**
    + Computer Associates eTrust PKI                           
    + VeriSign
    + Entrust
    + OpenCA
    + Nexus
    + Microsoft

#### VeriSign
- **Tổng quan:**
    + Là thương hiệu uy tín nhất thế giới
    + Bảo mật hơn 1 triệu máy chủ web trên toàn world
    + Hơn 40 ngân hàng lớn , 90000 tên miền tại 145 Quốc gia sử dụng.

- **Giải thuật:**
    + Sử dụng giải thuật mã hóa SSL mạnh mẽ nhất:
        + Giải thuật mã hóa cao cấp từ 128bits trở lên
        + Có thể trao đổi dữ liệu giữa người dùng và website được mã hóa từ 40-256bits

- **Topology:**
Link3

#### X.509
- **Tổng quan:**
    + Thành lập bởi ITU năm 1988
    + được gọi tắt là PKIK, gồm 4 phần cơ bản:
        + End entity: là người dùng chứng chỉ hoặc thiết bị (server, router) có hỗ trợ PKIX
        + Certificate Authority (CA): tổ chức có trách nhiệm phát hành và thu hồi chứng chỉ.
        + Registration Authority (RA): có trách nhiệm xác minh danh tính của người chủ sở hữu chứng chỉ.
        + Repository: có trách nhiệm lưu trữ, quản lý chứng chỉ và danh sách các chứng chỉ bị thu hồi bởi CA

- **Kiến trúc**
Link 4

- **Các giao dịch giữa người dùng, RA, CA và kho:**
    + Đăng kí ( với CA hoặc RA)
    + Khởi tạo chứng chỉ (khóa công khai,chữ kí,...)
    + Chứng chỉ được phát hành 
    + phục hồi khóa
    + Tạo khóa
    + Thu hồi chứng chỉ
    + Chứng chỉ chéo

- **Bài tập nho nhỏ:**
Link 5
    + Hãy tìm đường đi từ A đến B và ngược lại
    + User A: X<< W >> W << V >> V << Y >> << Z >> Z << B >>
    + User B: Z << Y >> Y << V >> V << W >> W << X >> X << A >>


- **Các định dạng của chứng chỉ X.509**
    + version 1 phát hành năm 1988
    + version 2 không được sử dụng rộng rãi
    + version 3 phát hành năm 1996 ,phổ biến nhất và còn sử dụng cho đến nay

- **Các thành phần chứng chỉ X.509**
    + Version(phiên bản)
    + Serial number (số serial)
    + Algorithm (tên hàm băm + giải thuật mã hóa)      
    + Issuer ( tổ chức phát hành)
    + Validity period: thời gian hiệu lực
    + Subject ( tên chủ sở hữu)
    + Public key (khóa công khai)
    + Extension (cung cấp thêm các thông tin khác)
    + Properties: Giá trị hàm băm của chứng chỉ
### C. IPsec
Mục này khá dài nên mình sẽ tóm tắt các ý chính có khả năng ra thi

#### Tổng quan:
- Là giao thức bảo mật chính tại tầng Network (OSI) hoặc tầng Internet (TCP/IP).
- Là yếu tố quan trọng để xây mạng riêng ảo (VPN – Virtual Private Networks).
- Bao gồm giao thức chứng thực, giao thức mã hóa, giao thức trao đổi khóa:
    + **AH (Authentication Header):** được sử dụng để xác định nguồn gốc gói tin IP và đảm bảo tính toàn vẹn của nó.
    + **ESP (Encapsulating Security Payload):** dùng để chứng thực và mã hóa gói tin IP (phần payload hoặc cả gói tin).
    + **IKE (Internet Key Exchange):** dùng để thiết lập khóa bí mật cho người gửi và nhận.

- **Các phiên bản:**
    + phiên bản 1995: RFC 1825 - 1829
    + phiên bản 1998: RFC 2401 - 2412
    + phiên bản 2005: RFC 4301 - 4309

- **Ứng dụng của IPSec:**
    + Bảo mật kết nối giữa các chi nhánh văn phòng qua Internet.
    + Bảo mật truy cập từ xa qua Internet.
    + Thực hiện kết nối Internet và Extranet với các đối tác.
    + Nâng cao tính bảo mật trong thương mại điện tử.

- **Cung cấp dịch vụ bảo mật:**
    + Mã hóa quá trình truyền thông tin
    + Đảm bảo tính nguyên vẹn của dữ liệu
    + Phải được xác thực giữa các giao tiếp
    + Chống quá trình replay trong các phiên bản bảo mật
- Thuật toán được sử dụng trong IPsec bao gồm HMAC-SHA1 cho tính toàn vẹn dữ liệu (integrity protection), và thuật toán TripleDES-CBC và AES-CBC cho mã mã hóa và đảm bảo độ an toàn của gói tin. Toàn bộ thuật toán này được thể hiện trong RFC4305.

#### Các thông tin một SA cung cấp:
- Chỉ mục các thông số bảo mật: là một chuỗi nhị phân 32 bit được dùng để xác định 1 tập cụ thể của các giải thuật và thông số dùng trong truyền thông. SPI bao gồm AH và ESP để đảm bảo cả 2 đều dùng cùng giải thuật và thông số.
- Địa chỉ IP đích.
- Giao thức bảo mật: AH hay ESP. IPsec không cho phép AH hay ESP dùng đồng thời trong cùng 1 SA.

#### Các phương thức của IPSec:
- gồm 2 phương thức:
    + **Phương thức vận chuyển:** được dùng khi có yêu cầu lọc gói tin và bảo mật point-to-point. Cả hai trạm cần 2 trạm đều cần hỗ trợ Ipsec sử dụng cùng giao thức xác thực và không đi qua 1 NAT nào. Nếu dữ liệu đi qua NAT sẽ bị đổi IP trong phần header và làm mất hiệu lực của ICV (giá trị kiểm soát tính toàn vẹn).
    + **Phương thức đường hầm (Tunnel mode):** dùng mode này khi cần kết nối Site-to-Site thông qua internet hoặc mạng công cộng khác. Tunnel Mode cung cập sự bảo về Gate-to-Gate.

#### Định dạng AH:
- Authentication Header bao gồm các vùng :
    + **Next Header (8 bits):** xác định header kết tiếp.
    + **Payload Length (8 bits):** chiều dài Authentication Header từ 32 bit, trừ 2.
    + **Reserved (16 bits):** sử dụng cho tương lai
    + **Security Parameters Index (32 bits):** xác định 1 SA.
    + **Sequence Number (32 bits):** 1 giá trị tăng đơn điệu.
    + **Authentication Data (variable):** 1 vùng có chiều dài biến đổi (phải là 1 số nguyên từ 32 bits) chứa giá trị kiểm tra tính toàn ven với gói tin này.

- **Các phương thức chứng thực:**
    + End-to-End Authentication.
    + End-to-Intermediate Authentication.

#### Định dạng ESP
- Một gói ESP chứa các vùng:
    + **Security Parameters Index (32 bits):** xác định một SA
    + **Sequence Number (32 bits):** một giá trị đếm tăng đơn điệu, cung cấp chức năng anti-replay (giống AH).
    + **Payload Data (variable):** 1 segment ở tầng Transport hoặc gói IP (tunnel mode) được bảo vệ bởi việc mã hóa.
    + **Padding (255 bytes)**
    + **Pad Length (8 bits):** chỉ ra số byte vùng đứng ngay trước vùng này.
    + **Next Header (8 bits):** chỉ ra kiểu dữ liệu chứa trong vùng payload data bằng cách chỉ ra header đầu tiên của vùng payload này.
    + **Authentication Data (variable):** một vùng có chiều dài biến đổi (phải là một số nguyên từ 32 bits) chứa ICV được tính bằng cách gói ESP trừ vùng Authentication Data.

#### Các giải thuật mã hoá và chứng thực
- Three-key triple DES
- RC5
- IDEA
- Three-key triple IDEA
- CAST 
- Blowfish
### D. SSL/TLS
#### Tổng quan 
- Giao thức SSL (Secure Socket Layer Protocol) và giao thức TLS (Transport Layer Security Protocol) là giao thức bảo mật tại tầng Transport dùng chủ yếu trong thực tế.
- Được thiết kế và phát triển bởi Netscape, SSL dùng để bảo vệ ứng dụng WWW và các giao dịch điện tử.
- TLS là phiên bản sửa đổi của SSL v3
- Giao thức SSL bao gồm 2 phần:
    + Phần 1 gọi là record protocol, đặt trên đỉnh của các giao thức tầng Transport.
    + Phần 2 đặt giữa các giao thức tầng Application (như HTTP) và record protocol, bao gồm các giao thức:
        + Handshake protocol
        + Change-cipher-spec protocol
        + Alert protocol

#### Các giao thức của SSL:
- **Giao thức bắt tay** (handshake protocol) thành lập các giải thuật mã hóa, giải thuật nén, và các thông số sẽ được sử dụng bởi cả hai bên trong việc trao đổi dữ liệu được mã hóa. Sau đó, các giao thức bản ghi (record protocol) chịu trách nhiệm phân chia thông điệp vào các khối, nén mỗi khối, chứng thực chúng, mã hóa chúng, thêm header vào mỗi khối, và sau đó truyền đi các khối kết quả.
- **Các giao thức đổi mật mã** (change-cipher-spec protocol) cho phép các bên giao tiếp có thể thay đổi các giải thuật hoặc các thông số trong một phiên truyền thông.
- **Các giao thức cảnh báo** (alert protocol) là một giao thức quản lý, nó thông báo cho các bên tham gia truyền thông khi có vấn đề xảy ra.

#### Cấu trúc SSL
link17
link18

#### Giao thức bản ghi (record protocol) của SSL
link19

#### Tìm hiểu sâu về giao thức bắt tay
- **Phase 1:** chọn giải thuật mã hóa như RSA, AES-128, 3DES, RC6, SHA-1… client sẽ khởi tạo với 1 thông điệp hello.
- **Phase 2:** Server xác thực và trao đổi khóa. Server gửi cho Client:
    +	Chứng chỉ khóa công khai của server.
    +	Thông tin trao đổi khóa của server.
    +	Yêu cầu chứng chỉ khóa công khai của client.
- **Phase 3:** client xác thực và trao đổi khóa. Client trả lời Server các thông tin:
    +   Chứng chỉ khóa công khai của Client
    +	Thông tin trao đổi khóa của Client.
- **Phase 4:** hoàn thành bắt tay. Server và Client sẽ gửi nhau thông điệp finish.
### E. PGP và S/MIME
#### Tổng quan
- Có nhiều giao thức bảo mật cho tầng Application tập trung vào bảo mật Email và việc đăng nhập từ xa. Được dùng nhiều nhất:
    + PGP (Pretty Good Privacy).
    + S/MIME (Secure/Multipurpose Internet Mail Extension).
    + SSH (Secure Shell).
    + Kerberos (chứng thực cho mạng cục bộ).

- **Cơ chế bảo mật Email**
     + Cho E và D biểu thị 1 giải thuật mã hóa và giải mã khóa đối xứng. Cho E^ và D^  biểu thị một giải thuật mã hóa và giải mã khóa công khai
     + Giả sử Alice muốn chứng minh với Bob là email M mà Bob nhận được là từ Alice gởi, Alice có thể gởi chuỗi sau cho Bob:
     picture8

     + Với K<sup>u</sup><sub>A</sub> và K<sup>r</sup><sub>A</sub> lần lượt là khóa công khai và khóa riêng tư.
     
     + Sau khi nhận được M II S<sub>M</sub> II CA < K<sup>u</sup><sub>A</sub> > từ Alice, với S<sub>M</sub> là chữ Ký vào M sử dụng khóa riêng tư của Alice. Trước tiên Bob so sánh chữ ký của CA trên chứng chỉ khóa công khai CA ( K<sup>u</sup><sub>A</sub>) và rút trích K<sub>A</sub> từ đó. Sau đó Bob
     rút trích M và so sánh
     Link9

     + Nếu đúng, Bob tin là M đến từ Alice

     + Giả sử Alice muốn đảm bảo rằng M giữ được tính bí mật trong suốt quá trình truyền và cô ấy biết khoá công khai của Bob (K<sup>u</sup><sub>B</sub>), cô ấy sẽ gửi cho Bob chuỗi sau: 
     Link10

     + Với K<sub>A</sub> là khóa bí mật của Alice
     + Sau khi nhận được chuỗi từ Alice ,Bob sử dụng khóa riêng tư của mình để giải mã:
     Link 11
     + Kế đó Bob dùng (K<sub>A</sub>) để giải mã thu được M: 
     link 12
- **Các chức năng của  PGP:**
link13

    + **(sơ đồ a)** chỉ chứng thực
    + **(sơ đồ b)** chỉ Bảo mật
    + **(sơ đồ c)** Chứng thực và bảo mật

link14 

- **Một số Đặc tính của PGP**
link15

#### S/MIME
- Một chuẩn Internet về định dạng cho Email. Hầu như mọi Email trên Internet truyền qua giao thức SMTP theo dạng MIME.
- S/MIME đưa 2 phương pháp an ninh cho email: mã hóa và chứng thực. Cả 2 đều dựa trên mã hóa bất đối xứng và PKI

- **Sơ đồ Chứng thực chữ kí số:**
link16

- **Các tính năng của một Webmail client hộ trợ S/MIME:**

    + Tạo chữ ký số cho 1 email gửi đi để đảm bảo người nhận email tin không có sự can thiệp và đến từ người gửi.
    + Mã hóa email gửi đi để ngăn bất cứ ai xem, thay đổi… Nội dung của email trước khi đến với người nhận.
    + Xác minh chữ ký số của email đã ký đến với quá trình liên quan đến một danh sách thu hồi chứng chỉ (CRL).
    + Tự động giải mã một email gửi đến để người nhận có thể đọc được nội dung của email.
    + Trao đổi chữ ký hoặc email mã hóa với những người dùng khác của S/MIME


### F. Kerberos
link6

#### Tổng quan:
- Là một giao thức mã hoá dùng để xác thực trong các mạng máy tính hoạt động trên những đường truyền không an toàn.
- Có thể chống lại việc nghe lén hay gửi lại các thông tin cũ,đảm bảo tín toàn vẹn dữ liệu
- Mục tiêu nằm vào client-server và đảm bảo chứng thực 2 chiều.
- Xây dựng trên mã hóa đối xứng , cần 1 bên thứ 3 uy tín để làm chung gian.
- Được phát triển bởi MIT.
#### Mô tả cách hoạt động:
link7

- **Giải thích thuật ngữ:**
    + User: người dùng
    + Ticket granting service: phiên chứng chỉ
    + Authenticaion service: bên thứ 3 trung gian
    + Database : nơi lưu trữ user
    + Service server: Bên cung cấp chứng chỉ
### G. SSH
#### Tổng quan:
- Năm 1995 ,nhà nghiên cứu người Phần Lan Tatu Ylonen đưa ra giải thuật Secure Shell (SSH) để bảo vệ việc đăng nhập từ xa khỏi hacker lỏ
- Được định nghĩa trong RFC 4251
- Sử dụng cổng TCP 22
- Hoạt động trên các flatform khác nhau:
    + Kết nối đến một máy chủ SSH trên một router của Cisco từ một máy khách chạy Windows
    +  Kết nối đến một máy chủ Linux từ một router Cisco hay có thể kết nối đến một máy chủ Windows 2008 từ một máy khách sử dụng hệ điều hành Linux.
- Tạo kết nối bảo mật giữa 2 máy tính.
- Có khả năng nén, bảo mật dữ liệu khi truyền (SFTP) và sao chép file (SCP)
- Là giao thức ứng dụng client-server.SSH chia thành 3 lớp trong ứng dụng mô hình mạng TCP/IP:
    + Connection
    + User Authentication
    + Transport Layer
Link5

#### Cách thức hoạt động
- **Định danh Host:**
    + Thông qua trao đổi khóa,Mỗi máy tính có hỗ trợ kiểu truyền thông SSH có một khoá định danh duy nhất gồm khóa công khai và khóa riêng tư.Dữ liệu được mã hóa bằng khóa công khai và chỉ có khóa riêng tư mới giải mã được.
    + khi bắt đầu 1 phiên SSH, máy chủ sẽ gửi khóa công khai đến máy khách,máy khách sẽ sinh khóa ngẫu nhiên và mã hóa bằng khóa công khai và gửi về máy chủ ,Máy chủ sử dụng khóa riêng tư để giải mã và có được khóa của máy khách.Khóa này chính là khóa dùng để trao đổi dữ liệu giữa 2 bên.

- **Mã hóa:**
    + Sau khi định dạnh xong,dữ liệu trước khi trao đổi sẽ đưuọc mã hóa.
    + Việc lựa chọn cơ chế mã hóa do **máy khách quyết định**.Cơ chế thường bao gồm: 3DES, IDEA và Blowfish.

- **Chứng thực:**
    + Mỗi định danh và truy nhập của người sử dụng có thể được cung cấp theo nhiều cách khác nhau. Chẳng hạn, kiểu chứng thực rhosts có thể được sử dụng, nhưng không phải là mặc định; nó đơn giản chỉ kiểm tra định danh của máy khách được liệt kê trong file rhost (theo DNS và địa chỉ IP). 
    + Việc chứng thực mật khẩu là một cách rất thông dụng để định danh người sử dụng, nhưng ngoài ra cũng có các cách khác: chứng thực RSA, sử dụng ssh-keygen và ssh-agent để chứng thực các cặp khoá.



    

## VII. Bảo mật mạng không dây

### A. Tổng quan và phân loại

### B. Các kiểu chứng thực

### C. WEP, WPA và WPA2

### D. Các mối đe dọa

### E. Phương pháp và công cụ tấn công

### F. Tấn công mạng Bluetooth

### G. Biện pháp phòng chống

### H. Công cụ bảo mật Wi-Fi

### I. Kiểm thử hệ thống

## VIII. Bảo mật mạng ngoại vi

### A. Tổng quan
### B. Bộ lọc gói tin (Packet Filters)
### C. Cổng mạch (Circuit Gateways)
### D. Cổng ứng dụng (Application Gateways)
### E. Bastion Hosts
### E. Cấu hình tường lửa
### G. Chuyển dịch địa chỉ mạng (NAT)
### H. TMG – Threat Management Gateway
