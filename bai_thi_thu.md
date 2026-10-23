

# BÀI LÀM – THI THỬ HACKATHON 01

-   **Mã đề:** Thi thử

-   **Họ tên:** Nguyễn Gia Thịnh

-   **Lớp:** CNTT1

-   **Link repository:**

-   **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```
Get-Location
Get-ChildItem -Force
Move-Item nhap_hang.txt docs
Move-Item logo_van_phong_pham.png media
 Copy-Item media\logo_van_phong_pham.png backup
 Remove-Item temp_131.tmp
 cd logs
 Get-ChildItem
 cd..
 Get-Location
 Get-ChildItem -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```

    Directory:
    C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   9:09 AM                backup
d-----        10/23/2026   8:54 AM                data
d-----        10/23/2026   9:07 AM                docs
d-----        10/23/2026   8:54 AM                logs
d-----        10/23/2026   9:08 AM                media
-a----        10/19/2026   9:41 AM             78 .env
-a----        10/19/2026  10:00 AM           2253 bai_lam.md


    Directory: C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-we
    bsite\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png


    Directory:
    C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6105 Don Ban Thang 10.xlsx


    Directory:
    C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM             51 nhap_hang.txt


    Directory:
    C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           1053 shop.log


    Directory:
    C:\Users\admin\Desktop\BTontap\starter-kit\van-phong-pham-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```
Get-Content  logs\shop.log  |  Select-String  "ERROR"
Get-Content  logs\shop.log  |  Select-String  "ERROR"  >  logs\daily_report.txt
Get-Content  logs\daily_report.txt


```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
```

## 4.4. Thao tác với tài liệu Markdown ([README.md](http://README.md))

> [README.md](http://README.md) được chấm trực tiếp trên file [README.md](http://README.md) ở gốc dự án. Đánh dấu [x] vào các mục đã làm để tự kiểm tra.

-   [x] Heading 1: tên dự án

-   [x] Mô tả ngắn có cả **in đậm** và _in nghiêng_

-   [x] Bảng Thư mục | Nội dung, ít nhất 3 dòng dữ liệu

-   [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án

-   [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành

-   [x] Blockquote nhắc không upload .env

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```
Set-ExecutionPolicy -Scope Process Bypass .\auto_report.ps1
```

### Nội dung file logs/auto_report.txt

```
# Script: auto_report.ps1
# Tac gia: Thinh
# Ngay tao: 23/10/2026

Write-Host "Dang loc log..."
"=== BAO CAO LOI ===" > logs\auto_report.txt
Get-Content logs\shop.log | Select-String "ERROR" >> logs\auto_report.txt
Write-Host "Hoan thanh!"
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```
(Get-Content  logs\shop.log  |  Select-String  "ERROR").Count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```
6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```
"=== TONG HOP LOG ==="  >  logs\tong_hop.txt
Get-Content  logs\shop.log  |  Select-String  "WARNING"  >>  logs\tong_hop.txt
(Get-Content  logs\shop.log  |  Select-String  "ERROR").Count  |  Out-File  logs\tong_hop.txt  -Append
Get-Content  logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```
=== TONG HOP LOG ===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham


6

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file data/don_ban_thang_10.xlsx, không cần ghi vào đây.
