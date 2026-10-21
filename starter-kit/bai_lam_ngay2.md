# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên:**
- **Lớp:**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):**

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
# Ghi lệnh vào đây
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\access.log | Select-String "ERROR"
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\access.log | Select-String "ERROR" | Out-File .\logs\error_report.txt
 ```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
(PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content -TotalCount 2 .\logs\error_report.txt)

```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
# Ghi 2 lệnh vào đây, mỗi lệnh một dòng 
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\access.log | Select-String "WARNING" | Measure-Object -Line

PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\payment.log | Select-String "ERROR" | Measure-Object -Line
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log: 4
ERROR trong payment.log: 3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây 
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> .\auto_warning.ps1

```

### Nội dung file logs/warning_report.txt

```text
2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng 
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh\logs> New-Item "tong_hop_ngay2.txt"
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh\logs> "=== TONG HOP ACCESS LOG ===" > .\tong_hop_ngay2.txt
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\access.log | Select-String "ERROR" >> .\logs\tong_hop_ngay2.txt
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\payment.log | Select-String "WARNING" >> .\logs\tong_hop_ngay2.txt
PS D:\rikkei-app\Thực Hành MarkDown.Minh Hiển\starter-kit (1)\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\payment.log | Select-String "WARNING" | Measure-Object -Line >> .\logs\tong_hop_ngay2.txt

```

### Nội dung file logs/tong_hop_ngay2.txt

```text
=== TONG HOP ACCESS LOG ===

2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)



2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi



Lines Words Characters Property
----- ----- ---------- --------
    5                       

```

## Bài 5. Câu hỏi ngắn

- **a) - lệnh ">" là để thêm một nội dung mới và xóa bỏ nội dung cũ ở trong tệp
- lệnh ">>" là chèn thêm nội dung với vào tệp nội dung cũ vẫn được dữ lại không bị mất**
- **b) - Nếu dùng lệnh ">" thì các nội dung có trong tệp sẽ bị mất và thay vào đó là nội dung mới**
- **c) - Vì đường dẫn tương đối giúp script dễ di chuyển và chạy được trên nhiều máy khác nhau mà không cần sửa đường dẫn**

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
