---
tags: [dld, week3, boolean-algebra]
course: 1322201
week: 3
date: 2026-09-08
---

# กฎการสลับที่ รวมหมู่ และกระจาย (Commutative, Associative, Distributive Law)

<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week3-MOC|MOC สัปดาห์ 3]] | ก่อนหน้า: [[Boolean-Algebra-Basics]]

## <span class="material-symbols-outlined">key</span> Keyword

- **กฎการสลับที่ (Commutative Law)** — สลับตำแหน่งตัวแปรได้ ผลลัพธ์เหมือนเดิม
- **กฎการรวมหมู่ (Associative Law)** — จัดกลุ่มวงเล็บใหม่ได้ ผลลัพธ์เหมือนเดิม (ต้องเป็นตัวกระทำชนิดเดียวกันทั้งหมด)
- **กฎการกระจาย (Distributive Law)** — มี 4 รูปแบบ บางรูปเหมือนพีชคณิตทั่วไป บางรูปไม่มีในคณิตศาสตร์ปกติ

## <span class="material-symbols-outlined">menu_book</span> Theory (เข้าใจง่าย)

### กฎการสลับที่ (Commutative Law)

A+B = B+A และ A·B = B·A — พิสูจน์ได้ตรงจากวงจร OR/AND ที่สลับขาอินพุตแล้ว output ค่าเดิม

### กฎการรวมหมู่ (Associative Law)

(A+B)+C = A+(B+C) และ (A·B)·C = A·(B·C) — จัดกลุ่มวงเล็บของเกตชนิดเดียวกันใหม่ได้โดยไม่กระทบผลลัพธ์

### กฎการกระจาย (Distributive Law) — 4 รูปแบบ (พิสูจน์ด้วยตารางความจริงเท่านั้น)

1. **A + ĀB = A + B**
2. **Ā + AB = Ā + B**
3. **A(B+C) = AB + AC** (กระจายคูณเข้าวงเล็บ เหมือนพีชคณิตทั่วไป)
4. **A + BC = (A+B)(A+C)** (รูปนี้ไม่มีในพีชคณิตจำนวนจริง)

> [!important] ข้อ 1, 2 และ 4 ไม่ใช่สามัญสำนึกทางคณิตศาสตร์ปกติ
> ต่างจากพีชคณิตจำนวนจริงที่คุ้นเคย ต้องพิสูจน์ด้วยตารางความจริง (truth table) เท่านั้นถึงจะเชื่อได้ ไม่สามารถ "มองออก" ได้ทันทีเหมือนข้อ 3

**ตัวอย่างการพิสูจน์ด้วยตารางความจริง (ข้อ 1: A+ĀB=A+B):**

| A | B | Ā | ĀB | A+ĀB | A+B |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 | 1 | 1 |

คอลัมน์ A+ĀB กับ A+B ตรงกันทุกแถว → พิสูจน์ว่าเท่ากันจริง (ข้ออื่นพิสูจน์ด้วยวิธีเดียวกัน คือสร้างตารางความจริงแล้วเทียบคอลัมน์)

### ตารางสรุปทฤษฎีบทพีชคณิตบูลีนทั้งหมด (10 ทฤษฎีบท)

| # | ชื่อทฤษฎีบท | สมการ |
| --- | --- | --- |
| 1 | Commutative | A+B=B+A, A·B=B·A |
| 2 | Associative | A+(B+C)=(A+B)+C, A·(B·C)=(A·B)·C |
| 3 | Distributive | A+(B·C)=(A+B)·(A+C), A·(B+C)=A·B+A·C |
| 4 | Identity | A+A=A, A·A=A |
| 5 | Negation | Ā (นิยามคอมพลีเมนต์), A̿=A (นอตซ้อน 2 ครั้ง) |
| 6 | Redundancy | A+A·B=A, A·(A+B)=A |
| 7 | — | 0+A=A, 1·A=A, 1+A=1, 0·A=0 |
| 8 | — | Ā+A=1, Ā·A=0 |
| 9 | — | A+ĀB=A+B, A·(Ā+B)=A·B |
| 10 | De Morgan's Theorem | (A+B)‾=Ā·B̄, (A·B)‾=Ā+B̄ |

> [!note] ตารางนี้ครอบคลุมกฎจาก [[Boolean-Algebra-Basics]] (ทฤษฎีบท 4, 5, 7, 8) และ [[DeMorgans-Theorem]] (ทฤษฎีบท 10) ด้วย ใช้เป็นสรุปรวมทั้งหมดได้เลย

---
<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[Boolean-Algebra-Simplification]]
