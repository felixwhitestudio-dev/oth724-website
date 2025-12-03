# ✅ Production Checklist สำหรับ OTH 7/24

## 📋 สิ่งที่ทำเสร็จแล้ว (Completed)

### ✅ 1. Website Structure
- [x] หน้าหลัก (index.html) พร้อมทุก section
- [x] Privacy Policy page (privacy-policy.html)
- [x] Terms & Conditions page (terms.html)
- [x] Responsive design สำหรับทุกหน้าจอ
- [x] Navigation และ smooth scrolling

### ✅ 2. SEO Optimization
- [x] Meta description และ keywords
- [x] Open Graph tags (Facebook sharing)
- [x] Twitter Cards
- [x] Schema.org structured data (JSON-LD)
- [x] Sitemap.xml
- [x] Robots.txt
- [x] Semantic HTML5

### ✅ 3. Contact Form
- [x] Form HTML structure
- [x] JavaScript validation
- [x] Success/Error messages
- [x] Formspree integration ready (ต้องแก้ไข Form ID)
- [x] Email field (_replyto)
- [x] Hidden fields (_subject, _next)

### ✅ 4. Analytics
- [x] Google Analytics code (ต้องแก้ไข GA ID)
- [x] Facebook Pixel code (ต้องแก้ไข Pixel ID)
- [x] Event tracking ready

### ✅ 5. Content
- [x] Hero section พร้อมรูปภาพและข้อความ
- [x] Bestsellers section (4 สินค้า)
- [x] Services section
- [x] Payment methods display (9 ช่องทาง)
- [x] Franchise information
- [x] Products section
- [x] Branches section
- [x] About section
- [x] Contact information

### ✅ 6. Branding
- [x] โลโก้ OTH 7/24 (สีเขียว + ทอง)
- [x] Color scheme สอดคล้องตลอด
- [x] Typography สไตล์มินิมอล
- [x] Payment logos ครบทุกธนาคาร

### ✅ 7. Documentation
- [x] README.md (คู่มือโปรเจค)
- [x] DEPLOY.md (คู่มือการ deploy)
- [x] CHECKLIST.md (ไฟล์นี้)

---

## 🔧 สิ่งที่ต้องทำก่อน Deploy (To-Do)

### 🎨 1. สร้างไฟล์ภาพ (Images)
สร้างไฟล์เหล่านี้และวางใน `public/images/`:

- [ ] **favicon-32x32.png** (32x32 px)
  - ใช้เครื่องมือ: https://realfavicongenerator.net/
  - หรือ Photoshop/Figma export PNG

- [ ] **favicon-16x16.png** (16x16 px)
  - ขนาดเล็กสำหรับ browser tab

- [ ] **apple-touch-icon.png** (180x180 px)
  - ไอคอนสำหรับ iOS/Apple devices

- [ ] **og-image.jpg** (1200x630 px)
  - รูปภาพสำหรับแชร์ Facebook/Twitter
  - ควรมีโลโก้ OTH 7/24 และข้อความหลัก
  - แนะนำ: พื้นสีเขียว #047857, โลโก้สีขาว

- [ ] **logo.png** (แนะนำ 512x512 px หรือใหญ่กว่า)
  - สัญลักษณ์โลโก้สำหรับ Schema.org
  - PNG พื้นหลังโปร่งใส

**เครื่องมือแนะนำ:**
- Canva: https://www.canva.com/ (ทำ og-image ง่าย)
- Figma: https://www.figma.com/ (สำหรับ designer)
- GIMP: https://www.gimp.org/ (ฟรี, เหมือน Photoshop)

---

### 📧 2. Setup Contact Form (Formspree)

**ขั้นตอน:**
1. [ ] ไปที่ https://formspree.io/ และสมัครสมาชิก (ฟรี)
2. [ ] สร้าง Form ใหม่ในระบบ
3. [ ] คัดลอก Form ID ที่ได้ (เช่น `xyzabc123`)
4. [ ] แก้ไขใน `index.html` บรรทัด ~414:

```html
<!-- เปลี่ยนจาก -->
<form id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">

<!-- เป็น (ใส่ Form ID จริง) -->
<form id="contactForm" action="https://formspree.io/f/xyzabc123" method="POST">
```

5. [ ] ทดสอบส่งฟอร์มหลัง deploy
6. [ ] ตั้งค่าอีเมลแจ้งเตือนใน Formspree dashboard

**ทางเลือกอื่น:**
- EmailJS: https://www.emailjs.com/
- SendGrid: https://sendgrid.com/
- เขียน Backend API เอง (Node.js/PHP)

---

### 📊 3. Setup Google Analytics

**ขั้นตอน:**
1. [ ] ไปที่ https://analytics.google.com/
2. [ ] สร้าง Account และ Property ใหม่ (เลือก GA4)
3. [ ] คัดลอก Measurement ID (รูปแบบ: `G-XXXXXXXXXX`)
4. [ ] แก้ไขใน `index.html` บรรทัด ~61 และ ~66:

```html
<!-- เปลี่ยนจาก -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_GA_ID"></script>
gtag('config', 'YOUR_GA_ID');

<!-- เป็น (ใส่ Measurement ID จริง) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
gtag('config', 'G-XXXXXXXXXX');
```

5. [ ] ทดสอบว่า Analytics ทำงานด้วย Real-Time report

---

### 📱 4. Setup Facebook Pixel (Optional)

**ขั้นตอน:**
1. [ ] ไปที่ Facebook Business Manager
2. [ ] สร้าง Pixel ใน Events Manager
3. [ ] คัดลอก Pixel ID
4. [ ] แก้ไขใน `index.html` บรรทัด ~76-78 (ลบ `//` ออก):

```javascript
fbq('init', 'YOUR_PIXEL_ID');  // เปลี่ยนเป็น Pixel ID จริง
fbq('track', 'PageView');
```

5. [ ] ติดตั้ง Facebook Pixel Helper extension เพื่อทดสอบ

**ข้ามได้ถ้า:** ไม่ได้ใช้ Facebook Ads

---

### 🌐 5. Update Domain URLs

**แก้ไขใน 3 ไฟล์:**

#### 5.1 index.html
ค้นหาและแทนที่ `oth724.com` ทั้งหมดด้วยโดเมนจริง:

- [ ] บรรทัด ~18: `<meta property="og:url">`
- [ ] บรรทัด ~20: `<meta property="og:title">`
- [ ] บรรทัด ~23: `<meta property="og:image">`
- [ ] บรรทัด ~28: `<meta property="twitter:url">`
- [ ] บรรทัด ~31: `<meta property="twitter:image">`
- [ ] บรรทัด ~39: `"url": "https://oth724.com"`
- [ ] บรรทัด ~40: `"logo": "https://oth724.com/public/images/logo.png"`

#### 5.2 sitemap.xml
- [ ] แทนที่ `https://www.oth724.com/` ทั้ง 6 บรรทัด

#### 5.3 robots.txt
- [ ] บรรทัด 3: `Sitemap: https://www.oth724.com/sitemap.xml`

**ตัวอย่าง:** ถ้าโดเมนจริงคือ `www.oth-lao.com` ให้แทนที่เป็น:
```html
<meta property="og:url" content="https://www.oth-lao.com/" />
```

---

### 🚀 6. เลือกวิธี Deploy

เลือก 1 วิธีจาก 4 ตัวเลือก:

#### ✅ Option 1: Netlify (แนะนำ - ง่ายที่สุด)
- [ ] สมัครที่ https://www.netlify.com/
- [ ] Drag & Drop โฟลเดอร์ `oth-minimart`
- [ ] ตั้งค่า Custom Domain
- [ ] SSL อัตโนมัติ (Let's Encrypt)

**ข้อดี:** ฟรี, ง่าย, SSL ฟรี, CDN ไว
**ข้อเสี่ย:** -

#### Option 2: Vercel
- [ ] สมัครที่ https://vercel.com/
- [ ] Connect GitHub และ import project
- [ ] Deploy อัตโนมัติ

**ข้อดี:** เร็วมาก, Git integration
**ข้อเสีย:** -

#### Option 3: GitHub Pages
- [ ] Push code ขึ้น GitHub
- [ ] เปิด GitHub Pages ใน Settings
- [ ] URL: `https://username.github.io/oth-minimart/`

**ข้อดี:** ฟรี, เชื่อมกับ Git
**ข้อเสีย:** SSL ต้องตั้งค่าเอง (ถ้าใช้ Custom Domain)

#### Option 4: Traditional Hosting
- [ ] เช่า Hosting (Hostinger, GoDaddy, etc.)
- [ ] Upload ไฟล์ทั้งหมดไปยัง `public_html/`
- [ ] ติดตั้ง SSL Certificate (Let's Encrypt)

**ข้อดี:** ควบคุมเต็มที่
**ข้อเสีย:** ต้องจัดการ server เอง

---

### 🔍 7. Submit to Search Engines

#### Google Search Console
- [ ] ไปที่ https://search.google.com/search-console
- [ ] Add Property (ใส่ URL)
- [ ] Verify ownership (HTML tag หรือ DNS)
- [ ] Submit sitemap: `https://yourdomain.com/sitemap.xml`

#### Bing Webmaster Tools
- [ ] ไปที่ https://www.bing.com/webmasters
- [ ] Add site
- [ ] Submit sitemap

---

### 🧪 8. Testing หลัง Deploy

#### Functionality
- [ ] เปิดเว็บไซต์ทุกหน้า (index, privacy-policy, terms)
- [ ] คลิกทุก navigation link
- [ ] ทดสอบ Contact Form โดยส่งข้อความจริง
- [ ] เช็คอีเมลว่าได้รับข้อความจาก Formspree

#### Mobile & Responsive
- [ ] ทดสอบบน iPhone/Android
- [ ] ทดสอบบน Tablet
- [ ] ทดสอบบน Desktop (ขนาดหน้าจอต่างๆ)
- [ ] ใช้ Chrome DevTools → Responsive mode

#### Performance
- [ ] ทดสอบความเร็วที่ https://pagespeed.web.dev/
- [ ] เป้าหมาย: Performance Score > 90
- [ ] ตรวจสอบ First Contentful Paint < 2s

#### Security
- [ ] ตรวจสอบว่ามี 🔒 (HTTPS) ใน URL bar
- [ ] ทดสอบที่ https://www.ssllabs.com/ssltest/
- [ ] เป้าหมาย: Grade A

#### SEO
- [ ] ทดสอบที่ https://search.google.com/test/mobile-friendly
- [ ] ตรวจสอบ Rich Results: https://search.google.com/test/rich-results

#### Social Sharing
- [ ] Facebook Debugger: https://developers.facebook.com/tools/debug/
  - [ ] ตรวจสอบ og:image แสดงถูกต้อง
  - [ ] ตรวจสอบ title และ description
- [ ] Twitter Card Validator: https://cards-validator.twitter.com/
  - [ ] ตรวจสอบ twitter:image แสดงถูกต้อง

#### Analytics
- [ ] เปิด Google Analytics Real-Time report
- [ ] เข้าเว็บไซต์และดูว่ามี Active User
- [ ] ตรวจสอบ Page Views

---

## 📅 Post-Launch Maintenance

### ประจำสัปดาห์ (Weekly)
- [ ] เช็ค Google Analytics (traffic, sources)
- [ ] ตรวจสอบข้อความจาก Contact Form
- [ ] Monitor uptime (ใช้ UptimeRobot.com ฟรี)

### ประจำเดือน (Monthly)
- [ ] อัพเดทเนื้อหาหรือโปรโมชัน
- [ ] เช็ค Google Search Console (keywords, errors)
- [ ] Backup website files
- [ ] ตรวจสอบ broken links

### ประจำไตรมาส (Quarterly)
- [ ] Review และอัพเดท Privacy Policy
- [ ] เช็ค SSL certificate expiry
- [ ] วิเคราะห์ SEO performance
- [ ] ปรับปรุง content based on analytics

---

## 🎯 Success Metrics

### เป้าหมายเดือนแรก:
- [ ] Website uptime > 99.5%
- [ ] Page load time < 3 seconds
- [ ] Google PageSpeed Score > 85
- [ ] 0 broken links
- [ ] ได้รับ Contact Form submissions อย่างน้อย 5 ครั้ง

### เป้าหมาย 3 เดือน:
- [ ] Google index > 10 pages
- [ ] Organic traffic > 100 visits/month
- [ ] Conversion rate > 2% (contact form)
- [ ] Bounce rate < 60%

---

## 🆘 Troubleshooting

### Contact Form ไม่ทำงาน
- ตรวจสอบ Form ID ถูกต้อง
- เช็ค Network tab ใน DevTools (F12)
- ดูว่า Formspree ได้รับ request หรือไม่

### Analytics ไม่แสดงข้อมูล
- รอ 24-48 ชั่วโมงหลัง setup
- ใช้ Real-Time report เพื่อทดสอบทันที
- ตรวจสอบ GA Measurement ID ถูกต้อง

### SSL Error
- รอ propagation (อาจใช้เวลา 24-48 ชั่วโมง)
- ตรวจสอบ DNS settings
- ใช้ Let's Encrypt ผ่าน hosting control panel

### Images ไม่แสดง
- ตรวจสอบ path: ต้องเป็น `public/images/filename.png`
- เช็ค file permissions (644 for files, 755 for folders)
- ดูใน Network tab (F12) ว่า request error หรือไม่

---

## 📞 Support Contacts

- **Technical Issues:** franchise@oth724.com
- **Netlify Support:** https://docs.netlify.com/
- **Vercel Support:** https://vercel.com/docs
- **Formspree Support:** https://formspree.io/help

---

**Last Updated:** 10 มิถุนายน 2568  
**Version:** 1.0  
**Status:** Ready for Production ✅
