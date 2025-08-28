# 📚 KMITL CS Department Special Problem Web Catalog

โครงงานนี้เป็นส่วนหนึ่งของการศึกษาระดับปริญญาตรี สาขาวิทยาการคอมพิวเตอร์ คณะวิทยาศาสตร์  
สถาบันเทคโนโลยีพระจอมเกล้าเจ้าคุณทหารลาดกระบัง (KMITL) ปีการศึกษา 2567  

---

## 📖 Project Overview
เว็บแอปพลิเคชันนี้ถูกพัฒนาขึ้นเพื่อจัดเก็บและสืบค้น โครงงานปัญหาพิเศษ (Special Problem) ของภาควิชาวิทยาการคอมพิวเตอร์ โดยเน้นไปที่การ สกัดข้อมูล จากไฟล์ PDF ภาษาไทย เช่น  
- ชื่อหัวข้อโครงงาน (ไทย/อังกฤษ)  
- ชื่อนักศึกษาและรหัส  
- อาจารย์ที่ปรึกษา  
- คณะ / ภาควิชา / ปีการศึกษา  
- บทคัดย่อ (ไทย/อังกฤษ)  
- คำสำคัญ (Keywords)  

เนื่องจากการทำ OCR ภาษาไทยยังมีข้อจำกัด ผู้พัฒนาได้ทำ **Fine-tune PyTesseract** โดยใช้ชุดข้อมูลภาษาไทย (เช่น `pythainlp/thaisum`) และไลบรารีเสริม เช่น **Leptonica, Poppler, PangoCairo** เพื่อเพิ่มความแม่นยำในการสกัดข้อความจาก ไฟล์ PDF  

---

## 🎯 Objectives
1. พัฒนาโมเดล OCR สำหรับภาษาไทยเพื่อเพิ่มความแม่นยำของ PyTesseract  
2. ออกแบบและพัฒนาเว็บแอปพลิเคชันสำหรับสกัดข้อมูลจาก PDF โดยอัตโนมัติ  
3. จัดเก็บข้อมูลโครงงานให้มีความถูกต้องและเป็นระบบเพื่อรองรับการสืบค้น  

---

## 🛠 Tech Stack
- Backend: Flask, SQLAlchemy  
- Database: MySQL / SQLite  
- OCR & Data Processing:PyTesseract, Leptonica, Poppler, PangoCairo  
- Frontend: HTML, CSS, JavaScript (Bootstrap)  
- Tools: Postman (API Testing), Regular Expression  

---

## ⚙️ System Features
- 🔍 Search & View: ค้นหาและดูรายละเอียดโครงงาน  
- ⬇️ Download PDF: ดาวน์โหลดไฟล์โครงงานปัญหาพิเศษ  
- 👩‍🎓 Student/User System:  
  - นักศึกษา → อัปโหลดโครงงาน / แก้ไขข้อมูลโครงงาน  
  - ผู้ดูแลระบบ (Admin) → จัดการข้อมูล, ลบโครงงาน, ดูรายการคำผิด  
- 📝 Error Correction Tool: ฟีเจอร์แก้ไขคำผิดที่สกัดได้จาก OCR ก่อนบันทึกเข้าสู่ระบบ  
- 📊 Database Design: ออกแบบด้วย ER-Diagram และตารางเชื่อมโยง (Projects, Students, Keywords, PDF files, Corrections)

---

## 📊 Results
จากการทดสอบโมเดล OCR ที่ Fine-tuned:  
- Word Error Rate (WER): 5.028%  
- Character Error Rate (CER): 1.778%

ช่วยให้การสกัดข้อมูลจาก PDF มีความแม่นยำสูงขึ้น และลดเวลาการกรอกข้อมูลด้วยตนเอง แม้ยังมีข้อจำกัดที่ต้องให้ผู้ใช้ตรวจสอบข้อมูลอีกครั้งก่อนบันทึก 

---

## 🚀 How to Use
1. Clone repository และติดตั้ง dependencies  
2. ตั้งค่าฐานข้อมูลด้วย SQLAlchemy  
3. รัน Flask server  
   ```bash
   python app.py
