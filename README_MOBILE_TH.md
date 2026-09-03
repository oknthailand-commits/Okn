# BP1048P4 DSP 7CH — UI v1.1

โปรเจกต์ Android แนวนอนสำหรับมือถือ โดยยึดภาพต้นแบบของผู้ใช้เป็นหลัก

หน้าหลัก:
- MAIN: Master + Fader CH1–CH7
- EQ: 15 Band และกราฟ EQ
- CROSSOVER: HPF/LPF
- DELAY: Time Alignment
- MIXER: L/R
- PRESET
- SETTINGS

หมายเหตุ: BLE layer และ protocol layer เป็นฐานสำหรับการเชื่อมต่อ BP1048P4; คำสั่ง DSP จริงต้องยืนยันกับ firmware ของบอร์ด GoloPine ก่อนใช้งานจริง


v2.2.1 BLE CAPTURE.1: แก้ compile error จากชื่อตัวแปร master ซ้ำกับ LinearLayout แล้ว


v2.1.0: เพิ่มหน้า BLE MONITOR สำหรับดู TX/RX, UUID และสถานะการเขียน เพื่อไล่โปรโตคอล GoloPine/BP1048P4


v2.1.2: เพิ่มปุ่ม BLE MONITOR ที่หน้า MAIN และเปิดหน้า Monitor โดยตรง


v2.1.3: แก้หน้า BLE MONITOR ให้แสดงจริงใน body และอัปเดต LOG แบบสดเมื่อรับข้อมูล BLE


v2.2.1 BLE CAPTURE: READ TEST ส่ง firmware query เดียว พร้อมแสดง READ TEST PRESSED ใน LOG เพื่อยืนยันการกดปุ่ม


### v2.4.4: Master Android/Bluetooth Link เปิดตลอด
ไม่ต้องติ๊ก checkbox อีกต่อไป การลาก Master จะปรับ Android/Bluetooth media volume ทันที
