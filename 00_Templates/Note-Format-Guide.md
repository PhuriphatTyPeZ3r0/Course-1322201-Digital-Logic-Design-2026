---
tags: [dld, meta, guide]
---

# คู่มือ Format การสรุปโน้ตวิชา Digital Logic Design (1322201)

โน้ตทุกไฟล์ในวิชานี้ใช้ format เดียวกัน เพื่อให้:
- สแกนข้ามโน้ตของแต่ละคนได้เร็ว (icon หัวข้อเดียวกันหมด อยู่ตำแหน่งเดิมเสมอ)
- backlink ระหว่างโน้ต ↔ MOC ทำงานได้จริง ไม่ขาดตอน
- ทุกคนสรุปแล้วเอามารวม/แชร์กันได้โดยไม่ต้องแปลง format

Template 2 ไฟล์ในโฟลเดอร์นี้ (`Lecture-Note-Template.md`, `MOC-Template.md`) คือของที่ให้ copy ไปกรอกจริง ส่วนไฟล์นี้อธิบายว่า "ทำไม" แต่ละกฎถึงเป็นแบบนี้ พร้อมตัวอย่างจริงจาก `01_Lectures/Week1/` และ `01_Lectures/Week2/`

## วิธีใช้งานใน Obsidian

1. เปิด **Settings → Core plugins → Templates** ให้เป็นเปิด (เปิดอยู่แล้วใน vault นี้)
2. ตั้ง **Template folder location** = `00_Templates`
3. (แนะนำ) ตั้ง **Date format** = `YYYY-MM-DD` ใน settings ของ Templates plugin เพื่อให้ `{{date}}` ออกมาตรงกับ format ที่ใช้ในโน้ตทุกไฟล์
4. สร้างโน้ตใหม่ → `Ctrl/Cmd+P` → "Insert template" → เลือก `Lecture-Note-Template` หรือ `MOC-Template`
5. ถ้า copy ไป vault อื่น: เอาแค่ 2 ไฟล์ template ไปวางในโฟลเดอร์ template ของ vault นั้น ไม่ต้องพึ่ง config อื่นของ vault นี้

**Placeholder 2 แบบในไฟล์ template:**
- `{{title}}`, `{{date}}` — Obsidian เติมให้อัตโนมัติตอน insert template (`{{title}}` = ชื่อไฟล์ที่ตั้งตอนสร้างโน้ต)
- `<ข้อความในวงเล็บมุม>` — ต้องลบแล้วพิมพ์ทับเอง ก่อน commit **ห้ามเหลือ `<...>` ค้างอยู่ในไฟล์จริง**

## กฎ Frontmatter

| field | โน้ตหัวข้อ | MOC | หมายเหตุ |
| --- | --- | --- | --- |
| `tags` | `[dld, weekN, <topic-tag>]` | `[dld, weekN, moc]` | topic-tag เลือก 1-2 คำที่สื่อเนื้อหา เช่น `number-system`, `complement` |
| `course` | `1322201` | `1322201` | ตายตัว ไม่ต้องเปลี่ยน |
| `week` | เลขสัปดาห์ | เลขสัปดาห์ | ต้องตรงกับเลขใน `tags` |
| `date` | `{{date}}` | `{{date}}` | วันที่สร้างโน้ต (≈ วันที่เข้าเรียน) |
| `course-name`, `instructor`, `source` | ไม่ใช้ | ใช้ | มีเฉพาะใน MOC เท่านั้น — `source` คือชื่อไฟล์สไลด์ที่ใช้สอนสัปดาห์นั้น |

## กฎโครงสร้างโน้ตรายหัวข้อ (`Lecture-Note-Template.md`)

อ้างอิงจริง: [[../01_Lectures/Week1/Binary-Arithmetic.md|Binary-Arithmetic]], [[../01_Lectures/Week1/Complements.md|Complements]]

1. **H1** — ชื่อหัวข้อภาษาไทย (ใส่ภาษาอังกฤษกำกับในวงเล็บถ้าเป็นศัพท์เทคนิคที่ควรจำ)
2. **บรรทัด nav บนสุด** — `<span class="material-symbols-outlined">arrow_back</span> กลับไปที่ [[WeekN-MOC]] | ก่อนหน้า: [[...]]`
   - โน้ตแรกของสัปดาห์: ตัดส่วน "ก่อนหน้า" ออก เหลือแค่ลิงก์กลับ MOC (ดู `Course-Intro.md`)
3. **<span class="material-symbols-outlined">key</span> Keyword** (บังคับ) — list คำศัพท์/แนวคิดหลัก 2-5 ตัว แบบ **ตัวหนา** + คำอธิบาย 1 บรรทัด ไม่ใช่ theory ยาว ๆ
4. **<span class="material-symbols-outlined">menu_book</span> Theory (เข้าใจง่าย)** (บังคับ) — เนื้อหาหลัก ใช้ตาราง/สูตร LaTeX (`$...$`)/callout ได้ตามความเหมาะสม แบ่ง `###` ย่อยได้ถ้ายาว
5. **<span class="material-symbols-outlined">schema</span> Diagram** (มีเงื่อนไข — ดูหัวข้อถัดไป)
6. **บรรทัดปิดท้าย** — `---` แล้วตามด้วย `<span class="material-symbols-outlined">arrow_forward</span> ต่อไป: [[...]]`
   - โน้ตสุดท้ายของสัปดาห์: เปลี่ยนเป็นลิงก์กลับ MOC แทน (ดูรูปแบบท้าย `Course-Intro.md`)

### เมื่อไหร่ต้องมี <span class="material-symbols-outlined">schema</span> Diagram และเมื่อไหร่ไม่ต้องมี

ใส่เฉพาะเมื่อหัวข้อมี **ขั้นตอน/กระบวนการ/decision flow** ที่วาด mermaid flowchart แล้วช่วยความเข้าใจจริง (เช่น กระบวนการบวกเลขฐานสอง, ขั้นตอนลบด้วย Complement) ถ้าหัวข้อเป็นเนื้อหาบอกเล่า/นิยาม/ตารางล้วน ๆ ไม่มีลำดับขั้นตอน **ให้ลบ section นี้ทิ้งทั้งหมด** — ตัวอย่างจริงที่ไม่มี Diagram คือ `Course-Intro.md` (เนื้อหา admin ไม่มีกระบวนการให้วาด)

## กฎโครงสร้าง MOC (`MOC-Template.md`)

อ้างอิงจริง: [[../01_Lectures/Week1/Week1-MOC.md|Week1-MOC]], [[../01_Lectures/Week2/Week2-MOC.md|Week2-MOC]]

1. **H1** — `Week N — <ชื่อหัวข้อสัปดาห์ภาษาอังกฤษ> (MOC)`
2. **บรรทัด nav บนสุด** — ลิงก์สัปดาห์ก่อนหน้า (ไม่มีในสัปดาห์แรกของวิชา)
3. **<span class="material-symbols-outlined">check_circle</span> เช็คลิสต์ก่อนเข้าเรียน** (บังคับ) — checkbox list สิ่งที่ควรทบทวน/เตรียมก่อนเข้าเรียน แต่ละข้อลิงก์ไปโน้ตที่เกี่ยวข้อง
4. **<span class="material-symbols-outlined">assignment</span> ภาพรวมสัปดาห์ N (สรุปย่อ)** (บังคับ) — ย่อหน้าสรุปเนื้อหาทั้งสัปดาห์ ไม่ใช่แค่สัปดาห์แรกที่มีเนื้อหา orientation — ทุกสัปดาห์มี section นี้เสมอ แค่เนื้อหาข้างในเปลี่ยนไปตามหัวข้อจริงของสัปดาห์นั้น
5. **<span class="material-symbols-outlined">map</span> แผนที่หัวข้อสัปดาห์ N** (บังคับ) — mermaid `graph TD` แสดงหัวข้อหลัก → หัวข้อย่อย ของสัปดาห์นั้น
6. **<span class="material-symbols-outlined">collections_bookmark</span> โน้ตรายหัวข้อ** (บังคับ) — ตาราง หัวข้อ / เนื้อหาหลัก / หน้าสไลด์
7. **callout ปิดท้าย** (ไม่บังคับ แต่แนะนำ) — เลือกได้ตามบริบท เช่น `[!tip]` สรุปจุดที่มักสับสน หรือแอบดูหัวข้อสัปดาห์หน้า
8. **บรรทัดปิดท้าย** — ลิงก์สัปดาห์ถัดไป (ใส่ทีหลังตอนสร้าง MOC สัปดาห์ถัดไปแล้ว ถ้ายังไม่มีให้ลบบรรทัดนี้ก่อน)

> [!note] หมายเหตุ
> section "ภาพรวมคาบปฐมนิเทศ" ที่เห็นใน `Week1-MOC.md` เป็นเนื้อหาเฉพาะของสัปดาห์เปิดเทอม (แนะนำรายวิชา) **ไม่ได้รวมอยู่ใน MOC-Template.md** — ให้ใช้ section "<span class="material-symbols-outlined">assignment</span> ภาพรวมสัปดาห์ N" ธรรมดาแทนสำหรับทุกสัปดาห์

## ชุด Icon หัวข้อ (ตายตัว ห้ามเปลี่ยน)

| Icon (Material Symbols) | รหัส HTML | ใช้กับ | ความหมาย |
| --- | --- | --- | --- |
| arrow_back / arrow_forward | `<span class="material-symbols-outlined">arrow_back</span>` / `<span class="material-symbols-outlined">arrow_forward</span>` | ทุกโน้ต | นำทางไปก่อนหน้า/ถัดไป |
| key | `<span class="material-symbols-outlined">key</span>` | โน้ตหัวข้อ | Keyword |
| menu_book | `<span class="material-symbols-outlined">menu_book</span>` | โน้ตหัวข้อ | Theory |
| schema | `<span class="material-symbols-outlined">schema</span>` | โน้ตหัวข้อ | Diagram |
| check_circle | `<span class="material-symbols-outlined">check_circle</span>` | MOC | เช็คลิสต์ก่อนเข้าเรียน |
| assignment | `<span class="material-symbols-outlined">assignment</span>` | MOC | ภาพรวมสัปดาห์ |
| map | `<span class="material-symbols-outlined">map</span>` | MOC | แผนที่หัวข้อ (mermaid) |
| collections_bookmark | `<span class="material-symbols-outlined">collections_bookmark</span>` | MOC | ตารางโน้ตรายหัวข้อ |

## Callout ที่ใช้ได้

| Callout | ใช้เมื่อ |
| --- | --- |
| `[!tip]` | เคล็ดลับ/เทคนิคช่วยจำ, จุดที่มักสับสน, แอบดูหัวข้อถัดไป |
| `[!important]` | ข้อควรระวัง หรือความแตกต่างสำคัญที่มักทำผิด |
| `[!note]` | ข้อสังเกตเพิ่มเติมที่ไม่ใช่ theory หลัก |
| `[!example]` | ตัวอย่างที่ยกมาจากสไลด์โดยตรง |
| `[!info]` | ประกาศ/ข้อมูลตารางเรียน (ใช้เฉพาะกรณีจำเป็นใน MOC) |

## Checklist ก่อน commit

- [ ] ไม่มี `<...>` ค้างอยู่ในไฟล์
- [ ] `week` ใน frontmatter ตรงกับ `tags`
- [ ] ลิงก์ `[[...]]` ทั้งหมดชี้ไปโน้ตที่มีอยู่จริง (ไม่ใช่ placeholder)
- [ ] ถ้าไม่มี Diagram section ต้องเป็นเพราะหัวข้อไม่มีกระบวนการจริง ๆ ไม่ใช่ขี้เกียจวาด
- [ ] เพิ่มแถวของโน้ตนี้ใน MOC (ตาราง <span class="material-symbols-outlined">collections_bookmark</span> + แผนที่ <span class="material-symbols-outlined">map</span>) ของสัปดาห์นั้นแล้ว
