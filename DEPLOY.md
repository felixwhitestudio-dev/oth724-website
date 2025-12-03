# 📋 คู่มือการ Deploy เว็บไซต์ OTH 7/24 สู่ Production

## ✅ สิ่งที่ทำเสร็จแล้ว

### 1. Meta Tags และ SEO
- ✅ เพิ่ม Open Graph tags สำหรับ Facebook sharing
- ✅ เพิ่ม Twitter Cards
- ✅ เพิ่ม Schema.org structured data (JSON-LD)
- ✅ สร้าง sitemap.xml และ robots.txt
- ✅ เพิ่ม meta keywords และ description

### 2. Contact Form
- ✅ เพิ่ม JavaScript handler สำหรับ form submission
- ✅ ตั้งค่าพร้อมใช้กับ Formspree (ต้องแก้ไข Form ID)
- ✅ เพิ่ม validation และ error handling
- ✅ เพิ่ม smooth scroll navigation

### 3. Analytics
- ✅ เพิ่ม Google Analytics placeholder
- ✅ เพิ่ม Facebook Pixel placeholder

### 4. Privacy & Terms
- ✅ สร้างหน้า privacy-policy.html
- ✅ สร้างหน้า terms.html
- ✅ เพิ่มลิงก์ใน footer

---

## 📝 สิ่งที่ต้องทำก่อน Deploy

### 1. 🎨 สร้าง Favicon และ OG Image

คุณต้องสร้างไฟล์ภาพเหล่านี้และวางใน `public/images/`:

```
public/images/
├── favicon-32x32.png    (32x32 px)
├── favicon-16x16.png    (16x16 px)
├── apple-touch-icon.png (180x180 px)
├── og-image.jpg         (1200x630 px) สำหรับ social sharing
└── logo.png             (สัญลักษณ์โลโก้สำหรับ Schema.org)
```

**วิธีสร้าง Favicon:**
- ใช้เครื่องมือออนไลน์: https://realfavicongenerator.net/
- หรือใช้ Adobe Photoshop/Figma export เป็น PNG

---

### 2. 📧 Setup Contact Form (Formspree)

**ขั้นตอน:**

1. ไปที่ https://formspree.io/
2. สมัครสมาชิก (ฟรี)
3. สร้าง Form ใหม่
4. คัดลอก Form ID (เช่น `xyzabc123`)
5. แก้ไขใน `index.html` บรรทัด 414:

```html
<!-- เปลี่ยนจาก -->
<form id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">

<!-- เป็น -->
<form id="contactForm" action="https://formspree.io/f/xyzabc123" method="POST">
```

**ทางเลือกอื่น:** EmailJS, SendGrid, หรือเขียน Backend API เอง

---

### 3. 📊 Setup Google Analytics

**ขั้นตอน:**

1. ไปที่ https://analytics.google.com/
2. สร้าง Property ใหม่ (GA4)
3. คัดลอก Measurement ID (รูปแบบ: `G-XXXXXXXXXX`)
4. แก้ไขใน `index.html` บรรทัด 61 และ 66:

```html
<!-- เปลี่ยนจาก -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_GA_ID"></script>
gtag('config', 'YOUR_GA_ID');

<!-- เป็น -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
gtag('config', 'G-XXXXXXXXXX');
```

---

### 4. 📱 Setup Facebook Pixel (Optional)

**ขั้นตอน:**

1. ไปที่ Facebook Events Manager
2. สร้าง Pixel ใหม่
3. คัดลอก Pixel ID
4. แก้ไขใน `index.html` บรรทัด 76-78 (ลบ `//` ออก):

```javascript
fbq('init', 'YOUR_PIXEL_ID');  // เปลี่ยนเป็น Pixel ID ของคุณ
fbq('track', 'PageView');
```

---

### 5. 🌐 Update URLs

แก้ไข URL ในไฟล์ทั้งหมดจาก `oth724.com` เป็นโดเมนจริงของคุณ:

**ไฟล์ที่ต้องแก้:**
- `index.html` - บรรทัด 18, 20, 23, 28, 31, 39, 40
- `sitemap.xml` - ทุกบรรทัดที่มี URL
- `robots.txt` - บรรทัด 3

**ตัวอย่าง:**
```html
<!-- เปลี่ยนจาก -->
<meta property="og:url" content="https://oth724.com/" />

<!-- เป็น -->
<meta property="og:url" content="https://www.yourdomain.com/" />
```

---

## 🚀 Deploy ไปยัง Production

### วิธีที่ 1: Netlify (แนะนำ - ฟรีและง่าย)

1. ไปที่ https://www.netlify.com/
2. สมัครสมาชิกด้วย GitHub
3. เลือก "Add new site" → "Deploy manually"
4. Drag & Drop โฟลเดอร์ `oth-minimart` ทั้งหมด
5. รอสักครู่จะได้ URL ชั่วคราว (เช่น `random-name.netlify.app`)
6. Custom Domain:
   - ไปที่ Domain settings
   - Add custom domain
   - ตั้งค่า DNS ตามที่แนะนำ
7. SSL จะติดตั้งอัตโนมัติ (Let's Encrypt ฟรี)

---

### วิธีที่ 2: GitHub Pages (ฟรี)

1. สร้าง GitHub repository ชื่อ `oth-minimart`
2. Upload ไฟล์ทั้งหมดขึ้น GitHub
3. ไปที่ Settings → Pages
4. เลือก Source: "Deploy from a branch"
5. เลือก Branch: `main` → `/root`
6. Save และรอสักครู่
7. URL จะเป็น: `https://yourusername.github.io/oth-minimart/`
8. Custom domain: เพิ่ม CNAME file หรือตั้งค่าใน Settings

---

### วิธีที่ 3: Vercel (รวดเร็วที่สุด)

1. ไปที่ https://vercel.com/
2. Import project จาก GitHub
3. Deploy จะเสร็จภายใน 30 วินาที
4. Custom domain ตั้งค่าได้ง่าย
5. SSL อัตโนมัติ

---

### วิธีที่ 4: Traditional Hosting (Hostinger, GoDaddy, etc.)

1. เช่า Shared Hosting หรือ VPS
2. เข้า cPanel หรือ File Manager
3. Upload ไฟล์ทั้งหมดไปยัง `public_html/` หรือ `www/`
4. ตรวจสอบ file permissions (644 สำหรับไฟล์, 755 สำหรับโฟลเดอร์)
5. ติดตั้ง SSL Certificate:
   - ใช้ Let's Encrypt (ฟรี) ผ่าน cPanel
   - หรือซื้อ SSL แยก

---

## 🔧 หลัง Deploy

### 1. ทดสอบ Website

- [ ] เปิดเว็บไซต์และเช็คทุกหน้า
- [ ] ทดสอบ Contact Form โดยส่งข้อความจริง
- [ ] เช็ค Mobile Responsive บนมือถือ
- [ ] ทดสอบความเร็วด้วย https://pagespeed.web.dev/
- [ ] ตรวจสอบ SSL (ต้องมี 🔒 ใน URL bar)

### 2. Submit to Search Engines

**Google:**
1. ไปที่ https://search.google.com/search-console
2. Add property (ใส่ URL เว็บไซต์)
3. Verify ownership (ใช้ HTML tag หรือ DNS)
4. Submit sitemap: `https://yourdomain.com/sitemap.xml`

**Bing:**
1. ไปที่ https://www.bing.com/webmasters
2. Add site
3. Submit sitemap

### 3. Test Open Graph

- Facebook Sharing Debugger: https://developers.facebook.com/tools/debug/
- Twitter Card Validator: https://cards-validator.twitter.com/

---

## 📊 Monitoring และ Maintenance

### ประจำสัปดาห์:
- เช็ค Google Analytics (จำนวนผู้เข้าชม, แหล่งที่มา)
- เช็คข้อความจาก Contact Form
- ตรวจสอบ uptime (ใช้ UptimeRobot ฟรี)

### ประจำเดือน:
- อัพเดทราคาสินค้าหรือโปรโมชัน
- เช็ค Google Search Console (keywords, errors)
- Backup เว็บไซต์

### ประจำไตรมาส:
- ตรวจสอบและอัพเดท Privacy Policy
- เช็ค SSL certificate (ต้องไม่หมดอายุ)

---

## 🔐 Security Checklist

- [ ] ตรวจสอบว่า SSL ทำงานถูกต้อง (https://)
- [ ] เปลี่ยน Formspree Form ID (ไม่ใช่ YOUR_FORM_ID)
- [ ] ไม่เปิดเผย API keys หรือ secrets ในโค้ด
- [ ] ตั้งค่า HTTPS redirect (http → https อัตโนมัติ)
- [ ] เพิ่ม CAPTCHA ถ้ามี spam ใน Contact Form

---

## 📞 Support

หากมีปัญหาในการ Deploy:
- GitHub Issues: สร้าง issue ใน repository
- Email: franchise@oth724.com
- เอกสารเพิ่มเติม: 
  - Netlify Docs: https://docs.netlify.com/
  - Vercel Docs: https://vercel.com/docs

---

## 📋 File Structure

```
oth-minimart/
├── index.html           (หน้าหลัก)
├── privacy-policy.html  (นโยบายความเป็นส่วนตัว)
├── terms.html          (ข้อกำหนด)
├── styles.css          (สไตล์ทั้งหมด)
├── sitemap.xml         (Sitemap สำหรับ Google)
├── robots.txt          (คำแนะนำสำหรับ search bots)
├── package.json        (NPM config สำหรับ dev server)
├── public/
│   └── images/         (รูปภาพทั้งหมด)
│       ├── Alipay.png
│       ├── promptpay.png
│       ├── bcelone.png
│       ├── jcb.png
│       ├── logobcel.png
│       ├── lbd.png
│       ├── apb.png
│       ├── favicon-32x32.png     (ต้องสร้าง)
│       ├── favicon-16x16.png     (ต้องสร้าง)
│       ├── apple-touch-icon.png  (ต้องสร้าง)
│       ├── og-image.jpg          (ต้องสร้าง)
│       └── logo.png              (ต้องสร้าง)
└── README.md           (ไฟล์นี้)
```

---

**สร้างโดย:** GitHub Copilot  
**วันที่:** 10 มิถุนายน 2568  
**เวอร์ชัน:** 1.0
