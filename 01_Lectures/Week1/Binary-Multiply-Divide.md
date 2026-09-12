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

**การคูณ (shift-and-add):**

```mermaid
flowchart TD
    Start(["ตัวตั้ง × ตัวคูณ"]) --> Pick["อ่านตัวคูณทีละบิตจาก LSB"]
    Pick --> IsOne{"บิตนี้ = 1 ?"}
    IsOne -->|ใช่| Copy["ผลคูณย่อยบรรทัดนี้ = ตัวตั้ง (เลื่อนซ้ายตามตำแหน่งบิต)"]
    IsOne -->|ไม่ใช่| Zero["ผลคูณย่อยบรรทัดนี้ = 0 (เลื่อนซ้ายตามตำแหน่งบิต)"]
    Copy --> More{"ยังมีบิตตัวคูณเหลือไหม?"}
    Zero --> More
    More -->|มี| Pick
    More -->|ไม่มี| SumAll["บวกผลคูณย่อยทุกบรรทัดรวมกัน"]
    SumAll --> Done(["คำตอบ"])
```

**การหาร (long division):**

```mermaid
flowchart TD
    Start(["ตัวตั้ง ÷ ตัวหาร"]) --> Compare["เทียบตัวหารกับส่วนบนของตัวตั้ง"]
    Compare --> Enough{"หารได้ไหม<br/>(ส่วนบน ≥ ตัวหาร)?"}
    Enough -->|"ได้"| One["เขียน 1 ในผลหาร<br/>ลบตัวหารออกจากส่วนบน"]
    Enough -->|"ไม่ได้"| ZeroQ["เขียน 0 ในผลหาร"]
    One --> Bring["ดึงบิตถัดไปของตัวตั้งลงมาต่อ"]
    ZeroQ --> Bring
    Bring --> More{"ยังมีบิตเหลือไหม?"}
    More -->|มี| Compare
    More -->|ไม่มี| Done(["ผลหาร + เศษที่เหลือ"])
```

---
<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[Codes-BCD]]
