# v2.3.9 Volume Probe

เพิ่มหน้า VOLUME PROBE เพื่อแยก Android Media Volume event ออกจาก DSP BLE packet

- ใช้ AudioManager STREAM_MUSIC
- ปุ่ม Volume Up/Down แสดง Android volume UI และบันทึก before/after
- ContentObserver บันทึกการเปลี่ยนแปลง volume ที่ตรวจพบ
- ไม่มีการส่ง DSP packet จากหน้า Volume Probe
- ไม่สามารถดัก packet BLE ของแอปผู้ผลิตโดยตรง

วัตถุประสงค์: ใช้เป็นเครื่องมือประกอบการ reverse engineering; packet จริงต้องมาจาก HCI snoop/การวิเคราะห์ APK/firmware
