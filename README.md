# N3 語彙 — Web luyện từ vựng N3

App tĩnh (HTML/JS thuần) học từ vựng N3 theo sách *Mimi Kara Oboeru N3 Goi*.
Trắc nghiệm Nhật→Việt, furigana, flashcard, test theo Unit / 50 từ / 2 Unit / tổng hợp,
ghi lại số giờ học mỗi ngày. Cài được vào màn hình chính (PWA), học offline.

## Chạy thử trên máy
Mở `index.html` bằng Chrome là chạy. (Nếu Service Worker không chạy khi mở file trực tiếp,
dùng server tĩnh: `python -m http.server 8099` rồi vào http://localhost:8099 )

## Đưa lên GitHub Pages (tên miền username.github.io)

**Khuyến nghị: tạo repo riêng tên `n3goi`** (không đụng tới trang chính của bạn).
Link sẽ là: `https://<tên-github>.github.io/n3goi/`

### Cách 1 — Kéo thả trên web (dễ nhất)
1. Vào https://github.com/new → đặt tên repo `n3goi` → chọn **Public** → Create.
2. Mở repo → **Add file ▸ Upload files** → kéo TẤT CẢ file trong thư mục này
   (`index.html`, `data.js`, `manifest.webmanifest`, `sw.js`, `icon-192.png`,
   `icon-512.png`, `icon-maskable.png`, `icon.svg`) vào → **Commit changes**.
3. Vào tab **Settings ▸ Pages** → mục *Build and deployment* → Source: **Deploy from a branch**
   → Branch: **main** / **/(root)** → **Save**.
4. Đợi ~1 phút, mở `https://<tên-github>.github.io/n3goi/` trên điện thoại/máy tính.

### Cách 2 — Dùng git (nếu bạn quen dòng lệnh)
```bash
cd n3goi
git init
git add .
git commit -m "N3 vocab app"
git branch -M main
git remote add origin https://github.com/<tên-github>/n3goi.git
git push -u origin main
```
Rồi làm bước 3–4 ở Cách 1.

## Cài vào màn hình chính (điện thoại Realme – Chrome)
Mở link `.github.io/n3goi/` → menu **⋮** ▸ **Thêm vào Màn hình chính / Cài đặt ứng dụng**.
Sau đó mở như 1 app, học offline được.

## Cập nhật từ vựng
Toàn bộ từ nằm trong `data.js` (mảng `window.N3DATA.words`). Mỗi lần thêm/sửa từ,
chỉ cần upload lại `data.js` và **đổi số version** trong `sw.js` (`n3goi-v1` → `n3goi-v2`)
để điện thoại tải bản mới.
