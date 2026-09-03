# v2.4.5 – แก้ Master Slider
- ลาก Master slider แล้วสั่ง Android/Bluetooth STREAM_MUSIC โดยตรง
- ถ้า setStreamVolume ถูกละเลยโดยเส้นทาง Bluetooth/Samsung จะ fallback ด้วย ADJUST_RAISE/LOWER
- เมื่อปล่อย slider จะ sync ค่า dB กลับจาก Android volume จริง
- Master Android/Bluetooth link เปิดตลอด
- ยังไม่ส่ง DSP packet ที่เดาเอง เพราะ protocol OEM ยังไม่ยืนยัน
