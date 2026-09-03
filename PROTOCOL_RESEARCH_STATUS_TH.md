# BP1048P4 DSP PRO v2.3.5 — Protocol Research Status

## เป้าหมาย
สร้างเครื่องมือ Android สำหรับควบคุม BP1048P4 7CH และแกะโปรโตคอล GoloPine รุ่น 1 Apr 2026 โดยไม่ส่ง packet ที่ยังไม่ยืนยันไปยังฮาร์ดแวร์

## หลักฐานจาก APK 1 Apr 2026
- Flutter / libapp.so
- UFE_TYPE_FLOAT32
- modify float32 Value =
- WriteActuatorPeripheralCommand
- Read Actuator sent ID=
- On actuator data updated
- writeCharacteristic
- EqGraphicOnchange
- notifyEncryptionRequired / indicateEncryptionRequired
- AEADBlockCipher / ENCRYPTED_SIZE

## BLE UUID ที่ยืนยันจาก APK
- Service: 0000AB00-0000-1000-8000-00805F9B34FB
- TX: 0000AB01-0000-1000-8000-00805F9B34FB
- RX: 0000AB02-0000-1000-8000-00805F9B34FB
- Additional: 40AF0003-9479-43F6-AE95-C45FB2AFB9D2

## สิ่งที่ยังไม่ยืนยัน
A5 5A ... 16 เป็นตัวอย่างโปรโตคอล BP1048 USB จากงานวิจัยภายนอก ไม่ถือเป็น BLE packet ของ GoloPine จนกว่าจะมีหลักฐาน TX/RX จริง

## ACTUATOR LAB
หน้าใหม่ใช้สำหรับคำนวณ IEEE-754 FLOAT32 ของ Master Volume ที่ -70 ถึง +6 dB และบันทึกลง BLE LOG เท่านั้น ไม่ส่ง packet ไป DSP

## ขั้นต่อไป
ต้องจับ packet จริงของแอปผู้ผลิต (เช่น Android Bluetooth HCI snoop) ขณะเปลี่ยน Master Volume แล้วนำ packet มาเทียบกับ FLOAT32 ในหน้า ACTUATOR LAB เพื่อหา Actuator ID, framing, checksum และ encryption อย่างถูกต้อง
