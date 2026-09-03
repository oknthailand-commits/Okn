# v2.4.2 OEM Crypto Engine

เพิ่ม transport facts ของ GoloPine ที่ยืนยันจาก HCI: AB00/AB01/AB02 และ TX handle 0x0006.
เพิ่ม AES-GCM helper สำหรับขั้นตอนถอดรหัสที่ต้องใช้ session key จริงจาก OEM handshake.
ไม่มีการฝังคีย์ลับหรือส่ง packet เดาสุ่มไปยัง DSP.

สถานะ: BLE connection/UI ใช้งานได้; hardware actuator write ของ GoloPine ยังต้องได้ session/key mapping ที่ถูกต้องก่อนเปิดใช้งานจริง.
