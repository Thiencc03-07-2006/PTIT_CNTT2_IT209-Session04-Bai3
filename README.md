# Bài 3: Cấu hình xác thực SSH và Đẩy dự án lên GitHub

Bài thực hành cấu hình SSH Ed25519 và kết nối repository local với GitHub.

## SSH

Đã tạo SSH Key sử dụng thuật toán Ed25519.

Đã cấu hình Public Key trên GitHub.

Kiểm tra kết nối:

```bash
ssh -T git@github.com
````

Kết nối SSH tới GitHub thành công.

## Repository

Repository được cấu hình sử dụng giao thức SSH.

Remote URL:

```text
git@github.com:USERNAME/REPOSITORY.git
```

## Push

Project được đẩy lên GitHub bằng:

```bash
git push -u origin main
```

Private Key không được đưa vào repository.