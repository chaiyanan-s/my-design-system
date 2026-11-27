# my-design-system

Design token และไอคอนสำหรับให้ Claude Design ใช้สร้าง UI

| ที่อยู่ | เนื้อหา | ต้นทาง |
|---|---|---|
| `tokens/tokens.css` | สี ระยะห่าง มุมโค้ง ขนาด motion เงา gradient และ text style | [Demo Training - UI System](https://www.figma.com/design/whJejnFfwT8EFTWjuoId7X/) |
| `icons/<name>.svg` | ไอคอน Lucide 2,044 ตัว (รายชื่อใน `icons/INDEX.txt`) | [Lucide Icons (Community)](https://www.figma.com/design/Ya2vvyOyUTWxQfSbrTXuMX/) |

## กติกาการใช้

- โหลด `tokens/tokens.css` แล้วอ้างค่าด้วย `var(--...)` ห้าม hardcode สี ระยะห่าง หรือมุมโค้ง
- ชื่อ token: Figma `bg/canvas` คือ CSS `--bg-canvas`
- สีใน UI ใช้ semantic token (`--bg-*`, `--text-*`, `--border-*`, `--chart-*`) ไม่ใช้ primitive เช่น `--orange-700` โดยตรง
- `brand` คือสีส้ม ส่วน `accent`, `link`, `focus`, `selected` คือสีน้ำเงิน (royal)
- ตัวอักษรใช้คลาส `.type-*` เช่น Figma `Body/Default` คือ `.type-body-default` ฟอนต์ IBM Plex Sans Thai
- เงาใช้ `box-shadow: var(--elevation-panel | sticky | dialog | toast)`
- `--gradient-brand` ใช้กับข้อความสีขาวแบบหนา ขนาด 18.66px ขึ้นไปเท่านั้น
- มีธีมสว่างอย่างเดียว
- Layout ใช้ `--device-{handheld,tablet,desktop}-{margin,gutter,columns}`

## ไอคอน

- ใช้ไอคอนจาก `icons/` เท่านั้น ค้นชื่อใน `icons/INDEX.txt` ห้ามวาด SVG เองหรือเดาชื่อ
- กรอบ 24×24 เส้นหนา 2 และใช้ `stroke="currentColor"` จึงกำหนดสีด้วย `color` ของ element แม่ ให้ inline SVG เพราะถ้าโหลดผ่าน `<img>` จะไม่รับสี
- SVG มาจากแพ็กเกจ `lucide-static` 1.82.0 โดยจับคู่ตามชื่อไอคอนใน Figma มี 18 ตัวที่เวอร์ชันนี้ไม่มี (โลโก้แบรนด์ เช่น `github`, `figma` และ `rail-symbol`) จึงใช้จาก 0.469.0
- สัญญาอนุญาตอยู่ใน `icons/LICENSE` โลโก้แบรนด์ยังเป็นเครื่องหมายการค้าของเจ้าของแบรนด์
