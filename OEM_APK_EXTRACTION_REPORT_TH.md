# GoloPine OEM APK – Extraction Report

ตรวจจาก APK ที่ผู้ใช้ให้มา: `APP Android golopine_audio_turning_1Apr2025.apk`

## พบหลักฐาน
- เป็น Flutter Android app (`lib/arm64-v8a/libapp.so`)
- พบ BLE service/characteristic:
  - `0000AB00-0000-1000-8000-00805F9B34FB`
  - `0000AB01-0000-1000-8000-00805F9B34FB`
  - `0000AB02-0000-1000-8000-00805F9B34FB`
- พบ UUID เพิ่มเติม:
  - `40af0001-9479-43f6-ae95-c45fb2afb9d2`
  - `40af0002-9479-43f6-ae95-c45fb2afb9d2`
  - `40af0003-9479-43f6-ae95-c45fb2afb9d2`
- พบ string ที่เกี่ยวข้องกับ BLE:
  - `writeCharacteristic`
  - `readCharacteristic`
  - `setNotifyValue`
  - `OnCharacteristicReceived`
  - `OnCharacteristicWritten`
  - `Matched Writing Characteristic`
  - `Matched Reading Characteristic`
  - `Listen to Notify`
- พบ string ที่เกี่ยวข้องกับ DSP:
  - `EqGraphicOnchange`
  - `UFE_TYPE_BIQUAD_CASCADE`
  - `Parse BiquadFilter failed`
  - `modify float32 Value`
  - `Read FIFO Sensor`
  - `Start Decoding device description`
- พบลายเซ็นไบต์ `A5 5A ... 16` ใน `libapp.so`

## สิ่งที่ยังไม่ควรสรุป
การพบ `A5 5A` ใน binary ไม่ได้หมายความว่าเฟรมทุกตำแหน่งเป็นคำสั่งปรับ EQ โดยตรง เพราะบาง occurrence อยู่ใน native code/data ที่ต้องวิเคราะห์บริบทต่อ

## แผนพิสูจน์ mapping
1. เชื่อมต่อ `LE-GoloPine_DSP_A`
2. จับ RX จริง
3. ตั้งค่าในแอปผู้ผลิต 1 ค่า เช่น Master Volume
4. จับ packet ก่อน/หลัง
5. เปลี่ยนทีละ 1 ค่า แล้วหา byte ที่เปลี่ยน
6. ทำซ้ำกับ EQ band, Q, frequency, crossover, delay
7. เมื่อยืนยันแล้วจึงนำ mapping เข้า controller ของเรา

รุ่นแอปนี้เพิ่มหน้า `OEM PROTOCOL` เพื่อแสดงหลักฐานที่แกะได้และยิงคำสั่งทดสอบโดยไม่อ้างว่า mapping เสร็จแล้ว
