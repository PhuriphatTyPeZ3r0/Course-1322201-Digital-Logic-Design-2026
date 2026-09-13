---
tags: [dld, week1, number-system, arithmetic]
course: 1322201
week: 1
date: 2026-09-07
---

# การคูณ/หารเลขฐานสอง

<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[Week1-MOC|MOC สัปดาห์ 1]] | ก่อนหน้า: [[Complements]]

## <span class="material-symbols-outlined">key</span> Keyword

- ใช้**หลักการเดียวกับเลขฐานสิบ** เพียงแต่มีแค่ 2 เลข (0,1)
- **การคูณ** = shift + add (เลื่อนบิตแล้วบวก)
- **การหาร** = long division แบบเดียวกับฐาน 10

## <span class="material-symbols-outlined">menu_book</span> Theory (เข้าใจง่าย)

**การคูณเลขฐานสอง:** ตารางคูณมีแค่ 4 กรณี (ง่ายกว่าฐาน 10 มาก)

| A | B | A×B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

วิธีทำ: คูณตัวตั้งด้วยแต่ละบิตของตัวคูณทีละบิต (ได้ผลคูณย่อย = ตัวตั้งเดิม หรือ 0 ทั้งหมด) แล้ว**เลื่อนตำแหน่ง (shift)** ไปทางซ้ายทีละ 1 ตำแหน่งในแต่ละบรรทัดเหมือนคูณเลขฐาน 10 จากนั้นนำผลคูณย่อยทั้งหมดมา**บวกกัน** (ใช้กติกาบวกเลขฐานสองจาก [[Binary-Arithmetic]])

**การหารเลขฐานสอง:** ใช้วิธี long division เหมือนฐาน 10 ทุกขั้นตอน คือ เทียบตัวหารกับตัวตั้งบางส่วน ถ้าหารได้ (ตัวตั้งบางส่วน ≥ ตัวหาร) ใส่ 1 แล้วลบออก ถ้าหารไม่ได้ใส่ 0 แล้วดึงบิตถัดไปลงมา ทำซ้ำจนครบ

## <span class="material-symbols-outlined">schema</span> Diagram

**การคูณแบบเลื่อนและบวก (Shift-and-Add Multiplication Activity Diagram):**

```mermaid
flowchart TD
    Start((●)) --> Init(["รับตัวตั้งและตัวคูณ (Input Multiplicand & Multiplier)"])
    Init --> Pick(["อ่านตัวคูณทีละบิตจาก LSB (Read Multiplier Bit)"])
    Pick --> IsOne{"บิตนี้ = 1 ?<br/>(Multiplier Bit = 1?)"}
    IsOne -->|Yes| Copy(["ผลคูณย่อย = ตัวตั้งเลื่อนซ้ายตามตำแหน่ง<br/>(Shifted Multiplicand)"])
    IsOne -->|No| Zero(["ผลคูณย่อย = 0 เลื่อนซ้ายตามตำแหน่ง<br/>(Zero Shifted)"])
    Copy --> More{"ยังมีบิตตัวคูณเหลือไหม?<br/>(More multiplier bits?)"}
    Zero --> More
    More -->|Yes| Pick
    More -->|No| SumAll(["บวกผลคูณย่อยทุกแถวรวมกัน (Accumulate Partial Products)"])
    SumAll --> Done(["ได้ผลคูณสุทธิ (Product Output)"])
    Done --> Stop(((●)))
```

**การหารยาวเลขฐานสอง (Binary Long Division Activity Diagram):**

```mermaid
flowchart TD
    Start((●)) --> Init(["รับตัวตั้งและตัวหาร (Input Dividend & Divisor)"])
    Init --> Compare(["เทียบตัวหารกับส่วนบนของตัวตั้ง (Compare Divisor vs Partial Dividend)"])
    Compare --> Enough{"หารได้หรือไม่ ?<br/>(Partial Dividend ≥ Divisor?)"}
    Enough -->|Yes| One(["เขียน 1 ในผลหาร ลบตัวหารออก<br/>(Quotient bit = 1, Subtract Divisor)"])
    Enough -->|No| ZeroQ(["เขียน 0 ในผลหาร<br/>(Quotient bit = 0)"])
    One --> Bring(["ดึงบิตถัดไปของตัวตั้งลงมาต่อ (Bring down next bit)"])
    ZeroQ --> Bring
    Bring --> More{"ยังมีบิตตัวตั้งเหลือไหม?<br/>(More bits remaining?)"}
    More -->|Yes| Compare
    More -->|No| Done(["ได้ผลหารและเศษ (Quotient & Remainder)"])
    Done --> Stop(((●)))
```

---
<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[Codes-BCD]]
