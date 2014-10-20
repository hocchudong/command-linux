Lệnh CD 
============================
===

### 1.	Chuyển đến thư mục /usr/local
```
root@controller:~#cd /usr/local
root@controller:/usr/local#
```
### 2.	Chuyển từ thư mục hiện tại tới thư mục sử dụng đường dẫn tuyệt đối
```
root@controller:/usr/local# cd /usr/local/lib
root@controller:/usr/local/lib#
```
### 3.	Chuyển từ thư mục hiện tại tới thư mục sử dụng đường dẫn tương đối
```
root@controller:/usr/local# cd lib
root@controller:/usr/local/lib#
```
### 4.	Chuyển trở lại thư mục từ thư mục bạn đang ở
```
root@controller:/usr/local/lib# cd /usr/local/
root@controller:/usr/local#
```
### 5.	Quay trở lại thư mục cha
```
root@controller:/usr/local/lib# cd ..
root@controller:/usr/local#
```
### 6.	Hiển thị thư mục làm việc cuối cùng
```
root@controller:/usr/local# cd --
root@controller:~#
```
### 7.	Di chuyển 2 thư mục từ thư mục bạn đang ở
```
root@controller:/usr/local# cd ../ ../
root@controller:/usr#
```
### 8.	Di chuyển đến thư mục root
```
root@controller:/usr# cd
root@controller:~#
hoặc root@controller:/user#cd~
```
### 9.	Thay đổi thư mục làm việc vào thư  mục hiện tại
```
root@controller:/usr/local# cd .
root@controller:/usr/local#
```
### 10.	Chuyển vào thư mục /var/www/html với <tab>
```
root@controller:/v<tab>/w<tab>/h<tab>
```
### 11.	Chuyển vào thư mục có chứa khoảng trắng
```
root@controller:/usr# cd test\ abc/; hoặc
root@controller:/urs#cd 'test abc'; hoặc
root@controller:/usr#cd "test abc"/
```
