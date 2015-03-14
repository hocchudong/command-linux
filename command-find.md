
### Command find
Command `find` là câu lệnh dùng để tìm kiếm file và thư mục theo những yêu cầu cho trước
### Tìm file 

##### Tìm file có tên tecmint.txt ở thư mục hiện tại
```
find -name "tecmint.txt"
```
##### Tìm file có tên hoainam.conf theo đường dẫn
```
find /etc/tmp/ -name "hoainam.conf" 
```
- Lúc này câu lệnh sẽ tìm file đường dẫn /etc/tmp/
- Thay tùy chọn -name bằng -iname : Lúc đó câu lệnh sẽ tìm tất cả các file hoainam.conf kể cả từ viết hoa và viết thường

##### Tìm file khi chỉ nhớ từ gợi mở
```
find -name "a*"
Lúc này câu lệnh sẽ tìm tất cả các file có tên đầu là a 
```
```
find -name "*a*"
Tìm tất cả các file có tên ở giữa là a
```

### Tìm thư mục

##### Tìm thư mục có tên **hoainam**
```
find -type d -name "hoainam"
```
```
find /etc/tmp -type d -name "hoainam"
Tìm thư mục hoài nam tại đường dẫn /etc/tmp
```
##### Tìm thư mục có tên gợi mở
```
find /etc/tmp -type d -name "h*" 
Câu lệnh tìm tất cả các thư mục có tên đầu là h
```

### Tìm file hoặc thư mục theo Permissions 
Khi muốn tìm thư mục hoặc file theo Permissions hoặc muốn kết hợp với Permissions ta thêm tùy chọn `-perm <mức permissions>`
VD: khi muốn tìm file & thư mục có mức Permissions là 777 thì thêm tùy chọn `-perm 777`
```
find -perm 777 -name hoainam.txt
```

### Tìm file & thư mục trống

##### Tìm thư mục trống 
```
find -type d -entry
```
##### Tìm file trống
```
find -type f -entry
```
### Tìm theo tên người sử hữu 

Thêm tùy chọn `user <tên người sở hữu>`
```
find / -name "hoainam.txt" -user root
Tìm tất cả file hoainam.txt thuộc người dùng root trong hệ thống
```
### Tìm file theo dung lượng
Thêm tùy chọn `-size <kích thước file>`

VD: muốn tìm file có dung lượng 10M thêm tùy chọn `-size 10MB`

========

### Tài liệu tham khảo
http://www.tecmint.com/35-practical-examples-of-linux-find-command/

