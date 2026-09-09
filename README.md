# วิธีนำเว็บไซต์ E-Portfolio ขึ้น Netlify

โฟลเดอร์นี้คือโปรเจกต์เว็บไซต์ที่พร้อมสำหรับ deploy ขึ้น Netlify แล้ว

## วิธีที่ 1: ผ่าน GitHub (แนะนำ ทำครั้งเดียว อัปเดตง่ายในอนาคต)

1. สร้างบัญชี GitHub (ถ้ายังไม่มี) ที่ https://github.com
2. สร้าง repository ใหม่ (New repository) เช่นชื่อ `pa-portfolio`
3. อัปโหลดไฟล์ทั้งหมดในโฟลเดอร์นี้เข้า repository นั้น (ลาก-วางไฟล์ผ่านหน้าเว็บ GitHub ได้เลย ไม่ต้องใช้คำสั่ง)
4. ไปที่ https://app.netlify.com แล้วสมัคร/ล็อกอิน (สมัครด้วยบัญชี GitHub ได้เลย สะดวกสุด)
5. กด "Add new site" > "Import an existing project" > เลือก GitHub > เลือก repository `pa-portfolio`
6. Netlify จะตรวจพบไฟล์ `netlify.toml` และตั้งค่า build ให้อัตโนมัติ (Build command: `npm run build`, Publish directory: `dist`)
7. กด "Deploy site" รอสักครู่ เว็บไซต์จะขึ้นออนไลน์พร้อมลิงก์ให้ใช้งานทันที (เช่น `your-site-name.netlify.app`)
8. ครั้งต่อไปถ้าอยากแก้ไขเนื้อหา แค่แก้ไฟล์ใน GitHub แล้ว Netlify จะ build ให้ใหม่อัตโนมัติ

## วิธีที่ 2: ลาก-วางไฟล์ (เร็วกว่า แต่ต้องมี Node.js ในเครื่องคอมพิวเตอร์)

1. ติดตั้ง Node.js จาก https://nodejs.org (ถ้ายังไม่มี)
2. เปิดโฟลเดอร์นี้ด้วย Terminal / Command Prompt แล้วรันคำสั่ง:
   ```
   npm install
   npm run build
   ```
3. จะได้โฟลเดอร์ชื่อ `dist` เกิดขึ้นมา
4. ไปที่ https://app.netlify.com/drop แล้วลากโฟลเดอร์ `dist` ไปวาง
5. เว็บไซต์จะขึ้นออนไลน์ทันที พร้อมลิงก์ให้ใช้งาน

## หมายเหตุ

- เว็บไซต์นี้เป็น React + Vite ใช้ไอคอนจากไลบรารี `lucide-react`
- ภาพทั้งหมด (ภาพปก, เกียรติบัตร, รูปโปรไฟล์ ฯลฯ) ถูกฝังอยู่ในโค้ดโดยตรง (base64) จึงไม่ต้องอัปโหลดไฟล์ภาพแยก
- หากต้องการแก้ไขเนื้อหา (ชื่อ, ข้อมูล PA, เกียรติบัตร) แก้ไขได้ที่ไฟล์ `src/App.jsx`
