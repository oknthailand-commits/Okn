# v2.4.4 MASTER PACKET LAB

รุ่นนี้ต่อจาก v2.4.3 เพื่อหาคำสั่ง Master Volume ของ GoloPine จาก packet จริง โดยไม่ส่ง packet เดาสุ่ม

## วิธีใช้กับมือถือ
1. เปิดแอป GoloPine ตัวเดิม
2. เปิด Bluetooth HCI snoop log บนเครื่อง Samsung
3. ปิด/เปิด Bluetooth ใหม่ แล้วเชื่อมต่อ DSP
4. ทำ capture ชุด BEFORE: เชื่อมต่อแล้วอย่าเปลี่ยนค่า Master
5. ทำ capture ชุด AFTER: กด Master ใน GoloPine 1 ครั้งเท่านั้น แล้วรอ 3–5 วินาที
6. เปิดแอป BP1048P4 DSP PRO 2.4.4
7. เข้า MASTER PACKET LAB
8. เลือก BEFORE และ AFTER แล้วกด เปรียบเทียบ
9. ผลลัพธ์จะแสดง payload ของ AB01/handle 0x0006 ที่เปลี่ยน

จากนั้นนำผลลัพธ์กลับมาให้ผม เพื่อระบุ mapping ของ Master และทำ LIVE DSP WRITE ต่อ

## ความปลอดภัย
- รุ่นนี้ไม่ส่ง packet ที่คาดเดาไปยัง DSP
- A5 5A เป็น protocol ที่พบจาก USB research และยังไม่ถือว่าเป็น GoloPine BLE protocol
- packet 13 bytes ที่พบก่อนหน้านี้ยังไม่ถือว่าเป็น Master จนกว่าจะยืนยันด้วย differential capture
