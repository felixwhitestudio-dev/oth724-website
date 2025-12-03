# OTH 7/24 Franchise Website

เว็บไซต์แฟรนไชส์ร้านสะดวกซื้อ 24 ชั่วโมง สำหรับประเทศลาว

## 🎯 คุณสมบัติ

- ✅ ดีไซน์สไตล์มินิมอล (Uniqlo/Muji inspired)
- ✅ Responsive บนทุกหน้าจอ
- ✅ SEO Optimized (Meta Tags, Schema.org, Sitemap)
- ✅ Contact Form พร้อม JavaScript validation
- ✅ Payment Methods Display (Visa, Mastercard, JCB, Alipay, PromptPay, BCEL, LDB, APB)
- ✅ Google Analytics และ Facebook Pixel ready
- ✅ Privacy Policy และ Terms of Service
- ✅ Smooth scroll navigation

## 🚀 Quick Start

### Development Server

```bash
# ติดตั้ง dependencies
npm install

# รัน development server
npm run dev

# เปิด browser ที่ http://localhost:3000
```

### Production Build

ไฟล์พร้อม deploy ทันที! ไม่ต้อง build เพิ่ม

## 📁 โครงสร้างไฟล์

```
oth-minimart/
├── index.html              # หน้าหลัก
├── privacy-policy.html     # นโยบายความเป็นส่วนตัว
├── terms.html             # ข้อกำหนดและเงื่อนไข
├── styles.css             # สไตล์ทั้งหมด
├── sitemap.xml            # Sitemap สำหรับ SEO
├── robots.txt             # คำแนะนำสำหรับ search engines
├── package.json           # NPM configuration
├── DEPLOY.md              # คู่มือการ Deploy
└── public/images/         # รูปภาพและโลโก้
```

## 🔧 ต้องทำก่อน Deploy

1. **สร้าง Favicon และ OG Image**
   - `public/images/favicon-32x32.png`
   - `public/images/favicon-16x16.png`
   - `public/images/apple-touch-icon.png`
   - `public/images/og-image.jpg` (1200x630px)
   - `public/images/logo.png`

2. **Setup Contact Form**
   - สมัคร Formspree: https://formspree.io/
   - แก้ไข Form ID ใน `index.html` บรรทัด 414

3. **Setup Google Analytics**
   - สร้าง GA4 Property: https://analytics.google.com/
   - แก้ไข `YOUR_GA_ID` ใน `index.html` บรรทัด 61, 66

4. **Update URLs**
   - แก้ไข `oth724.com` เป็นโดเมนจริงในไฟล์:
     - `index.html`
     - `sitemap.xml`
     - `robots.txt`

📖 **ดูรายละเอียดเพิ่มเติมใน [DEPLOY.md](DEPLOY.md)**

## 📊 SEO Features

- ✅ Meta Description และ Keywords
- ✅ Open Graph Tags (Facebook sharing)
- ✅ Twitter Cards
- ✅ Schema.org Structured Data (JSON-LD)
- ✅ Sitemap.xml
- ✅ Robots.txt
- ✅ Semantic HTML5

## 🎨 Design System

### สี (Colors)
- **Primary Green:** #047857
- **Secondary Green:** #059669
- **Gold Accent:** #fbbf24
- **Red:** #dc2626
- **White/Light:** #ffffff, #f9fafb

### Typography
- **Logo:** Arial, Helvetica Neue (Bold, Uppercase)
- **Body:** -apple-system, BlinkMacSystemFont, Segoe UI

## 📱 Contact

- **อีเมล:** franchise@oth724.com
- **โทร:** +856 20 9651 5095
- **LINE ID:** @oth724
- **ที่อยู่:** Vientiane Capital, Lao PDR

## 📄 License

© 2025 OTH 7/24 Franchise. All Rights Reserved.

---

**สร้างด้วย:** HTML5, CSS3, JavaScript (Vanilla)  
**เวอร์ชัน:** 1.0
