---
marp: true
theme: default
size: 16:9
paginate: true
title: React Navigation and Lesson App
description: สไลด์สรุปจากเอกสาร 07_th.md
backgroundImage: url('wallpaper.png')
backgroundSize: cover
style: |
  section {
    color: blue; /* สีตัวอักษรทั้งหมด */
  }
  h1 {
    color: black;
    font-size: 56px !important;
    line-height: 1.1;
    margin: 0.2em 0 0.4em;
    
  }
  h2 {
    color: black;
    font-size: 56px !important;
    line-height: 1.1;
    margin: 0.2em 0 0.4em;
    
  }
  h3 {
    color: black;
  }
---

# 🌐 Basic Web Programming  
## บทที่ 2 : CSS พื้นฐาน & Box Model


---

# 🎯 จุดประสงค์การเรียนรู้

หลังจบบทนี้ ผู้เรียนจะสามารถ...

- อธิบายหน้าที่ของ CSS ได้  
- เชื่อม CSS แบบ inline / internal / external ได้  
- ใช้ selectors เพื่อเลือกองค์ประกอบ HTML ได้  
- ปรับสี ฟอนต์ และการจัดวางด้วย display / margin / padding / border  
- ออกแบบและตกแต่งหน้า **Profile Page** ด้วย external CSS ได้

---

# 🧩 CSS คืออะไร?

- **CSS (Cascading Style Sheets)** ใช้ "กำหนดหน้าตา" ของหน้าเว็บ  
- แยกส่วน **โครงสร้าง (HTML)** ออกจาก **การตกแต่ง (CSS)**

```html
<p>สวัสดี</p>
````

```css
p {
  color: blue;
  font-size: 20px;
}
```

---

# 🔗 การเชื่อม CSS มี 3 แบบ

| แบบ      | วิธีเขียน                                  | ใช้เมื่อ           |
| -------- | ------------------------------------------ | ------------------ |
| Inline   | `<p style="color:red;">`                   | แก้เฉพาะจุด        |
| Internal | `<style> ... </style>` ใน `<head>`         | หน้าเดียว          |
| External | `<link rel="stylesheet" href="style.css">` | หลายหน้าใช้ร่วมกัน |

---

# 🧠 สาธิต: การเชื่อมแบบ External

**HTML:**

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>My Profile</h1>
</body>
```

**style.css:**

```css
h1 {
  color: royalblue;
  text-align: center;
}
```

---

# 🎯 ฝึกทำ: เชื่อม External CSS

🪄 สร้างไฟล์

1. `index.html`
2. `style.css`

จากนั้นให้ลองเปลี่ยน:

* สีพื้นหลัง `<body>`
* สีตัวอักษร `<h1>`

---

# 🪞 CSS Selectors

ใช้ "เลือก" องค์ประกอบ HTML ที่จะตกแต่ง

| ชนิด    | ตัวอย่าง    | อธิบาย                      |
| ------- | ----------- | --------------------------- |
| Element | `p {}`      | ทุกแท็ก `<p>`               |
| Class   | `.box {}`   | องค์ประกอบที่มี class="box" |
| ID      | `#main {}`  | เฉพาะ id="main"             |
| กลุ่ม   | `h1, h2 {}` | หลายแท็กพร้อมกัน            |
| ซ้อนกัน | `div p {}`  | `<p>` ที่อยู่ใน `<div>`     |

---

# 🎨 สี และ ฟอนต์

```css
body {
  background-color: #f0f0f0;
  color: #333;
  font-family: "Prompt", sans-serif;
}
```

🧭 **รูปแบบสีที่ใช้ได้**

* ชื่อสี เช่น `red`
* รหัส HEX เช่น `#ff0000`
* RGB เช่น `rgb(255,0,0)`

---

# 🧱 Box Model

องค์ประกอบแต่ละชิ้น = "กล่อง"

```
+-----------------------+
|     margin            |
|  +------------------+ |
|  |   border         | |
|  | +--------------+ | |
|  | |  padding     | | |
|  | | +----------+ | | |
|  | | | content  | | | |
|  | | +----------+ | | |
|  | +--------------+ | |
|  +------------------+ |
+-----------------------+
```

---

# ⚙️ ส่วนประกอบของ Box Model

```css
div {
  margin: 20px;
  padding: 10px;
  border: 2px solid black;
}
```

| ส่วน      | หน้าที่                      |
| --------- | ---------------------------- |
| `margin`  | ระยะห่างรอบนอก               |
| `border`  | เส้นขอบกล่อง                 |
| `padding` | ระยะห่างระหว่างขอบกับเนื้อหา |
| `content` | เนื้อหาจริงในกล่อง           |

---

# 📏 display property

```css
p { display: block; }
span { display: inline; }
```

| ค่า          | หน้าที่                                  |
| ------------ | ---------------------------------------- |
| block        | เริ่มบรรทัดใหม่ (เช่น `<div>`, `<p>`)    |
| inline       | ต่อเนื่องในบรรทัด (เช่น `<span>`, `<a>`) |
| inline-block | เหมือน inline แต่ปรับขนาดได้             |
| none         | ซ่อนองค์ประกอบ                           |

---

# 🧪 สาธิต: กล่องและระยะห่าง

```html
<div class="card">Hello CSS!</div>
```

```css
.card {
  background: lightblue;
  border: 2px solid blue;
  padding: 20px;
  margin: 10px;
}
```

👉 สังเกตผลเมื่อเปลี่ยนค่า `margin` และ `padding`

---

# 💄 ตกแต่ง Profile Page (Before)

**HTML เท่านั้น**

```html
<body>
  <h1>ชื่อ-สกุล</h1>
  <p>นักศึกษาสาขา ...</p>
  <img src="me.jpg" alt="profile photo">
</body>
```

---

# 💅 ตกแต่ง Profile Page (After)

**style.css**

```css
body {
  font-family: 'Prompt', sans-serif;
  background-color: #fdfdfd;
  text-align: center;
}

img {
  border-radius: 50%;
  width: 150px;
  border: 3px solid #0077ff;
}

h1 {
  color: #0077ff;
}
```

---

# 🧩 สรุปสิ่งที่เรียนรู้วันนี้

✅ CSS คือภาษาสำหรับตกแต่งเว็บ
✅ มี 3 วิธีเชื่อมต่อ: inline / internal / external
✅ ใช้ selectors เพื่อกำหนดรูปแบบเฉพาะจุด
✅ เข้าใจ Box Model และการจัดระยะห่าง
✅ ฝึกตกแต่งหน้า Profile ด้วย external CSS

---

# 🧠 กิจกรรมท้ายชั่วโมง

> สร้างหน้าเว็บ “My Profile”
> และตกแต่งด้วย `style.css` ให้ดูเป็นมืออาชีพ

💡 แนะนำ:

* ใช้สีพื้นหลังที่เหมาะสม
* ปรับขนาดรูปโปรไฟล์ให้กลม
* จัดข้อความให้อยู่ตรงกลาง

