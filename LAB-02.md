# Cấu hình VLANs, Trunking và VLANs routing

## 1.	Mô hình bài lab: 
4 Switch trong đó switch L3-SW-1 và L3-SW-2 được kết nối với nhau và sử dụng etherchannel port. L3-SW1 đóng vai trò là VTP server, các switch còn lại đóng vai trò VTP client. VLANs sẽ được tạo trên Switch L3-SW1 (vtp server) sau đó sẽ update xuống các switch còn lại (vtp client).,

[Mô hình]
![image](https://user-images.githubusercontent.com/38779855/225658123-30e95c8c-e547-4c81-884c-e1a4bde3aa0c.png)

## 2.	Triển khai cấu hình (IP theo hình) :

Kéo thả các thiết bị cần thiết vào :  4 VPCS, 2 L2-SW, 2 L3-SW, 1 Router
-	L3-SW1 đóng vai trò là VTP Client , Vlans sẽ được tạo trên nó rồi update xuống các switch còn lại
-	Tiến hành nối dây các thiết bị với nhau theo sơ đồ 
-	Cấu hình VTP cho Switch:

## 3. Kiểm tra kết quả từ PC1 ping giữa VLAN 10 và VLAN 20 thành công -> Pass

```
PC1> ping 192.168.10.1
84 bytes from 192.168.10.1 icmp_seq=1 ttl=255 time=34.002 ms
84 bytes from 192.168.10.1 icmp_seq=2 ttl=255 time=53.003 ms
84 bytes from 192.168.10.1 icmp_seq=3 ttl=255 time=18.001 ms
84 bytes from 192.168.10.1 icmp_seq=4 ttl=255 time=9.001 ms
```
```
PC1> ping 192.168.10.20
84 bytes from 192.168.10.20 icmp_seq=1 ttl=64 time=90.005 ms
84 bytes from 192.168.10.20 icmp_seq=2 ttl=64 time=59.003 ms
84 bytes from 192.168.10.20 icmp_seq=3 ttl=64 time=91.005 ms
84 bytes from 192.168.10.20 icmp_seq=4 ttl=64 time=84.005 ms
```
```
PC1> ping 192.168.20.1
84 bytes from 192.168.20.1 icmp_seq=1 ttl=255 time=23.001 ms
84 bytes from 192.168.20.1 icmp_seq=2 ttl=255 time=23.001 ms
84 bytes from 192.168.20.1 icmp_seq=3 ttl=255 time=96.006 ms
84 bytes from 192.168.20.1 icmp_seq=4 ttl=255 time=40.002 ms
```
```
PC1> ping 192.168.20.20
84 bytes from 192.168.20.20 icmp_seq=2 ttl=63 time=101.005 ms
84 bytes from 192.168.20.20 icmp_seq=3 ttl=63 time=107.006 ms
84 bytes from 192.168.20.20 icmp_seq=4 ttl=63 time=146.008 ms
84 bytes from 192.168.20.20 icmp_seq=5 ttl=63 time=112.006 ms
```


