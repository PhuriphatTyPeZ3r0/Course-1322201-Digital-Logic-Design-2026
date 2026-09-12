---
tags: [dld, week4, assignment]
course: 1322201
week: 4
date: 2026-09-08
source: "4. แผนผังคาโนห์ 2568.pdf"
---

# แบบฝึกหัดสัปดาห์ 4

<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week4-MOC|MOC สัปดาห์ 4]]

> [!warning] หมายเหตุ
> ข้อ 4.5 (ในหัวข้อ 4 ตัวแปร) มีสมการยาวและหนาแน่นมาก แนะนำให้เปิดไฟล์ต้นฉบับ `01_Lectures/02_Teaching_Slides/4. แผนผังคาโนห์ 2568.pdf` หน้า 31 ประกอบเทียบเคียงก่อนลงมือทำ เพื่อความชัวร์เรื่องตำแหน่งขีดบน (complement)

## Assignment 4.1 — ลดรูปด้วย K-Map 2 ตัวแปร แบบ Minterm (อ้างอิง [[Kmap-Grouping-Rules]])

1. AB̄ + AB
2. ĀB̄ + AB̄
3. AB̄ + AB + ĀB
4. ĀB̄ + ĀB + AB

## Assignment 4.2 — ลดรูปด้วย K-Map 2 ตัวแปร แบบ Maxterm (อ้างอิง [[Kmap-Grouping-Rules]])

1. (A+B̄)(Ā+B̄)
2. (A+B)(A+B̄)
3. (Ā+B)(Ā+B̄)
4. (A+B)(Ā+B)(Ā+B̄)

## Assignment 4.3 — ลดรูปด้วย K-Map 3 ตัวแปร (อ้างอิง [[Kmap-Grouping-Rules]])

1. f(A,B,C) = ΣM(1,3,6,7)
2. f(A,B,C) = ΣM(0,3,5,6,7)
3. f(A,B,C) = πM(0,2,5,6,7)
4. f(A,B,C) = πM(1,2,5,6)

## Assignment 4.4 — ลดรูปด้วย K-Map 4 ตัวแปร แบบ ΣM/πM (อ้างอิง [[Kmap-Grouping-Rules]])

1. f(A,B,C,D) = ΣM(1,3,4,6,9,11,12,14)
2. f(A,B,C,D) = πM(0,2,4,5,6,7,12,13,14,15)

## Assignment 4.5 — ลดรูปด้วย K-Map 4 ตัวแปร แบบสมการ SOP/POS (อ้างอิง [[Kmap-Grouping-Rules]])

1. f(A,B,C,D) = Ā·C + A·C·D + B̄·D + A·B·C̄·D
2. f(A,B,C,D) = C·(C+D̄)·(A+B̄+D)·(Ā+B+C+D̄)
3. โจทย์เพิ่มเติมอีก 1 ข้อในสไลด์หน้า 31 (สมการ SOP 6 พจน์ 4 ตัวแปร) — ดูจากไฟล์ต้นฉบับโดยตรงตามหมายเหตุด้านบน

---
<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week4-MOC|MOC สัปดาห์ 4]]
