# Hướng dẫn Deployment

## Bước 1: Chuẩn bị GitHub

### 1.1 Tạo GitHub repository
1. Đăng nhập vào [GitHub](https://github.com)
2. Click **+** → **New repository**
3. Đặt tên: `vocabulary-app` (hoặc tên khác)
4. Chọn **Public** (hoặc Private)
5. Click **Create repository**

### 1.2 Clone repository về máy
```bash
git clone https://github.com/YOUR-USERNAME/vocabulary-app.git
cd vocabulary-app
```

### 1.3 Copy files vào folder
Copy những file này vào folder `vocabulary-app`:
- `vocabulary-app.html`
- `package.json`
- `README.md`
- `.gitignore`
- `vercel.json`

### 1.4 Push code lên GitHub
```bash
git add .
git commit -m "Initial commit: vocabulary learning platform with Supabase"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/vocabulary-app.git
git push -u origin main
```

## Bước 2: Deploy lên Vercel

### 2.1 Tạo tài khoản Vercel
1. Truy cập [Vercel](https://vercel.com)
2. Click **Sign up** hoặc **Sign in with GitHub**

### 2.2 Import GitHub repository
1. Click **Add New...** → **Project**
2. Click **Import Git Repository**
3. Dán URL GitHub repository
4. Click **Continue**

### 2.3 Configure project
1. **Project name**: `vocabulary-app`
2. **Framework**: Chọn **Other** hoặc để trống
3. **Root directory**: `/` (để trống)
4. Click **Deploy**

### 2.4 Chờ deployment hoàn thành
Vercel sẽ tự động:
- Build project
- Deploy files
- Cấp domain (*.vercel.app)

## Bước 3: Lấy URL chia sẻ

Sau deployment, Vercel sẽ cấp cho bạn URL như:
```
https://vocabulary-app-xxxx.vercel.app
```

### Chia sẻ cho học sinh:
- **Giao viên**: `https://vocabulary-app-xxxx.vercel.app/vocabulary-app.html#teacher`
- **Học sinh**: `https://vocabulary-app-xxxx.vercel.app/vocabulary-app.html`

## Bước 4: Test

### Test chức năng giao viên
1. Mở link teacher
2. Tạo bộ từ mới
3. Nhập vài từ
4. Lưu bộ từ

### Test chức năng học sinh
1. Mở link học sinh (không có `#teacher`)
2. Nhập tên
3. Chọn bộ từ
4. Học bằng flashcard

## Cập nhật code

Mỗi lần sửa code, chỉ cần:
```bash
git add .
git commit -m "Fix: tên sửa"
git push
```

Vercel sẽ **tự động deploy** các thay đổi!

## Troubleshooting

### Lỗi: "Connection refused"
→ Kiểm tra Supabase URL và Key trong HTML

### Lỗi: "Not found"
→ Tên file có đúng không? (`vocabulary-app.html`)

### Lỗi: "CORS error"
→ Supabase RLS có được bật không?

### Deploy lâu
→ Chờ thêm, thường mất 1-2 phút

## Cần giúp?

Nếu có vấn đề, kiểm tra:
1. GitHub repository có file không
2. Vercel project được tạo đúng
3. Supabase database được setup
4. Browser console (F12) để xem lỗi
