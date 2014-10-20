Command_dmesg
###Lệnh dmesg hiển thị các messeage từ vòng đệm kernel. Hiển thị các thiết bị nhận biết được bởi kernel
==========
###1.	Lệnh list tất cả loaded drivers trong kernel

`````
dmesg
Có thế sử dụng thêm các tool thao tác văn bản: “more”, “less”, “tail”, “grep”
dmesg | more
dmesg | less
`````
###2.	Lệnh list tất cả deteced divices

`````
Để phát hiện các ổ đĩa cứng đã được phát hiện bởi hạt nhân, bạn có thể tìm kiếm từ khóa "sda" cùng với "grep":
dmesg | grep sda
`````
###3.	Chỉ in ra 20 dòng đầu tiên

`````
dmesg | head -20
`````
###4.	Chỉ in ra 20 dòng cuối

`````
dmesg | tail -20
`````
###5.	Tìm phát hiện device và chuỗi đặc biệt

`````
dmesg | grep –i usb
dmesg | grep –i dma
dmesg | grep –i tty
dmesg | grep –i memory
`````
###6.	Xóa log của dmesg

`````
dmesg –c
`````
###7.	Giám sát dmesg theo thời gian thực

`````
watch “dmesg | tail -20”
`````
####Link tham khảo 
```
http://www.tecmint.com/dmesg-commands/
```
