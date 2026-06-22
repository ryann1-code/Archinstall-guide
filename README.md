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
