# Archinstall-guide (  )
# 🚀 Arch Linux Installation Guide (Dành cho Newbies bằng `archinstall`)

Chào mừng bạn đến với hướng dẫn cài đặt Arch Linux! Hướng dẫn này được thiết kế dành riêng cho những người mới bắt đầu (newbies), sử dụng **`archinstall`** — một script cài đặt tự động chính thức có sẵn trong file ISO của Arch Linux. Bạn sẽ có một hệ thống Arch hoàn chỉnh, mượt mà mà **không cần phải gõ từng lệnh phân rã thủ công hay ngồi chờ compile (biên dịch) phức tạp.**

---

## 📋 Chuẩn bị trước khi cài đặt

### 1. Tải bộ cài đặt (ISO) chính thức
Để đảm bảo an toàn và cập nhật nhất, bạn luôn luôn phải tải file ISO từ trang chủ của Arch Linux.

* **Bước 1:** Truy cập vào trang [Arch Linux Download](https://archlinux.org/download/).
* **Bước 2:** Cuộn xuống phần **HTTP Direct Downloads**, chọn một Mirror (máy chủ) gần Việt Nam nhất (ví dụ: *Worldwide* hoặc các nước Châu Á như *Singapore, Japan*).
* **Bước 3:** Tải file có đuôi `.iso` (Ví dụ: `archlinux-XXXX.XX.XX-x86_64.iso`).

### 2. Tạo USB Boot
Bạn cần một chiếc USB trống (dung lượng tối thiểu 4GB).
* **Trên Windows:** Tải phần mềm [Rufus](https://rufus.ie/), chọn USB, chọn file ISO vừa tải và nhấn **Start** (Khuyên dùng chế độ *ISO Image mode*).
* **Trên Linux/macOS:** Bạn có thể dùng phần mềm giao diện như **BalenaEtcher** hoặc dùng lệnh `dd` trong Terminal.

### 3. Kiểm tra thiết bị
* Máy tính của bạn phải được cắm **dây mạng (Ethernet)** hoặc ở vị trí có **Wi-Fi ổn định**.
* Định dạng ổ cứng khuyến khích là **UEFI** (Hầu hết các máy tính từ 2015 đến nay đều hỗ trợ). Hãy vào BIOS để tắt **Secure Boot**.

---

## 🛠️ Quy trình cài đặt chi tiết

### Bước 1: Khởi động vào USB Installer
1. Cắm USB vào máy, khởi động lại và nhấn phím tắt để vào **Boot Menu** (F12, F11, F8 hoặc F2 tùy dòng máy).
2. Chọn boot vào USB dưới chế độ **UEFI**.
3. Màn hình GRUB của Arch Linux xuất hiện, chọn dòng đầu tiên: `Arch Linux install medium (x86_64, UEFI)`.
4. Đợi một lát, hệ thống sẽ tự động đăng nhập vào tài khoản root với giao diện dòng lệnh: `root@archiso ~ #`.

### Bước 2: Kết nối Internet
`archinstall` cần internet để tải các gói phần mềm mới nhất về máy.

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
    station wlan0 connect <Tên_Wifi_Của_Bạn
