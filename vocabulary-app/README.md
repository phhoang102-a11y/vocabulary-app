# Sổ Từ Vựng (Vocabulary Learning Platform)

Nền tảng học từ vựng cho giáo viên và học sinh, được xây dựng với Supabase và JavaScript.

## Tính năng

### Cho giáo viên:
- **Quản lý bộ từ vựng**: Tạo, sửa, xóa bộ từ
- **Báo cáo tiến độ**: Xem chi tiết tiến độ học của từng học sinh
- **Quản lý lớp học**: Nhập danh sách học sinh để các em chọn tên

### Cho học sinh:
- **Học flashcard**: Luyện từ vựng bằng flashcard interactif
- **Kiểm tra nhanh**: Quiz 10 từ ngẫu nhiên
- **Theo dõi tiến độ**: Xem tiến độ cá nhân với biểu đồ

## Cách sử dụng

### Truy cập trang web
- **Cho giáo viên**: `https://your-domain.com/vocabulary-app.html#teacher`
- **Cho học sinh**: `https://your-domain.com/vocabulary-app.html`

### Để giáo viên tạo bộ từ
1. Truy cập trang quản lý với `#teacher`
2. Click "Bộ từ mới"
3. Nhập tên bộ từ
4. Nhập danh sách từ (mỗi dòng: `từ [tab] nghĩa`)
5. Click "Lưu bộ từ"

### Để học sinh học
1. Chọn tên từ danh sách hoặc nhập tên
2. Chọn bộ từ để học
3. Lật thẻ để xem nghĩa
4. Đánh dấu "Đã thuộc" hoặc "Chưa thuộc"
5. Hoàn thành bộ từ để làm kiểm tra

## Cài đặt Supabase

Ứng dụng này sử dụng Supabase làm backend. URL và key đã được nhúng trong code.

### Database Schema
- `sets`: Bộ từ vựng (title, words JSONB, due, createdAt, updatedAt)
- `progress`: Tiến độ học của học sinh (name, sets JSONB, joinedAt, lastAt)
- `config`: Cấu hình lớp (roster JSONB)

## Deployment

### Vercel
1. Tạo GitHub repository
2. Push code lên GitHub
3. Import repository vào [Vercel](https://vercel.com)
4. Click Deploy
5. Trang web sẽ được deploy tự động

### Localhost
```bash
npm start
# Hoặc
python -m http.server 8000
```

## Hỗ trợ

Nếu có lỗi, kiểm tra:
- Kết nối Supabase (URL và Key)
- Row Level Security (RLS) được bật trên các bảng
- Network connectivity

## License

MIT
