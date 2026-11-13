# Pilot Logbook Entry Web App

เว็บแอป (ไฟล์ HTML ไฟล์เดียว) สำหรับกรอกข้อมูลรายการบินลงไฟล์ Pilot Logbook Excel — เปิดในเบราว์เซอร์ได้เลย ไม่ต้องติดตั้งอะไร

A single-file HTML web app for entering flight records into a Pilot Logbook Excel (.xlsx) file. Runs entirely in the browser.

## วิธีใช้ / Usage

1. เปิด `index.html` ใน Chrome หรือ Edge (ต้องต่ออินเทอร์เน็ตครั้งแรกเพื่อโหลดไลบรารี ExcelJS จาก CDN)
2. ลากไฟล์ `.xlsx` ของ logbook มาวาง หรือคลิกเลือกไฟล์
3. กรอกรายการบินในฟอร์ม แล้วกด **+ เพิ่มรายการ**
4. กด **บันทึกลง Excel และดาวน์โหลด** เพื่อรับไฟล์ใหม่ (ไฟล์ต้นฉบับไม่ถูกแก้ไข)

## คุณสมบัติ / Features

- อ่านโครงสร้าง logbook แบบ 50 ชีต (S1–S50, ข้อมูลแถว 4–21 ต่อชีต) อัตโนมัติ และต่อรายการใหม่จากแถวว่างถัดไป
- Dropdown ตรงตาม validation ในไฟล์: ชนิดเครื่องบิน, ภารกิจ, สถานะการบิน, ชั่วโมงบิน 0.1–5.0
- ดู แก้ไข ลบรายการเก่าได้ทุกชีต พร้อมสรุปชั่วโมงบินรวม
- เขียนเฉพาะคอลัมน์ค่า — สูตร Excel, แถว Total และรูปแบบเซลล์เดิมถูกรักษาไว้
- ข้อมูลไม่ถูกส่งออกจากเครื่อง (ประมวลผลในเบราว์เซอร์ทั้งหมด)

## GitHub Pages

เปิดใช้งานเป็นเว็บไซต์ได้: repo → **Settings → Pages → Source: Deploy from a branch → main / (root)** แล้วเข้าที่ `https://<username>.github.io/<repo>/`

## Tech

- [ExcelJS](https://cdnjs.cloudflare.com/ajax/libs/exceljs/4.4.0/exceljs.min.js) (CDN) — อ่าน/เขียน .xlsx โดยรักษาสูตรและสไตล์
- HTML + CSS + Vanilla JS ไฟล์เดียว ไม่มี build step
