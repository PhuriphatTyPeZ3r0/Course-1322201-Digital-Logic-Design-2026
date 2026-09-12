# 1322201 Digital Logic Design (การออกแบบดิจิทัลลอจิก)

คลังสรุปเนื้อหา แบบฝึกหัด และโปรเจกต์รายวิชา **1322201 การออกแบบดิจิทัลลอจิก (Digital Logic Design)**  
สถาบันการจัดการปัญญาภิวัฒน์ (PIM) — ภาคการศึกษา 1/2569

---

## <span class="material-symbols-outlined">push_pin</span> ข้อมูลรายวิชาเบื้องต้น

- **อาจารย์ผู้สอน:** ผศ.ดร. ติณณภพ ดินดำ (Tinnaphob Dindam, Ph.D.)
- **ตารางเรียน:** วันจันทร์ 09:30–12:30 น. และ 14:00–17:00 น. (6 ชม./สัปดาห์)
- **ห้องเรียน:** Electronic & Digital Lab (C)
- **ช่วงเวลา:** 07/09/2569 – 15/11/2569
- **ช่องทางหลัก:** PIM e-Learning

### <span class="material-symbols-outlined">ads_click</span> เกณฑ์การประเมินผล
| สัดส่วนคะแนน | รายละเอียด |
|---|---|
| **10%** | การเข้าชั้นเรียน / ความตรงต่อเวลา |
| **15%** | งานค้นคว้าหัวข้อที่มอบหมายและการบ้าน |
| **30%** | สอบกลางภาค (Midterm Exam) |
| **15%** | สอบปฏิบัติการ (Final Lab Test) |
| **30%** | สอบปลายภาค (Final Exam) |

---

## <span class="material-symbols-outlined">folder_copy</span> โครงสร้าง Repository (Project Structure)

```text
01_1322201_Digital-Logic-Design/
├── 01_Lectures/
│   ├── 01_Docs/              # เอกสารและตำราประกอบการสอน (Ignored in Git)
│   ├── 02_Teaching_Slides/   # สไลด์ประกอบการสอนประจำสัปดาห์ (Ignored in Git)
│   └── Week1/                # โน้ตสรุปเนื้อหาบรรยายสัปดาห์ที่ 1 (Markdown / Obsidian)
├── 02_Labs_Assignments/      # ใบงาน แบบฝึกหัด และโค้ดแล็บ (VHDL/Verilog/Circuit)
├── 03_Projects/              # โครงงานและโปรเจกต์ประจำวิชา
├── 04_Exams_Review/          # แนวข้อสอบ สรุปทบทวนก่อนสอบกลางภาคและปลายภาค
└── README.md                 # เอกสารแนะนำและสารบัญหลัก
```

---

## <span class="material-symbols-outlined">menu_book</span> สารบัญสรุปเนื้อหาบรรยาย (Lecture Notes Index)

### <span class="material-symbols-outlined">label</span> [Week 1: Number System & Codes](01_Lectures/Week1/Week1-MOC.md)
แผนที่ความรู้สรุปภาพรวมและเช็คลิสต์ประจำสัปดาห์ที่ 1

- [x] **[Course-Intro](01_Lectures/Week1/Course-Intro.md)** — ปฐมนิเทศรายวิชา, เกณฑ์คะแนน, และโครงสร้างเนื้อหา
- [x] **[Number-System-Basics](01_Lectures/Week1/Number-System-Basics.md)** — ระบบตัวเลขฐาน 10, 2, 8, 16 และ Positional Form
- [x] **[Base-Conversion](01_Lectures/Week1/Base-Conversion.md)** — วิธีแปลงฐานตัวเลข $(10 \leftrightarrow 2, 8, 16)$ และ $(2 \leftrightarrow 8 \leftrightarrow 16)$
- [x] **[Binary-Arithmetic](01_Lectures/Week1/Binary-Arithmetic.md)** — การบวกและลบเลขฐานสอง (พร้อมตัวทด Carry และขอยืม Borrow)
- [x] **[Complements](01_Lectures/Week1/Complements.md)** — ระบบคอมพลีเมนต์ ($r$'s and $(r-1)$'s complement) และการลบด้วยการบวก
- [x] **[Binary-Multiply-Divide](01_Lectures/Week1/Binary-Multiply-Divide.md)** — การคูณและการหารเลขฐานสอง
- [x] **[Codes-BCD](01_Lectures/Week1/Codes-BCD.md)** — รหัส BCD (8421) และการบวกเลข BCD
- [x] **[Excess3-Gray-Code](01_Lectures/Week1/Excess3-Gray-Code.md)** — รหัสเกิน 3 (Excess-3) และรหัสเกรย์ (Gray Code)
- [x] **[Error-Detect-Correct](01_Lectures/Week1/Error-Detect-Correct.md)** — การตรวจจับและแก้ไขข้อผิดพลาด (Parity Bit & Hamming Code)
- [x] **[ASCII-Code](01_Lectures/Week1/ASCII-Code.md)** — รหัสแอสกี (ASCII Code) และการแทนค่าอักขระ

---

## <span class="material-symbols-outlined">lightbulb</span> วิธีการใช้งาน (How to Use)

- **เปิดอ่านผ่าน GitHub:** สามารถคลิกลิงก์ Markdown ด้านบนเพื่ออ่านเนื้อหาและสูตรคำนวณผ่าน GitHub ได้ทันที
- **เปิดผ่าน Obsidian:** สามารถเปิดโฟลเดอร์นี้เป็น Obsidian Vault ได้ทันที รองรับ Wikilinks, MathJax ($...$), Callouts (`> [!info]`), และ Mermaid Diagrams
