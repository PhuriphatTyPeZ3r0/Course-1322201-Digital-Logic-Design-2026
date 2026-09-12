---
tags: [dld, week2, moc]
course: 1322201
course-name: Digital Logic Design (การออกแบบดิจิทัลลอจิก)
week: 2
date: 2026-09-07
instructor: ผศ.ดร. ติณณภพ ดินดำ (Tinnaphob Dindam, Ph.D.)
source: "2.  Digital IC  Logic Gates 2568.pdf"
---

# Week 2 — IC & Logic Gates (MOC)

<span class="material-symbols-outlined">arrow_back</span> สัปดาห์ก่อนหน้า: [[Week1-MOC|MOC สัปดาห์ 1]]

## <span class="material-symbols-outlined">check_circle</span> เช็คลิสต์ก่อนเข้าเรียน

- [ ] ทบทวนความหมาย HIGH/LOW และ Positive/Negative Logic — ดู [[Logic-Gates]]
- [ ] จำสัญลักษณ์เกตพื้นฐานทั้ง 8 ตัวให้ได้ (Buffer, NOT, AND, OR, NAND, NOR, XOR, XNOR) พร้อมสมการและตารางความจริง
- [ ] เข้าใจความแตกต่าง TTL vs CMOS คร่าวๆ (ความเร็ว, กำลังไฟฟ้า, แรงดันเลี้ยง) — ดู [[IC-Basics]]
- [ ] ฝึกเขียนวงจรลอจิกจากสมการบูลีน (จากสัปดาห์ก่อนที่ทบทวน Complement/Boolean มา)
- [ ] ทบทวนวิธีเขียนสมการจากตารางความจริงทั้ง 2 แบบ คือ Minterm (SOP) และ Maxterm (POS) — ดู [[SOP-POS-Minterm-Maxterm]]
- [ ] ลองทำแบบฝึกหัด Assignment 2.1 ล่วงหน้า (เขียนวงจรจากสมการ) — ดู [[Week2-Assignments]]

## <span class="material-symbols-outlined">assignment</span> ภาพรวมสัปดาห์ 2 (สรุปย่อ)

หัวข้อหลักของสัปดาห์นี้ต่อยอดจากท้ายสไลด์สัปดาห์ 1 (IC เกต 74HC04/74HC32) เข้าสู่เนื้อหา **ไอซีดิจิตอลและลอจิกเกต** อย่างเต็มรูปแบบ ครอบคลุม 3 ส่วนหลัก:

1. **โครงสร้างไอซี** — SSI/MSI/LSI/VLSI และความแตกต่าง TTL vs CMOS
2. **ลอจิกเกตพื้นฐาน 8 ตัว** — Buffer, NOT, AND, OR, NAND, NOR, XOR, XNOR พร้อมสมการบูลีนและตารางความจริง
3. **การแปลงตารางความจริงเป็นสมการ** — Minterm/Sum of Product (SOP) และ Maxterm/Product of Sum (POS) พร้อมการพิสูจน์ด้วยเวนไดอะแกรม

## <span class="material-symbols-outlined">map</span> แผนที่หัวข้อสัปดาห์ 2

```mermaid
graph TD
    MOC[Week 2: IC & Logic Gates] --> A[[IC-Basics]]
    MOC --> B[[Logic-Gates]]
    MOC --> C[[SOP-POS-Minterm-Maxterm]]
    MOC --> D[[Week2-Assignments]]

    A --> A1[SSI/MSI/LSI/VLSI]
    A --> A2[TTL vs CMOS]
    A --> A3[Fan Out / Noise Margin]

    B --> B1[Buffer / NOT]
    B --> B2[AND / OR]
    B --> B3[NAND / NOR]
    B --> B4[XOR / XNOR]
    B --> B5[ความสัมพันธ์ระหว่างเกต]

    C --> C1[Minterm / SOP]
    C --> C2[Maxterm / POS]
    C --> C3[Venn Diagram พิสูจน์เอกลักษณ์]

    style MOC fill:#2b6cb0,color:#fff
    style A fill:#38a169,color:#fff
    style B fill:#dd6b20,color:#fff
    style C fill:#805ad5,color:#fff
    style D fill:#718096,color:#fff
```

## <span class="material-symbols-outlined">collections_bookmark</span> โน้ตรายหัวข้อ

| หัวข้อ | เนื้อหาหลัก | หน้าสไลด์ |
|---|---|---|
| [[IC-Basics]] | Analog vs Digital, IC (SSI/MSI/LSI/VLSI), TTL vs CMOS, Fan Out, Noise Margin | 1-8 |
| [[Logic-Gates]] | เครื่องหมายสมการลอจิก, Truth Table, เกตพื้นฐาน 8 ตัว, ความสัมพันธ์ระหว่างเกต, ตัวอย่างวิเคราะห์วงจร | 9-21, 26 |
| [[SOP-POS-Minterm-Maxterm]] | Minterm/SOP, Maxterm/POS, Venn Diagram | 27-40 |
| [[Week2-Assignments]] | Assignment 2.1 (สมการ→วงจร), 2.2 (วงจร→ฟังก์ชัน), 2.3 (ตารางความจริง→สมการ) | 25, 27, 41-42 |

> [!tip] จุดที่มักสับสน
> - **NAND ≠ NOT-AND ต่อกันแบบสุ่ม** — NAND คือ AND ตามด้วย NOT เสมอ (ไม่ใช่ NOT ก่อนแล้ว AND)
> - **Minterm ดูแถวที่ output = 1**, **Maxterm ดูแถวที่ output = 0** — สลับกันบ่อยเวลาแปลงตัวแปรเป็นบาร์/ไม่บาร์
> - Minterm: ค่า 1 → ตัวแปรปกติ, ค่า 0 → มีบาร์ | Maxterm: ค่า 0 → ตัวแปรปกติ, ค่า 1 → มีบาร์ (**กลับกันกับ Minterm**)

<span class="material-symbols-outlined">arrow_forward</span> สัปดาห์ถัดไป: [[Week3-MOC|MOC สัปดาห์ 3]]
