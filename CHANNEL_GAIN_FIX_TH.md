# v2.4.7 — CH1–CH7 ปุ่ม +/− และ Fader Fix

- เพิ่มปุ่ม `−` และ `+` สำหรับ CH1–CH7 ปรับทีละ 1 dB
- ลาก Fader แล้วตัวเลข CH อัปเดตทันที
- ปล่อย Fader แล้วบันทึกค่า local และเขียน BLE log
- ขอบเขต -60 ถึง +6 dB
- สำคัญ: ค่าดังกล่าวยังเป็น local UI/profile; การเขียน DSP hardware จริงยังรอการยืนยัน GoloPine encrypted packet mapping
