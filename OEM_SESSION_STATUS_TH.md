# v2.4.2 OEM SESSION + HCI ANALYZER

รุ่นนี้ปรับโครงสร้างให้ปลอดภัยและตรงกับหลักฐานที่จับได้จาก GoloPine/HCI

## ยืนยันจาก HCI
- BLE ATT Write Command (`0x52`)
- TX handle ที่พบจริง: `0x0006`
- ตรงกับ characteristic AB01 ใน session ที่จับได้
- มีทั้ง payload 9 ไบต์และ 13 ไบต์ใน capture

## สิ่งที่ยังไม่ยืนยัน
ข้อมูลหลัง AB01 เป็นข้อมูลเข้ารหัส/obfuscated จึงยังไม่เปิดการเขียน DSP จาก Master Volume/EQ แบบเดาสุ่ม

## เพิ่มใน 2.4.2
- HCI ANALYZER บนมือถือ
- เลือกไฟล์ `.cfa` / `btsnoop_hci.log` แล้วแสดง ATT writes
- กรอง handle `0x0006` ให้อัตโนมัติ
- แสดงจำนวน packet และ packet ที่ยาว >=13 ไบต์
- HCI Analyzer เป็น read-only ไม่ส่งข้อมูลกลับไปยัง DSP
- ปรับเวอร์ชัน Settings เป็น 2.4.2
- คง BLE scanner/connection และ UI DSP 7CH

## เป้าหมายต่อไป
ใช้ capture ที่มีอยู่และ capture ที่ผู้ใช้สร้างจากการเปลี่ยนค่าเพียงหนึ่งตัวแปร เพื่อหาความสัมพันธ์ของ actuator payload และ session/authentication ก่อนเปิด live write
