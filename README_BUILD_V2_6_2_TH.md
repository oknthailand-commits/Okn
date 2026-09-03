# GoloPine DSP 7CH v2.6.2 — Build Fix

รุ่นนี้แก้ workflow สำหรับ GitHub Actions โดยใช้ Java 17 + Gradle 8.9 + Android Gradle Plugin 8.7.3

## วิธีใช้บนมือถือ
1. แตก ZIP แล้วนำ **ไฟล์และโฟลเดอร์ภายใน ZIP** ไปไว้ที่ root ของ GitHub repository
2. เปิดแท็บ **Actions**
3. เลือก **Build GoloPine DSP 7CH APK**
4. กด **Run workflow**
5. เมื่อ Build ผ่าน ให้เปิดงานที่สำเร็จ → **Artifacts** → `GoloPine-DSP-7CH-v2.6.2-debug`
6. ดาวน์โหลด ZIP ของ artifact แล้วแตกไฟล์ จะได้ `app-debug.apk`

## หน้าจอ
- MAIN ตาม Reference UI
- EQ 15-Band ตาม Reference UI
- ปุ่มเชื่อมต่อ DSP อยู่บนหน้า MAIN
- Landscape responsive

## หมายเหตุ protocol
BLE transport ใช้ GoloPine 250401: AB00 / AB01 / AB02 ที่ยืนยันจาก HCI capture
ยังไม่เปิดการเขียน EQ/GAIN แบบเดาสุ่มจนกว่าจะยืนยัน command mapping ของ firmware จริง
