# Bài 3: Cấu hình xác thực SSH và Đẩy dự án lên GitHub

## 1. Tạo SSH Key Ed25519

Sử dụng thuật toán Ed25519 để tạo cặp khóa SSH:

```bash
ssh-keygen -t ed25519
```

Cặp khóa được tạo gồm:

* `id_ed25519`: Private Key
* `id_ed25519.pub`: Public Key

Private Key được giữ bảo mật trên máy cá nhân và không được đưa lên GitHub.

## 2. Cấu hình SSH trên GitHub

Public Key `id_ed25519.pub` được thêm vào GitHub tại:

**GitHub → Settings → SSH and GPG keys → New SSH key**

## 3. Kiểm tra kết nối SSH

Sử dụng lệnh:

```bash
ssh -T git@github.com
```
```
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi Thiencc03-07-2006! You've successfully authenticated, but GitHub does not provide shell access.
```

Kết quả xác nhận kết nối SSH tới tài khoản GitHub thành công.

## 4. Khởi tạo Git Repository

Khởi tạo Git Repository cho project:

```bash
git init
```

Thêm các tệp vào Staging Area:

```bash
git add .
```

Tạo commit đầu tiên:

```bash
git commit -m "Initial commit"
```

## 5. Liên kết với GitHub Repository

Remote `origin` được cấu hình bằng giao thức SSH:

```bash
git remote add origin git@github.com:Thiencc03-07-2006/PTIT_CNTT2_IT209-Session04-Bai3.git
```

Kiểm tra remote:

```bash
git remote -v
```

Kết quả có dạng:

```text
origin  git@github.com:Thiencc03-07-2006/PTIT_CNTT2_IT209-Session04-Bai3.git (fetch)
origin  git@github.com:Thiencc03-07-2006/PTIT_CNTT2_IT209-Session04-Bai3.git (push)
```

## 6. Đẩy project lên GitHub

Đổi tên branch chính thành `main`:

```bash
git branch -M main
```

Đẩy project lên GitHub:

```bash
git push -u origin main
```

## 7. Repository GitHub

URL repository:

```text
git@github.com:Thiencc03-07-2006/PTIT_CNTT2_IT209-Session04-Bai3.git
```

## 8. Bảo mật

Private Key `id_ed25519` không được đưa vào repository hoặc chia sẻ cho người khác.

Chỉ sử dụng Public Key `id_ed25519.pub` để cấu hình xác thực SSH với GitHub.
