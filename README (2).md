# 💌 Trang Web Mời Hẹn Hò Lãng Mạn

Một trang web tương tác đầy lãng mạn, responsive tốt trên **desktop, tablet, và mobile** 📱

---

## 🎯 Tính Năng Chính

✨ **5 Bước Stepper:**
- **Bước 1:** Mời hẹn hò - Nút "No" chạy trốn khắp màn hình
- **Bước 2:** Chọn ngày/giờ hẹn
- **Bước 3:** Chọn món ăn (4 lựa chọn dạng grid)
- **Bước 4:** Xác nhận & gửi Telegram
- **Bước 5:** Cảm ơn + Hiệu ứng animation

🎨 **Design:**
- Tông màu pastel hồng (`#fce7ec`)
- Font chữ thanh lịch: Dancing Script + Poppins
- Card style với bóng mềm
- **Fully responsive:** Desktop, Tablet, Mobile (480px+)
- Animation mượt mà, hover effects

📲 **Mobile Optimized:**
- Font size cân bằng cho mỗi breakpoint
- Button 44px+ cho dễ click trên điện thoại
- Food grid tự động 1 cột trên mobile
- Image tự scale phù hợp
- Layout padding tối ưu cho màn hình nhỏ

🚀 **Telegram Integration:**
- Gửi lời mời trực tiếp qua Telegram Bot API
- Hiện "Đang gửi..." khi gửi
- Xử lý lỗi thân thiện

---

## 📋 Cài Đặt Telegram (QUAN TRỌNG)

### 1️⃣ Tạo Bot Telegram
```
1. Mở Telegram, tìm @BotFather
2. Gửi /start → /newbot
3. Đặt tên bot (vd: "Date Invitation Bot")
4. Đặt username (vd: "my_date_bot")
5. Sao chép BOT_TOKEN
```

### 2️⃣ Lấy CHAT_ID
```
1. Mở bot vừa tạo, gửi /start
2. Vào URL này (thay <BOT_TOKEN>):
   https://api.telegram.org/bot<BOT_TOKEN>/getUpdates
3. Tìm "chat": {"id": 123456789}
4. Sao chép số đó (CHAT_ID)
```

### 3️⃣ Cấu Hình File
Mở `index.html` với trình soạn thảo (VS Code, Notepad++, etc):
```javascript
// Tìm dòng này (khoảng dòng 630-631):
const BOT_TOKEN = 'YOUR_BOT_TOKEN';
const CHAT_ID = 'YOUR_CHAT_ID';

// Thay bằng:
const BOT_TOKEN = '123456:ABCdefGHIjklmnoPQRstUVwxyz';
const CHAT_ID = '987654321';
```

---

## 🚀 Cách Chạy

### **Cách 1: Chỉ cần mở file (Đơn giản nhất)**
```
1. Tải index.html về máy
2. Double-click vào file
3. Browser sẽ mở tự động
```

### **Cách 2: Dùng Local Server (Nếu có lỗi CORS)**
```bash
# Mở Terminal/CMD tại folder chứa index.html

# Windows:
python -m http.server 8000

# macOS/Linux:
python3 -m http.server 8000

# Rồi truy cập: http://localhost:8000/index.html
```

---

## 📱 Responsive Breakpoints

| Device | Width | Behavior |
|--------|-------|----------|
| **Desktop** | 769px+ | Full size, 2-column food grid |
| **Tablet** | 481-768px | Scaled down, adjusted padding |
| **Mobile** | ≤480px | Optimized for touch, 1-column grid |

### Mobile Features (≤480px):
- ✅ Nút bấm tối thiểu 44px × 44px (dễ chạm)
- ✅ Font chữ cân bằng: h1 1.6rem, h2 1.3rem
- ✅ Food grid chuyển 1 cột
- ✅ Padding giảm, nhưng vẫn đẹp
- ✅ Image tự-scale max 280px height
- ✅ Summary card padding tối ưu
- ✅ Input field padding & font size vừa vặn

---

## 🎮 Tính Năng Tương Tác

### Nút "No" Chạy Trốn 🏃‍♂️
```javascript
// Khi hover nút "No" → nó "chạy trốn"
// Thay đổi position sang fixed
// Random left/top trên màn hình
// Animation scale nhẹ nhàng
```

### Food Selection ✓
```javascript
// Click vào món ăn → highlight
// Thêm border pink, background light pink
// Lưu tên món vào formData
```

### Validation & Error Handling
- ✅ Kiểm tra date/time nhập
- ✅ Kiểm tra Telegram config
- ✅ Xử lý lỗi API
- ✅ Hiển thị tin nhắn lỗi rõ ràng

---

## 📂 Cấu Trúc File

```
date-invitation/
├── index.html          ← File duy nhất chứa tất cả
└── README.md          ← Hướng dẫn này
```

Không cần bất kỳ thư viện hay file bên ngoài!

---

## 🎨 Customize

### Đổi Màu
Mở `index.html`, tìm CSS section `RESET & BASE`:
```css
/* Màu chính (pastel pink): */
background: linear-gradient(135deg, #fce7ec 0%, #fff5f8 100%);

/* Màu nút/text (dark pink): */
color: #d63384;
```

### Đổi Emoji/Tiêu Đề
Tìm từng `<h1>`, `<h2>`, `<div class="step">`  
Thay emoji hoặc text theo ý bạn

### Đổi 4 Món Ăn
Tìm section `<!-- ==================== STEP 3: FOOD MISSION ==================== -->`
```html
<div class="food-item" onclick="selectFood(this, 'Tên Món')">
    <span class="food-emoji">🍗</span>
    <span class="food-name">Tên Món</span>
</div>
```

---

## 🐛 Troubleshooting

### ❌ "Lỗi gửi tin nhắn"
- Kiểm tra BOT_TOKEN có đúng không
- Kiểm tra CHAT_ID có đúng không
- Bot phải được start (`/start`) trước khi nhận tin

### ❌ "Nút chạy trốn không work"
- Kiểm tra console (F12) có lỗi không
- Refresh trang, thử lại

### ❌ "Mobile bị vẹo/lỗi layout"
- Refresh trang
- Xóa cache browser: Ctrl+Shift+Delete
- Thử browser khác

---

## 💡 Tips & Tricks

1. **Để test gửi Telegram mà không sợ lỗi:**
   - Thay CHAT_ID bằng ID của chính mình trước
   - Chạy qua lại mấy lần để test

2. **Customize thêm:**
   - Thêm GIF/ảnh khác ở bước 1
   - Thêm câu hỏi khác (vd: địa điểm)
   - Đổi icon emoji theo sở thích

3. **Share link:**
   - Host file lên GitHub Pages
   - Dùng Vercel, Netlify (free)
   - Send link cho người khác

---

## 📧 Telegram Message Format

Tin nhắn gửi sẽ như thế này:

```
🎉 LỜI MỜI HẸN HÒ 🎉

Tôi muốn mời bạn đi hẹn hò! 💕

📅 Ngày: Thứ Sáu, 15 tháng 6 năm 2026
🕐 Giờ: 19:30
🍽️ Thực Ăn: Ramen

Hy vọng bạn sẽ nói "YES"! 🥰
```

---

## ✨ Features Code

- **Pure Vanilla JS:** Không dùng jQuery, React, hay framework gì
- **1 File:** HTML + CSS + JS tất cả trong 1 file duy nhất
- **Responsive:** Mobile-first approach, 3 breakpoints
- **Async/Await:** Modern JavaScript, xử lý Telegram API bất đồng bộ
- **Error Handling:** Kiểm tra input, xử lý API errors
- **Smooth Animations:** Fade-in, float, heartbeat effects
- **Accessibility:** Min touch size 44px, semantic HTML

---

## 🎉 Chúc Mừng!

Bạn đã sẵn sàng mời người yêu đi hẹn hò bằng web lãng mạn này! 💕

Nếu có bất kỳ vấn đề gì, hãy kiểm tra:
1. Telegram config (BOT_TOKEN, CHAT_ID)
2. Console browser (F12 → Console tab)
3. File đã được save chưa?

**Happy dating! 🥰💌**
