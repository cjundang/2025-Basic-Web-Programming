---
marp: true
theme: default
size: 16:9
paginate: true
title: สร้างเว็บ Static แสดงข้อมูลทั่วไปด้วย HTML+CSS
description: xxx
backgroundImage: url('wallpaper-1.jpg')
backgroundSize: cover
footer: "INF67-175 Web Development | บทที่ 3: สร้างเว็บ Static แสดงข้อมูลทั่วไปด้วย HTML+CSS"

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


# 🎨 บทที่ 3  
## สร้างเว็บ Static ด้วย HTML + CSS

**รายวิชา:** INF67-175 Web Development
**เป้าหมาย:** ทำให้เว็บไซต์สวยงามด้วยการใช้ CSS  

---

## 🎯 จุดประสงค์การเรียนรู้

เมื่อจบสัปดาห์นี้ ผู้เรียนสามารถ...

1. อธิบายความแตกต่างระหว่าง HTML และ CSS ได้  
2. ใช้ CSS จัดรูปแบบตัวอักษร สี พื้นหลัง และระยะห่างได้  
3. ใช้ class / id เพื่อเลือกตกแต่งเฉพาะส่วนได้  
4. เชื่อมไฟล์ CSS ภายนอกกับ HTML ได้  
5. ปรับแต่งเว็บจากสัปดาห์ที่ 2 ให้สวยงามยิ่งขึ้น  

---

## 🌐 HTML vs CSS

| รายการ | HTML | CSS |
|---------|------|-----|
| หน้าที่ | สร้างโครงสร้างเว็บ | ตกแต่งและจัดรูปแบบ |
| ตัวอย่าง | `<p>ยินดีต้อนรับ</p>` | `p { color: blue; }` |

💡 HTML = *โครงบ้าน* 🏠  
CSS = *การตกแต่งบ้าน* 🎀  

---

## 🧩 โครงสร้าง HTML + CSS ร่วมกัน

```html
<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8">
    <title>My Styled Web</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>เว็บไซต์ของฉัน</h1>
    <p>ยินดีต้อนรับเข้าสู่เว็บไซต์ตัวอย่าง</p>
  </body>
</html>
````

---

## 📁 ไฟล์ style.css

```css
body {
  background-color: #f0f8ff;
  font-family: "Prompt", sans-serif;
}
h1 {
  color: navy;
  text-align: center;
}
```

---

## 🧱 วิธีเขียน CSS 3 แบบ

### 1️⃣ Inline CSS

```html
<p style="color: blue;">ข้อความสีน้ำเงิน</p>
```

### 2️⃣ Internal CSS

```html
<style>
  p { color: green; }
</style>
```

### 3️⃣ External CSS (แนะนำ)

```html
<link rel="stylesheet" href="style.css">
```

---

## 🎯 การเลือกองค์ประกอบ (Selectors)

| ประเภท | ตัวอย่าง         | หมายเหตุ                 |
| ------ | ---------------- | ------------------------ |
| Tag    | `p { }`          | ใช้กับแท็กทุกตัว         |
| Class  | `.highlight { }` | ใช้กับ class="highlight" |
| ID     | `#header { }`    | ใช้กับ id="header"       |

```html
<h2 class="highlight">หัวข้อสำคัญ</h2>
<p id="info">ข้อความอธิบาย</p>
```

```css
.highlight { color: orange; }
#info { font-style: italic; }
```

---

## ✏️ ตัวอย่าง: จัดรูปแบบข้อความ

```css
h1 {
  color: darkblue;
  text-align: center;
  font-family: "Prompt", sans-serif;
  text-transform: uppercase;
  letter-spacing: 3px;
}
p {
  font-size: 18px;
  line-height: 1.6;
  text-indent: 30px;
}
```

---

## 🧍 ตัวอย่างผลลัพธ์

> **เว็บไซต์ของฉัน**
> ยินดีต้อนรับเข้าสู่เว็บไซต์ตัวอย่าง
> (ข้อความจัดกึ่งกลาง ตัวใหญ่ และอ่านง่าย)

---

## 🧱 Box Model (กล่องของทุกองค์ประกอบ)

**แต่ละ element คือกล่อง**
ประกอบด้วย:
`margin → border → padding → content`

```css
div.card {
  border: 1px solid #ccc;
  padding: 20px;
  margin: 10px;
  border-radius: 8px;
  background-color: white;
}
```

---

## 🌈 ตัวอย่างการตกแต่งพื้นหลัง

```css
body {
  background-color: #e3f2fd;
}

h2 {
  background-color: #2196f3;
  color: white;
  padding: 10px;
}

p {
  background-color: #ffffff;
  border-left: 5px solid #2196f3;
  padding: 10px;
}
```

---

## 🖼️ พื้นหลังแบบภาพ

```css
body {
  background-image: url("bg.jpg");
  background-size: cover;
  background-attachment: fixed;
  color: white;
}
```

💡 ใช้ภาพเบา ๆ เช่น .jpg หรือ .webp เพื่อไม่ให้เว็บช้า

---

## 🧍 การจัดวาง Layout เบื้องต้น

```css
.container {
  width: 80%;
  margin: auto;
}
img {
  display: block;
  margin: 0 auto;
}
```

🧠 **Tip:**

* ใช้ `text-align: center;` สำหรับข้อความ
* ใช้ `margin: auto;` สำหรับรูปหรือกล่อง

---

## 🔗 ตัวอย่างการตกแต่งเมนูนำทาง

```html
<nav>
  <a href="index.html">หน้าแรก</a>
  <a href="about.html">เกี่ยวกับ</a>
  <a href="contact.html">ติดต่อ</a>
</nav>
```

```css
nav {
  background-color: #003366;
  padding: 10px;
  text-align: center;
}
```
---

## 🔗 ตัวอย่างการตกแต่งเมนูนำทาง
```css
nav a {
  color: white;
  text-decoration: none;
  margin: 0 10px;
  padding: 8px 16px;
  border-radius: 4px;
}
nav a:hover {
  background-color: #0066cc;
}
```

---
