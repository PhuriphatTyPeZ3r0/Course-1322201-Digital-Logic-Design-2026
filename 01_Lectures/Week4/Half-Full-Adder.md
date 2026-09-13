---
tags: [dld, week4, kmap, adder]
course: 1322201
week: 4
date: 2026-09-08
---

# วงจรบวกเลขฐานสอง: Half Adder และ Full Adder

<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week4-MOC|MOC สัปดาห์ 4]] | ก่อนหน้า: [[Kmap-Dont-Care-Conditions]]

## <span class="material-symbols-outlined">key</span> Keyword

- **Half Adder (วงจรบวกแบบไม่คิดตัวทด)** — บวกอินพุต 1 บิต 2 ตัว (A, B) โดยไม่มีตัวทดจากบิตก่อนหน้าเข้ามาเกี่ยว
- **Full Adder (วงจรบวกแบบคิดตัวทด)** — บวกอินพุต 1 บิต 2 ตัว **พร้อมตัวทดขาเข้า (Carry_in)** รวมเป็น 3 อินพุต
- **Sum** — ผลบวก, **Carry / Carry_out** — ตัวทดไปบิตถัดไป

## <span class="material-symbols-outlined">menu_book</span> Theory (เข้าใจง่าย)

วงจรบวก/ลบเลขฐานสอง คือวงจรที่นำอินพุต 2 ตัวขนาด 1 บิตที่มีลำดับความสำคัญเท่ากัน มาบวก/ลบกัน แบ่งเป็น 4 วงจร: Half Adder, Full Adder, Half Subtractor, Full Subtractor (2 วงจรแรกอยู่ในไฟล์นี้ อีก 2 วงจรอยู่ที่ [[Half-Full-Subtractor]])

### 1. Half Adder — วงจรบวกแบบไม่คิดตัวทด

ใช้บวกบิตที่มีลำดับความสำคัญ**ต่ำที่สุด** (LSB) เท่านั้น เพราะบิตนี้ไม่มีบิตอื่นที่ต่ำกว่ามาทดเข้ามา อินพุต A, B (1 บิต) → เอาต์พุต Sum และ Carry

| A | B | Sum | Carry |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

**สมการจาก K-Map:**
$$S = \bar{A}B + A\bar{B} = A \oplus B \qquad C = AB$$

วงจร: **Sum ใช้ XOR gate 1 ตัว**, **Carry ใช้ AND gate 1 ตัว** เท่านั้น — ง่ายที่สุดในบรรดา 4 วงจร

### 2. Full Adder — วงจรบวกแบบคิดตัวทด

ใช้บวกบิตที่**ไม่ใช่ LSB** เพราะต้องรับตัวทด (Carry_in) จากบิตที่ต่ำกว่ามาบวกร่วมด้วย รวมเป็น 3 อินพุต (A, B, Carry_in) → เอาต์พุต Sum และ Carry_out

| A | B | Carry_in | Sum | Carry_out |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

**สมการจาก K-Map:**
$$S = A \oplus B \oplus C_{in} \qquad C_{out} = AB + AC_{in} + BC_{in}$$

วงจร: **Sum ใช้ XOR gate 2 ตัวต่อกัน** (A⊕B ก่อน แล้วเอาผลไป XOR กับ Carry_in), **Carry_out ใช้ AND gate 3 ตัว + OR gate 1 ตัว** (จับคู่อินพุตทีละคู่ AND กันแล้วรวมด้วย OR)

> [!tip] จุดสังเกต
> Full Adder ต่างจาก Half Adder แค่ตรงที่**มีตัวทดขาเข้าเพิ่มมา 1 เส้น** — ทุกบิตของการบวกจริง (ยกเว้นบิตแรกสุด) ต้องใช้ Full Adder เพราะต้องรับตัวทดจากบิตก่อนหน้าเสมอ

## <span class="material-symbols-outlined">schema</span> Diagram

```mermaid
flowchart TD
    Start((●)) --> DefInputs([กำหนดสัญญาณอินพุตของวงจร<br>Half Adder: A, B | Full Adder: A, B, C_in])
    DefInputs --> TruthTable([สร้างตารางค่าความจริงของ Sum และ Carry<br>Construct Truth Table])
    TruthTable --> PlotKMap([พลอตค่า Sum และ Carry ลงตาราง K-Map แยกตาราง<br>Plot K-Maps for Outputs])
    PlotKMap --> GroupCells([จับกลุ่มช่อง 1 ตามกฎ K-Map เพื่อลดรูป<br>Group Minterms])
    GroupCells --> DerivEq([สกัดสมการลอจิก Sum และ Carry_out<br>Derive Minimized Equations])
    DerivEq --> DrawCircuit([วาดวงจรเกตดิจิทัลตามสมการ<br>Implement Logic Circuit])
    DrawCircuit --> EndNode(((●)))
```

---
<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[Half-Full-Subtractor]]
