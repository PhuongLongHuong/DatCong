# Hướng Dẫn Deploy lên GitHub Pages

## 🔧 Vấn đề Đã Sửa

### 1. **Lỗi Tải JSON trên GitHub Pages**
   - **Nguyên nhân**: Đường dẫn tương đối không hoạt động trên GitHub Pages khi repo không ở root
   - **Giải pháp**: Thêm BASE_PATH detection tự động điều chỉnh đường dẫn file

### 2. **Lỗi Null Element**
   - **Nguyên nhân**: Code cố gắng update element không tồn tại
   - **Giải pháp**: Thêm kiểm tra element trước khi update

### 3. **Mobile Responsiveness**
   - **Nguyên nhân**: Sidebar cố định trên mobile không thích hợp
   - **Giải pháp**: Thêm hamburger menu button và toggle sidebar

---

## 📱 Tính Năng

✅ **Desktop**: Sidebar luôn hiển thị + Control Panel bên phải  
✅ **Mobile**: Hamburger menu + Fullscreen map + Control Panel overlay  
✅ **Cross-platform**: Hoạt động giống nhau trên tất cả devices  
✅ **GitHub Pages**: Tự động detect path và load files đúng

---

## 🚀 Cách Deploy lên GitHub Pages

### **Bước 1: Tạo GitHub Repository**

```bash
# Tạo folder mới hoặc dùng folder hiện tại
cd C:\xampp\htdocs\LAND

# Khởi tạo git
git init
git add .
git commit -m "Initial commit"

# Thêm remote (thay YOURUSERNAME và YOURREPO)
git remote add origin https://github.com/YOURUSERNAME/YOURREPO.git
git branch -M main
git push -u origin main
```

### **Bước 2: Kích Hoạt GitHub Pages**

1. Vào GitHub → Settings → Pages
2. Chọn **Deploy from a branch**
3. Branch: **main** | Folder: **/root**
4. Lưu thay đổi

### **Bước 3: Truy Cập**

Sau 1-2 phút, app sẽ có sẵn tại:
```
https://YOURUSERNAME.github.io/YOURREPO
```

---

## 📝 Cách Cập Nhật

Sau khi thay đổi files:

```bash
git add .
git commit -m "Update description"
git push
```

GitHub Pages tự động cập nhật trong vòng 1-2 phút.

---

## 🛠️ Cấu Trúc File

```
LAND/
├── index.html           ← Main page
├── Giaothong.json       ← Traffic layer
├── Songngoi.json        ← Rivers layer
├── Thuadatcong.json     ← Public land layer
├── Phuongline.json      ← Boundary layer
├── Khupho.json          ← District labels
└── GITHUB_PAGES_SETUP.md
```

---

## ⚙️ Cấu Hình Cho Repository Khác

Nếu muốn thay đổi path:

```javascript
// Mặc định tự động detect:
const BASE_PATH = window.location.pathname.includes('github.io')
    ? window.location.pathname.substring(0, window.location.pathname.lastIndexOf('/') + 1)
    : './';

// Hoặc hardcode (nếu cần):
const BASE_PATH = '/YOURREPO/';
```

---

## 📊 Kiểm Tra Lỗi

1. **Mở Developer Console** (F12)
2. **Check**: 
   - BASE_PATH giá trị đúng không
   - JSON files load thành công không
   - Map display đúng không

---

## 🎨 Tính Năng Bổ Sung

### Desktop View
- Sidebar bên trái (340px) luôn hiển thị
- Control Panel bên phải toggle với nút ⚙️
- Full map view

### Mobile View (< 768px)
- Sidebar ẩn, hiện khi click ☰ button
- Fullscreen map (tập trung vào dữ liệu)
- Control Panel overlay bên phải
- Auto close sidebar khi click map

---

## ✨ Responsive Design

| Screen | Layout |
|--------|--------|
| Desktop (>768px) | Sidebar + Map + Panel |
| Tablet (600-768px) | Map + Mobile Panel |
| Mobile (<600px) | Map + Hamburger + Panel |

---

## 💡 Mẹo

- **Fast Loading**: JSON files tự động load khi page init
- **Touch Support**: Touch events tối ưu cho mobile
- **High Zoom**: Map zoom tới level 19 cho chi tiết
- **Responsive**: Leaflet tự động resize khi rotate device

Enjoy! 🎉
