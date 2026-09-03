# v2.3.6 ROOT BUILD FIX

แก้ปัญหา GitHub Actions ที่พยายาม build จาก `DSP_OKN/DSP_OKN` แล้วหา settings.gradle ไม่เจอ

รุ่นนี้ไม่ hard-code ชื่อโฟลเดอร์ใด ๆ โดย workflow จะค้นหาโฟลเดอร์ที่มีทั้ง:
- settings.gradle หรือ settings.gradle.kts
- app/build.gradle

จากนั้นใช้ `gradle -p <project> :app:assembleDebug`

แนะนำให้เอา **ไฟล์และโฟลเดอร์ทั้งหมดภายใน ZIP** ไปไว้ที่ root ของ repository โดยตรง แต่แม้จะมีโฟลเดอร์ซ้อน workflow ก็จะค้นหาให้
