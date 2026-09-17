# 🗺️ Phường Long Hương - Bản Đồ Vệ Tinh

Ứng dụng web bản đồ vệ tinh hiển thị dữ liệu thửa đất từ file GeoJSON.

🌐 **Live**: [Xem bản đồ](./index.html)

---

## ✨ Tính Năng

- 🛰️ **Bản Đồ Vệ Tinh HD** - Ảnh Esri chất lượng cao
- 🔍 **Tìm Kiếm** - Tìm thửa đất theo số thửa/tờ
- 📍 **Xem Tọa Độ** - Hiển thị GPS khi hover
- 🗺️ **Chuyển Basemap** - Vệ tinh, OSM, CartoDB
- 📱 **Mobile Responsive** - Hiệu ứng mượt mà
- ⚡ **Tĩnh 100%** - Không cần server

---

## 📂 Cấu Trúc

```
📦 LAND/
├── 📄 index.html         # Bản đồ chính
├── 📊 DatCong.geojson    # Dữ liệu thửa đất
└── 📖 README.md          # File này
```

---

## 🚀 Sử Dụng

### Local
```bash
# Python 3
python -m http.server 8000

# Hoặc mở trực tiếp
open index.html
```

### GitHub Pages
```bash
# 1. Git init
git init
git add .
git commit -m "Initial: Phuong Long Huong Map"

# 2. Push
git remote add origin https://github.com/YOUR_USERNAME/LAND.git
git push -u origin main

# 3. Enable Pages (Settings → Pages → Deploy from main/root)

# 4. Truy cập
https://YOUR_USERNAME.github.io/LAND/
```

---

## 🎯 GeoJSON

File `DatCong.geojson` chứa:
- **Features**: Polygon thửa đất
- **Properties**: 
  - `Sothua`: Số thửa
  - `So_To`: Số tờ
  - `Shape_Area`: Diện tích (m²)

---

## 🔗 URL Parameters

Zoom vào vị trí cụ thể:

```
?lat=10.482&lng=107.155&z=18&sothua=222
```

| Param | Mô Tả |
|-------|-------|
| `lat` | Latitude |
| `lng` | Longitude |
| `z` | Zoom (1-20) |
| `sothua` | Số thửa |

---

## 📱 Thiết Kế

✅ Mobile-First
✅ Touch-Friendly (44x44px buttons)
✅ Safe Area Support
✅ Dark Mode Compatible
✅ Fast Loading

---

## 🛠️ Stack

- HTML5, CSS3, JavaScript
- Leaflet.js (Map)
- GeoJSON (Data)
- GitHub Pages (Hosting)

---

## 🎨 Basemap

- 🛰️ **Vệ Tinh**: Esri World Imagery
- 🗺️ **OSM**: OpenStreetMap
- 🛣️ **Street**: CartoDB Voyager

---

## 📊 Stats

- **Thửa đất**: ~200+ (từ GeoJSON)
- **Zoom**: 1-20
- **Format**: GeoJSON Polygons
- **Diện tích**: Tính toán từ properties

---

## 🔍 Tìm Kiếm

Nhập số thửa hoặc số tờ để lọc hiển thị

---

## 🌐 Deploy

### GitHub Pages (Recommended)
- Free hosting
- Auto-deploy trên push
- Custom domain support

### Netlify
```bash
netlify deploy --prod
```

### Vercel
```bash
vercel
```

---

## 📝 Cập Nhật Dữ Liệu

Sửa `DatCong.geojson` rồi push:

```bash
git add DatCong.geojson
git commit -m "Update: Thêm thửa đất mới"
git push
```

Bản đồ sẽ tự động cập nhật trên GitHub Pages.

---

## 🐛 Xử Lý Sự Cố

### "Bản đồ không tải"
- Xóa cache: `Ctrl+Shift+Del`
- Hard refresh: `Ctrl+F5`
- Kiểm tra F12 → Console

### "GeoJSON không hiển thị"
- Kiểm tra file `DatCong.geojson` tồn tại
- Validate JSON: https://jsonlint.com/
- Kiểm tra format GeoJSON

### "Không truy cập được"
- Đợi 1-2 phút GitHub deploy
- Kiểm tra Settings → Pages
- Refresh page: `Ctrl+F5`

---

## 📚 Tài Liệu

- [Leaflet.js](https://leafletjs.com)
- [GeoJSON Spec](https://geojson.org)
- [GitHub Pages](https://docs.github.com/en/pages)

---

## 📄 License

MIT License

---

**Made for Phường Long Hương, Quận 7, TP.HCM**
