command top
====================

Xin chào các bạn. Bài viết này tôi xin giới thiệu về câu lệnh top và ý nghĩa của nó trong việc monitor hệ thống. Giúp các bạn hiểu hơn về từng dòng hiện thị khi dùng lệnh `top`.


##### 1. Giới thiệu: 
Trong việc quản trị hệ thống Linux nhưng thông tin về RAM, CPU các tiến trình đang chạy rất cần thần thiết đối với một người quản trị và để giúp chúng ta có thể xem được những thông số đó người quản trị sẽ sử dụng dụng câu lệnh `top`.

##### 2. Ý nghĩa từng dòng trong bản hiện thị câu lệnh `top`

Bảng hiển thị câu lệnh top:

<img class="image__pic js-image-pic" src="http://i.imgur.com/3vGe3Mw.png" alt="" id="screenshot-image">

- Dòng 1: 

<img class="image__pic js-image-pic" src="http://i.imgur.com/ImnnmiS.png" alt="" id="screenshot-image">
  - Thời gian hiện tại
  - Thời gian uptime của máy
  - Số user đang đăng nhập
  - tải trung bình của hệ thống

- Dòng 2:

<img class="image__pic js-image-pic" src="http://i.imgur.com/SlBNAql.png" alt="" id="screenshot-image">
  - Tổng số tiến trình (94 total) 
  - Số tiến trình đang chạy (1 running)
  - Số tiến trình đang chờ (93 sleeping)
  - Số tiến trình đã dừng (0 stopped)
  - Số tiến trình đang chờ dừng (0 zombie)

- Dòng 3:

<img class="image__pic js-image-pic" src="http://i.imgur.com/UXByCkI.png" alt="" id="screenshot-image">
  - Phần trăm CPU sử dụng cho người dùng (0.0%us)
  - Phần trăm CPU sử dụng cho hệ thống (0.0%sy)
  - Phần trăm CPU sử dụng cho tiến trình update (0.0%ni)
  - Phần trăm CPU không sử dụng (%99.7id)
  - Phần trăm CPU đợi các tiến trình I/O của hệ thống (0.3wa%)
  - Phần trăm CPU sử dụng giao tiếp với phần cứng (0.0%hi)
  - Phần trăm CPU sử dụng giao tiếp với phần mềm (0.0%si)
  - 
  
- Dòng 4,5:

<img class="image__pic js-image-pic" src="http://i.imgur.com/feUKvPQ.png" alt="" id="screenshot-image">

Thể hiện mức sử dụng của RAM và swap

- Ý nghĩa các thông số trong bảng

<img class="image__pic js-image-pic" src="http://i.imgur.com/T2jMaau.png" alt="" id="screenshot-image">

  - PID: ID của tiến trình
  - USER: User sử dụng tiến trình đó
  - PR: Mức đăng quyền của tiến trình
  - NI: Giá trị tốt của tiến trình
  - VIRT: Bộ nhớ ảo dùng cho tiến trình
  - RES: Bộ nhớ vật lý dùng cho tiến trình
  - SHR: 
  - S:
  - %CPU: Phần trăm CPU sử dụng cho tiến trình
  - %MEM: Phần trăm bộ nhớ sử dụng cho tiến trình
  - TIME: Tổng thời gian hoạt động của tiến trình
  - COMMAND: Tên của tiến trình
  
##### 3. Các tùy chọn hay dùng trong câu lệnh `top1`

*Tôi sẽ bổ sung phần này trong thời gian tiếp theo*

**Link tham khảo:**

[Link1:](http://linux.about.com/od/commands/l/blcmdl1_top.htm)

[Link2:](http://www.tecmint.com/12-top-command-examples-in-linux/)

Liên hệ:
skype: namptit307
