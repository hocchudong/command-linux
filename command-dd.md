command-dd-in-linux
===================
===================

Mục lục:
- [Mục lục](#user-content-dd_command_in_linux)
			
- [1. Mở đầu và khuyến nghị](#user-content-1-m%E1%BB%9F-%C4%91%E1%BA%A7u-v%C3%A0-khuy%E1%BA%BFn-ngh%E1%BB%8B)
			
- [2. Khái niệm và ứng dụng của câu lệnh](#user-content-2-kh%C3%A1i-ni%E1%BB%87m-v%C3%A0-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-c%C3%A2u-l%E1%BB%87nh)
			
- [3. Cú pháp và các trường tùy chọn](#user-content-3-c%C3%BA-ph%C3%A1p-v%C3%A0-c%C3%A1c-tr%C6%B0%E1%BB%9Dng-t%C3%B9y-ch%E1%BB%8Dn)
					
    - [a. Cú pháp](#user-content-a-c%C3%BA-ph%C3%A1p)
					
    - [b. Các tùy chọn](#user-content-b-c%C3%A1c-t%C3%B9y-ch%E1%BB%8Dn)
			
- [4. Các ví dụ trong hay được sử dụng trong thực tế:](#user-content-4-c%C3%A1c-v%C3%AD-d%E1%BB%A5-trong-hay-%C4%91%C6%B0%E1%BB%A3c-s%E1%BB%AD-d%E1%BB%A5ng-trong-th%E1%BB%B1c-t%E1%BA%BF)
					
    - [a. Sao lưu - phục hồi toàn bộ ổ cứng hoặc phân vùng trong ổ cứng](#user-content-a-sao-l%C6%B0u---ph%E1%BB%A5c-h%E1%BB%93i-to%C3%A0n-b%E1%BB%99-%E1%BB%95-c%E1%BB%A9ng-ho%E1%BA%B7c-ph%C3%A2n-v%C3%B9ng-trong-%E1%BB%95-c%E1%BB%A9ng)
					
    - [b.Sao lưu phục hồi MBR](#user-content-bsao-l%C6%B0u-ph%E1%BB%A5c-h%E1%BB%93i-mbr)
					
    - [c. Chuyển đổi chữ thường thành chữ in hoa](#user-content-c-chuy%E1%BB%83n-%C4%91%E1%BB%95i-ch%E1%BB%AF-th%C6%B0%E1%BB%9Dng-th%C3%A0nh-ch%E1%BB%AF-in-hoa)
					
    - [d. Tạo một file có dung lượng cố định](#user-content-d-t%E1%BA%A1o-m%E1%BB%99t-file-c%C3%B3-dung-l%C6%B0%E1%BB%A3ng-c%E1%BB%91-%C4%91%E1%BB%8Bnh)
			
- [5. Các tình huống áp dụng trong thực tế](#user-content-5-c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-%C3%A1p-d%E1%BB%A5ng-trong-th%E1%BB%B1c-t%E1%BA%BF)
			
- [6. Kết luận](#user-content-6-k%E1%BA%BFt-lu%E1%BA%ADn)

#### 1. Mở đầu và khuyến nghị

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các thuật ngũ liên quan đến ổ cứng, và kiến thức về MBR...

#### 2. Khái niệm và ứng dụng của câu lệnh
Câu lệnh `dd` trong linux là một trong những câu lệnh thường xuyên được sử dụng. Câu lệnh `dd` dùng để sử dụng trong các trường hợp sau:

- Sao lưu và phục hồi toàn bộ dữ liệu ổ cứng hoặc một partition 
- Chuyển đổi định dạng dữ liệu từ ASCII sang EBCDIC hoặc ngược lại
- Sao lưu lại MBR trong máy (MBR là một file dữ liệu rất quan trong nó chứa các lệnh để LILO hoặc GRUB nạp hệ điều hanh)
- Chuyển đổi chữ thường sang chữ hoa và ngược lại
- Tạo một file với kích cơ cô định
- Tạo một file ISO 

#### 3. Cú pháp và các trường tùy chọn
###### a. Cú pháp
```
#dd if=<địa chỉ đầu vào> of=<địa chỉ đầu ra> option
```
Trong đó:
- if=<soure> địa chỉ nguồn của dữ liệu nó sẽ bắt đầu đọc
- of=<targer> viết đầu ra của file
- option : các tùy chọn cho câu lệnh

###### b. Các tùy chọn
|Tùy chọn | Ý nghĩa |
|---------|---------|
|bs=Bytes |Quá trình đọc (ghi) bao nhiêu byte một lần đọc (ghi) |
|cbs=Bytes|Chuyển đổi bao nhiêu byte một lần |
|count=Blocks | thực hiện bao nhiêu Block trong quá trình thực thi câu lệnh |
|if | Chỉ đường dẫn đọc đầu vào |
|of | Chỉ đường dẫn ghi đầu ra|
|ibs=bytes | Chỉ ra số byte một lần đọc |
|obs=bytes | Chỉ ra số byte một lần ghi |
|skip=blocks | Bỏ qua bao nhiêu block đầu vào |
|conv=Convs | Chỉ ra tác vụ cụ thể của câu lệnh, các tùy chọn được ghi dưới bảng sau đây |

**Các tùy chọn của conv**

|Tùy chọn | Tác dụng  |
|-----------|----------|
|ascii | Chuyển đôi từ mã EBCDIC sáng ASCII |
|ebcdic | Chuyển đổi từ mã ASCII sang EBCDIC |
|lcase | Chuyển đổi từ chữ thường lên hết thành chữ in hoa |
|ucase | Chuyển đổi từ chữ in hoa sang chữ thường |
|nocreat | Không tạo ra file đầu ra |
|noerror | Tiếp tục sao chép dữ liệu khi đầu vào bị lỗi |
|sync | Đồng bộ dữ liệu với ổ đang sao chép sang |


*Lưu ý:* Khi bạn định dạng số lượng byte mỗi lần đọc. Mặc định nó được tính theo đơn vị là kb. Bạn có thể thêm một số trường sau để báo định dạng khác:

- c = 1 byte
- w = 2 byte
- b = 512 byte
- kB = 1000 byte 
- K = 1024 byte 
- MB = 1000000 byte
- M = (1024 * 1024) byte
- GB = (1000 * 1000 * 1000) byte
- G = (1024 * 1024 * 1024) byte

#### 4. Các ví dụ trong hay được sử dụng trong thực tế:
###### a. Sao lưu - phục hồi toàn bộ ổ cứng hoặc phân vùng trong ổ cứng
- Sao lưu toàn bộ dữ liệu ổ cứng sao ổ cứng khác:
```
#dd if=/dev/sda of=/dev/sdb conv=noerror,sync
```
Câu lệnh này dùng dể sao lưu toàn bộ dữ liệu của ổ sda sang ổ sdb với tùy chọn trong trường conv=noerrom.sync với ý ngĩa vẫn tiếp tục sao lưu nếu dữ liệu đầu vào bị lỗi và tự động đồng bộ với dữ liệu sdb

- Tạo một file image cho ổ sda1. Các này sẽ nhanh hơn là viêc chuyển dữ liệu sao ổ khác
```
dd if=/dev/sda1 of=/root/sda1.img 
```
- Nếu muốn nén ảnh file anh vào bạn có thể sử dụng command sau
```
dd if=/dev/sda1 | grip > /root/sda1.img.gz
```
-Sao lưu dữ liệu từ một phân vùng này đến một phân vùng khác
```
dd if=/dev/sda2 of=/dev/sdb2 bs=512 conv=noerror,sync
```
*Đối với câu lệnh này bs=512 có ý nghĩa mỗi lần đọc ghi nó đọc và ghi 512 byte*
- Phục hồi dữ liệu 
```
dd if=/root/sda1.img of=/dev/sda1
```
- Sao lưu từ đĩa CDroom
```
dd if=/dev/cdrom of=/root/cdrom.img conv=noerror
```

###### b.Sao lưu phục hồi MBR
Việc sao lưu lại mbr là việc làm cần thiết đối với hệ thống linux. nó đề phòng cho việc khi virut có thể nhảy được hẳn vào vùng MBR. Lúc bày bất kì một phần mềm diệt virut nào cũng không diệt được con virut này. Cách hay nhất là cài đặt lại mbr và lúc đó việc sao chép MBR lúc trước khi nhiễm sẽ phát huy tác dụng:
- Sao chép MBR
```
dd if=/dev/sda1 of=/root/mbr.txt bs=512 count=1
```
- Phục hồi lại MBR
```
dd if=/root/mbr.txt of=/dev/sda1
```
###### c. Chuyển đổi chữ thường thành chữ in hoa
- Chuyển chữ thường thành chữ in hoa
```
dd if=/root/test.doc of=/root/test1.doc conv=ucase
```
<img class="image__pic js-image-pic" src="http://i.imgur.com/ihXZb4z.png" alt="" id="screenshot-image">

- Chuyển chứ hoa thành chứ thường
```
dd if=/root/test1.doc of=/test2.doc conv=scase,sycn
```
###### d. Tạo một file có dung lượng cố định 
Tạo ra một file có kích thước 100M
```
dd if=/dev/zero of=/root/file1 bs=100M count=1
```

#### 5. Các tình huống áp dụng trong thực tế

Các ví dụ tôi vừa nêu trên đều sử dụng rất nhiều trong thực tế. Ngoài ra còn kết hợp với một số câu lệnh để làm thêm tác vụ khác như:

- VD1: Kết hợp với câu lệnh mkswap để tạo phân vùng swap cho máy 
    - Sử dụng câu lênh dd để tạo một phân vùng trống có kích cỡ 1G:
```
dd if=/dev/zero of=/root/swap bs=1024M count=1
```

<img class="image__pic js-image-pic" src="http://i.imgur.com/ULIQkPh.png" alt="" id="screenshot-image">

  - Gán quyền cho nó chỉ root mới vào xem được
```
chmod 600 /root/swap
```
<img class="image__pic js-image-pic" src="http://i.imgur.com/nllxHrl.png" alt="" id="screenshot-image">

- Chỉ cho đến vùng swap
```
mkswap /root/swap
```
```
swapon /root/swap 
```
<img class="image__pic js-image-pic" src="http://i.imgur.com/f6taOEY.png" alt="" id="screenshot-image">

Oki nào bây giờ kiểm tra lại xem thành công chưa. Sử dụng lệnh
```
swapon -s
```
<img class="image__pic js-image-pic" src="http://i.imgur.com/Rw4Zg2o.png" alt="" id="screenshot-image">
 
 Lúc này tổng dung lượng phân vùng swap sẽ là 2G ( do trước đó tôi cài đặt cho phân vùng swap là 1G trước rồi )
 
 <img class="image__pic js-image-pic" src="http://i.imgur.com/Wb2mdPV.png" alt="" id="screenshot-image">
 
 Nếu bạn muốn tạo vùng swap không bị mất khi reboot lại máy. Bạn vào file này rồi chỉnh sửa như sau:
 ```
 vi /etc/fstab
 rồi chỉnh sửa:
 /root/swap                 swap                    swap                defaults        0  0
 ```
 
 VD2: Ngoài ra bạn còn có thể kết hợp với câu lênh crontab để có thể lâp lịch sao chép dữ liêu ổ cứng của bạn theo định kì
Đầu tiên vào một file sh để chạy
```
vi dd_command.sh
với nội dung là:
dd if=/dev/sda1 of=/dev/sdb1 conv=noerror,sync
```
Tạo một crotab cho file chạy

```
crontab 0 10 * * * sh dd_command.sh
```
Lúc này đến 10h hàng ngày quá trình sao chép dữ liệu giữa ổ sda1 sang ổ sdb1 được thực hiện

#### 6. Kết luận

Bài viết trên đây tôi đã giới thiệu cho các bạn về câu lệnh dd một câu lệnh thường xuyên được sử dụng trong quản trị hệ thống Linux. Ngoài những tùy chọn tổi liệt kê là những tùy chọn thường xuyên được sử dụng trong thực tế thì vẫn còn một số tùy chọn khác thêm nữa. [Các bạn có thể xem đây đủ tại đây](http://www.computerhope.com/unix/dd.htm). 
Mọi thông tin liên hệ các bạn có thể liên hệ với tôi qua skype: **namptit307** hoặc vào [facebook](https://www.facebook.com/nam.nguyenhoai.71404) để chúng ta có thể thao luận thêm về câu lệnh này cũng như các tùy chọn của nó. Cảm ơn các bạn đã đọc bài viết của tôi!!! 
Tài liệu tham khảo:

[Link 1](http://www.computerhope.com/unix/dd.htm)

[Link 2](http://linoxide.com/linux-command/linux-dd-command-create-1gb-file/)

[Link 3](http://www.thegeekstuff.com/2010/10/dd-command-examples/)

[Link wiki](http://en.wikipedia.org/wiki/Dd_(Unix))


