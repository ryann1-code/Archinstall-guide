# Archinstall-guide (  )

**Kết nối mạng**
* **Nếu dùng mạng dây (LAN):** Hệ thống sẽ tự kết nối. Kiểm tra bằng lệnh:
    ```bash
    ping -c 3 google.com
    ```
* **Nếu dùng Wi-Fi:** Gõ lệnh dưới đây để mở công cụ quản lý Wi-Fi:
    ```bash
    iwctl
    ```
    Sau đó thực hiện các lệnh sau:
    ```bash
    device list (để xem tên ổ mạng, ví dụ: wlan0)
    station wlan0 scan
    station wlan0 get-networks
    station wlan0 connect <Tên_Wifi_Của_Bạn>
**Cập nhật**
  ```bash
    pacman -Sy
  ```
**Cài đặt các gói cần thiết**
```bash
pacman -S archlinux-keyring
pacman -S archinstall
```
**Chọn nơi phân vùng, tạo efi (dual boot) và mount**
```bash
lsblk (Liệt kê thông tin chi tiết các ổ lưu trữ):
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
nvme0n1     259:0    0 476.9G  0 disk 
├─nvme0n1p1 259:1    0 475.3G  0 part 
└─nvme0n1p2 259:2    0   1.6G  0 part
```

