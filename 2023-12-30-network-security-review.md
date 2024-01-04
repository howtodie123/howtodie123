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
#### Vai trò:
- Chứng thực (authentication) nhằm: 
  + Xác nhận nguồn gốc dữ liệu 
  + Thuyết phục người dùng là dữ liệu này chưa bị sửa đổi hay giả mạo
- Chứng thực là cơ chế quan trọng để duy trì tính toàn vẹn và không thể từ chối của dữ liệu.
#### Các phương pháp:
-	Mã hóa thông điệp: sử dụng khóa bí mật và khóa công khai để mã hóa thông điệp
-	Mã chứng thực thông điệp (MAC – Message Authen Code): một hàm và một khóa bí mật tạo ra 1 giá trị có chiều dài cố định sử dụng để chứng thực
-	Hàm băm (Hash function): Ánh xạ một thông điệp vào một giá trị băm có chiều dài cố định để chứng thực.
#### Chứng thực thông qua nhận dạng:
- Sử dụng các yếu tố nhận dạng như Password,PIN ,Smart card,Biometric: Vân tay, võng mạc,Chữ kí,...
#### Ví dụ về chứng thực:
- Giả sử Alice và Bob chia sẻ một khoá bí mật chung **K**. Alice muốn gởi một chuỗi dữ liệu **M** cho Bob và thuyết phục Bob rằng **M** thực sự đến từ Alice và không bị sửa trong quá trình truyền. Điều này có thể thực hiện như sau:
- Alice gởi **M** cùng với **C** cho Bob, với **C=EK(M) và E** là một giải thuật mã hoá thông thường đã quy ước trước giữa Alice và Bob.
- Do chỉ có Alice và Bob biết **K**, Bob có thể sử dụng **K** để giải mã **C** thu được **M’**. 
- Bob sẽ được thuyết phục rằng **M** thực sự đến từ Alice và **M** không bị thay đổi trong quá trình truyền nếu và chỉ nếu **M’=M**.
- Tuy nhiên, phương pháp này cho phép Alice có thể từ chối Charlie rằng **M** xuất phát từ Alice vì **M** có khả năng xuất phát từ Bob do cùng chia sẻ khoá bí mật **K**. 
 → Nhược điểm này được giải quyết bằng mật mã hoá khoá công khai.
- Nếu chuỗi **M** ngắn, có thể mã hóa **M** trực tiếp để xác nhận nó. 
- Nếu chuỗi **M** dài, chỉ cần tính toán một h ngắn đại diện cho **M** và mã hóa **h**.
#### Vậy h được tạo ra như thế nào?
- **h** được tạo ra mà không sử dụng khoá bí mật được gọi là digital digest hoặc digital fingerprint (dấu vân tay kỹ thuật số), có thể thu được từ một hàm băm (Hash Function).
- **h** được tạo ra bằng cách sử dụng một khoá bí mật được gọi là một mã xác thực thông điệp (MAC – Message Authentication Code).
- **h** cũng có thể thu được bằng cách sử dụng giải thuật checksum kết hợp một hàm băm để tạo ra một mã xác thực tin nhắn keyed-hash (HMAC - Keyed-Hash Message Authentication Code)
#### Điều khiển lỗi khi gởi thông điệp: 
- a) Kiểm soát lỗi nội bộ
- b) Kiểm soát lỗi bên ngoài
- Giải thích kí hiệu:
  + M : Message, là thông điệp
  + E : Encrypt, là hàm mã hóa
  + D : Decrypt, là hàm giải mã
  + K : Khóa 
  + F(M) : là hàm băm của dữ liệu M đầu vào 
  + || : Phép nối, dùng để nối 2 chuỗi kí tự, chuỗi bên dưới dùng để kiểm tra sau khi bên kia giải mã M

#### Các công dụng cơ bản của mã hóa:
- Giải thích kí hiệu
   + PU : public key , khóa công khai
   + PR : Private key, khóa bí mật
   + A : bên gửi
   + B : bên nhận
   + Các kí hiệu còn lại(xem lại ở trên)
- a) Mã hoá khoá đối xứng (khoá bí mật):
   + Bảo mật: chỉ A và B chia sẻ K
   + Chứng Thực:
      + Có thể đến chỉ từ A
      + Không thay đổi trong quá trình truyền
      + Yêu cầu một số định dạng và dự phòng
   + Không cung cấp chữ ký:
      + Người nhận có thể giả mạo thông điệp
      + Người gửi có thể phủ nhận thông điệp
- b) Mã hoá khoá bất đối xứng (khoá công khai)
   + A → B: E(PU<sub>b</sub>, M)
   + Bảo mật:
      + Chỉ B có PR<sub>b</sub> giải mã
   + Không cung cấp chứng thực
      + Bất cứ ai cũng có thể sử dụng PU<sub>b</sub> để mã hoá thông điệp và tự xưng là A.
- c) Mã hóa khóa công khai: chứng thực và chữ ký số:
   + A → B: E(PR<sub>a</sub>, M)
   + Cung cấp chứng thực và chữ ký số
      + Chỉ A có PRb để mã hoá
      + Không bị thay đổi trong quá trình truyền
      + Yêu cầu một số định dạng và dự phòng
      + Bất kỳ ai cũng có thể sử dụng PUa để xác minh chữ ký số
- d. Mã hoá khoá công khai: bảo mật, chứng thực, và chữ ký số
   +  A → B: E(PUb, E(PRa, M))
   +  Cung cấp bảo mật nhờ PUb.
   +  Cung cấp chứng thực và chữ ký số nhờ PRa.
### A. Mã chứng thực thông điệp

### B. Hàm băm

### C. Chữ ký số

## VI. Giao thức bảo mật mạng

### A. Vị trí của mật mã trong mạng máy tính

### B. Cơ sở hạ tầng khoá công khai

### C. IPsec

### D. SSL/TLS

### E. PGP và S/MIME

### F. Kerberos

### G. SSH

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
