# 🖼️ Hướng dẫn thiết lập khung cố định

## 📋 Cách thay đổi khung cố định

### Bước 1: Chuẩn bị khung
1. **Format ảnh**: Sử dụng PNG với nền trong suốt
2. **Kích thước**: Khuyến nghị 500x500px hoặc tỷ lệ 1:1
3. **Chất lượng**: Độ phân giải cao để đảm bảo khung sắc nét

## 🎯 PHƯƠNG PHÁP 1: Sử dụng File Local (Khuyến nghị)

### Bước 2A: Đặt file khung local
1. **Đổi tên file** khung thành `frame.png`
2. **Đặt file** trong cùng thư mục với `index.html`
3. **Cấu trúc thư mục** sẽ như sau:
   ```
   📁 gen-avatar-with-frame-app/
   ├── 📄 index.html
   ├── 🖼️ frame.png      ← File khung của bạn
   └── 📄 FRAME_SETUP.md
   ```

### Bước 3A: Kiểm tra code
Code đã được thiết lập để sử dụng file local:
```javascript
const FIXED_FRAME_URL = "./frame.png";
```

**Ưu điểm của file local:**
- ✅ Không cần internet để load khung
- ✅ Tốc độ load nhanh hơn
- ✅ Không có vấn đề CORS
- ✅ Bảo mật cao hơn

## 🌐 PHƯƠNG PHÁP 2: Sử dụng URL Online

### Bước 2B: Upload khung lên hosting
Bạn có thể sử dụng một trong các dịch vụ sau:

#### 🔗 **Imgur** (Miễn phí, dễ sử dụng)
1. Truy cập: https://imgur.com
2. Kéo thả file ảnh khung
3. Copy "Direct Link" (kết thúc bằng .png)

#### 🔗 **ImgBB** (Miễn phí)
1. Truy cập: https://imgbb.com
2. Upload ảnh
3. Copy "Direct Link"

#### 🔗 **Cloudinary** (Chuyên nghiệp)
1. Tạo account tại cloudinary.com
2. Upload ảnh
3. Copy URL

### Bước 3B: Cập nhật code cho URL online
Mở file `index.html` và tìm dòng:
```javascript
const FIXED_FRAME_URL = "./frame.png";
```

Thay thế bằng URL online:
```javascript
const FIXED_FRAME_URL = "YOUR_ONLINE_URL_HERE";
```

**Lưu ý**: Nếu dùng URL online, cần thêm lại:
```javascript
frameImg.crossOrigin = "anonymous";
```

### Bước 4: Test
1. Mở file HTML trong trình duyệt
2. Upload một ảnh avatar để test
3. Kiểm tra khung hiển thị đúng không

## 🎨 Khung backup
Nếu khung chính không load được, hệ thống sẽ tự động sử dụng khung tròn đơn giản được tạo bằng SVG.

## 💡 Tips thiết kế khung
1. **Để viền trong suốt** ở giữa để ảnh avatar hiển thị
2. **Thiết kế đẹp mắt** phù hợp với mục đích sử dụng
3. **Tránh quá chi tiết** để không làm lộn xộn
4. **Test với nhiều ảnh khác nhau** để đảm bảo khung phù hợp

## 🔧 Troubleshooting
- **Khung không hiển thị**: Kiểm tra URL có đúng không
- **Lỗi CORS**: Đảm bảo dịch vụ hosting hỗ trợ cross-origin
- **Khung bị méo**: Kiểm tra tỷ lệ ảnh gốc
