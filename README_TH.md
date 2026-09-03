# BP1048P4 DSP 7CH Controller v1.4

รุ่นวิเคราะห์ BLE สำหรับกรณี TX ขึ้น [FAILED]

การแก้ไข:
- ตรวจสอบ Properties ของ characteristic ก่อนเขียน
- เลือก WRITE หรือ WRITE_NO_RESPONSE ให้ตรงกับ characteristic
- แสดง Service UUID และ Characteristic UUID/Properties ใน log
- ไม่ส่ง firmware request อัตโนมัติทันทีหลัง connect เพื่อไม่ให้ชนกับขั้นตอน GATT/notification
- แสดงสาเหตุเมื่อ TX characteristic เขียนไม่ได้

ขั้นทดสอบ:
1. เปิด Bluetooth และอนุญาต Nearby devices
2. เปิดแอป
3. กด ค้นหา DSP
4. ถ้าเชื่อมต่อได้ ให้ดูบรรทัด GATT / TX
5. ส่งภาพหน้าจอ log มา เพื่อระบุ characteristic ที่ GoloPine firmware ใช้จริง

v2.4.4: เพิ่ม MASTER PACKET LAB สำหรับเทียบ HCI BEFORE/AFTER และหา packet Master Volume จริงจาก AB01/handle 0x0006 โดยไม่ส่ง packet เดาสุ่ม
