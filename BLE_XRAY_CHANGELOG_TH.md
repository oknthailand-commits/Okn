# v2.3.2 BLE X-RAY
- Enumerates every GATT service/characteristic and properties.
- Sequentially enables every NOTIFY/INDICATE characteristic with a CCCD.
- Sequentially reads every READ characteristic after notify setup.
- Logs TX, RX, CCCD callbacks and read values.
- Avoids descriptor/read concurrency that can cause GATT busy.
- This is for discovering the real GoloPine BLE behavior; it does not claim EQ byte mapping yet.
