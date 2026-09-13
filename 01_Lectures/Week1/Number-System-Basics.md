---
tags: [dld, week1, number-system]
course: 1322201
week: 1
date: 2026-09-07
---

# ระบบเลขฐาน (Number System) — พื้นฐาน

<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week1-MOC|MOC สัปดาห์ 1]] | ก่อนหน้า: [[Course-Intro]]

## <span class="material-symbols-outlined">key</span> Keyword

- **Number System / ระบบจำนวน** — วิธีเขียนแทนตัวเลขด้วยชุดสัญลักษณ์ (symbols) ชุดหนึ่ง
- **Base / Radix (ฐาน)** — จำนวนสัญลักษณ์ที่ใช้ในระบบนั้น
- **Decimal (ฐาน 10)** — `{0-9}` → มนุษย์ใช้
- **Binary (ฐาน 2)** — `{0,1}` → คอมพิวเตอร์ใช้
- **Octal (ฐาน 8)** — `{0-7}`
- **Hexadecimal (ฐาน 16)** — `{0-9, A-F}`
- **Positional Form / Polynomial Form** — ค่าของแต่ละหลักขึ้นกับ "ตำแหน่ง" (position)
- **MSD (Most Significant Digit)** — หลักซ้ายสุด, ค่ามากที่สุด
- **LSD (Least Significant Digit)** — หลักขวาสุด, ค่าน้อยที่สุด
- **MSB / LSB** — เหมือน MSD/LSD แต่ใช้เรียกในระบบฐานสอง (Bit)

## <span class="material-symbols-outlined">menu_book</span> Theory (เข้าใจง่าย)

ทุกระบบเลขฐานใช้หลักการเดียวกัน: **ค่าของตัวเลข = ผลรวมของ (หลัก × ฐานยกกำลังตำแหน่ง)**

$$N_b = a_{n-1}a_{n-2}\dots a_1a_0 . a_{-1}a_{-2}\dots a_{-m}$$

$$N = \sum a_i \times b^{i}$$

โดย `b` คือฐาน, ตำแหน่งซ้ายของจุดทศนิยมเริ่มนับจาก `0,1,2,...` (ยิ่งซ้ายยิ่งเลขชี้กำลังสูง) ส่วนขวาของจุดทศนิยมเป็นเลขชี้กำลังติดลบ `-1,-2,...`

**ตัวอย่างที่ทุกคนคุ้นเคย (ฐาน 10):**
$$2345 = 2\times10^3 + 3\times10^2 + 4\times10^1 + 5\times10^0$$

**หลักการเดียวกันนี้ใช้ได้กับทุกฐาน** เช่น ฐานสอง:
$$(1010.11)_2 = 1\times2^3+0\times2^2+1\times2^1+0\times2^0+1\times2^{-1}+1\times2^{-2} = (10.75)_{10}$$

> [!tip] จำง่ายๆ
> มนุษย์ใช้ฐาน 10 เพราะมี 10 นิ้ว, คอมพิวเตอร์ใช้ฐาน 2 เพราะวงจรไฟฟ้ามีแค่ 2 สถานะ (มี/ไม่มีกระแส → 1/0) ส่วนฐาน 8 และ 16 เป็น "ทางลัด" ในการเขียนเลขฐานสองยาวๆ ให้สั้นลง (จะเห็นชัดใน [[Base-Conversion]])

**ตารางเทียบฐาน (ต้องคุ้นตา ใช้บ่อยมาก):**

| Decimal | Binary | Octal | Hex |
|---|---|---|---|
| 0 | 0000 | 0 | 0 |
| 1 | 0001 | 1 | 1 |
| 2 | 0010 | 2 | 2 |
| ... | ... | ... | ... |
| 8 | 1000 | 10 | 8 |
| 15 | 1111 | 17 | F |
| 16 | 10000 | 20 | 10 |

**Powers ที่ควรจำขึ้นใจ:** $2^0..2^{10}$ = 1,2,4,8,16,32,64,128,256,512,1024 | $8^0..8^3$ = 1,8,64,512 | $16^0..16^3$ = 1,16,256,4096

## <span class="material-symbols-outlined">schema</span> Diagram

**แนวคิดแบบจำลองค่าประจำหลัก (Positional Form System Diagram):**

```mermaid
flowchart LR
    subgraph Positional_Form["แบบจำลองค่าประจำหลัก (Positional Form System)"]
        D0["บิตตำแหน่ง 0 (Position 0)<br/>b⁰"] --> Sum["ผลรวมค่าสุทธิ (Total Value N)<br/>N = Σ (digit × baseⁱ)"]
        D1["บิตตำแหน่ง 1 (Position 1)<br/>b¹"] --> Sum
        D2["บิตตำแหน่ง 2 (Position 2)<br/>b²"] --> Sum
        Dn["บิตตำแหน่ง n-1 (Position n-1)<br/>bⁿ⁻¹"] --> Sum
    end
```

**ตัวอย่างการแจกแจงค่าประจำหลักของเลข 2345 (Positional Weight Expansion):**

```mermaid
flowchart LR
    subgraph Decompose["การแจกแจงค่าประจำหลัก (Positional Weight Expansion)"]
        a["หลักพัน 2 (MSD)"] -->|"× 10³"| s["Sum = 2345 (Decimal Total)"]
        b["หลักร้อย 3"] -->|"× 10²"| s
        c["หลักสิบ 4"] -->|"× 10¹"| s
        d["หลักหน่วย 5 (LSD)"] -->|"× 10⁰"| s
    end
```

---
<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[Base-Conversion]]
