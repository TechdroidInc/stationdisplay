# BLe Configuration

The Station Display uses standard bluetooth characteristics for configuration. An App like nRF Connect can be used instead of the official app the configure the device.

Station Display Service ID: "d29a9c37-c13b-4ed4-8c68-1e3f1d3854e8"

Here is the current characteristics list:

| characteristics | type | format | description |
|------------|------------|------------|------------|
| 4b02f36a-f7e6-45a8-a7a1-f0c2c3665881 | READ | text | Device Serial |
| 21a54a59-b503-43f8-b75b-5a8e0024a174 | READ | text | Hardware Version |
| 41b22899-009e-4dad-ad8b-cd02c66e4f82 | READ | text | Version |
| 75e82c97-dc7e-4834-963b-37a0beb5ad64 | READ/WRITE | text | Wifi SSID |
| ee90cd40-9672-4de6-8013-47d5352d6f6c | WRITE | text | Wifi Password |
| f9cdc6b4-ed49-4c99-860b-5fad34265f50 | READ/WRITE | text (1 = default, 2 = with title bar, 3 = High contrast, 4 = high contrast with title bar) | Theme |
| b26f2ee4-5ccb-4243-8d50-3cb6183e0e9b | READ/WRITE | text | Station Id |
| 9f0eedb3-02dd-4009-a99d-cea6180da13f | READ/WRITE | text (A = All, R = In, H = Out) | Station Direction |
| eb438a8c-e9f5-44e5-bbec-12e370097882 | WRITE | text | Trigger Reboot if required (Will trigger a reboot if any settig was changed that requires a reboot to take effect) |
| c9d09e31-fa6c-4237-bfb4-2477407ad7d6 | READ/WRITE | text (de-CH, fr-CH, it-CH, en-US) | Language |
| bc6d40d0-745a-4799-8bcb-2acfe17ebe56 | READ/WRITE | text | Bluetooth Device Name |
| 4f709081-6ad4-443f-b67b-d9cf81dd5bcf | READ/WRITE | text (A, 0-255) | LCD Brightness |
| 4cddf99a-49d0-11ee-be56-0242ac120002 | READ/WRITE | int (1 = disabled, 2 = enabled) | BLe Auto Off, for security this should be left disabled |
| 35e327fa-33aa-4c05-ae7b-8c0c1cbbdefa | READ | text | Wifi Signal |
| 64ba442f-a956-4715-8d93-ef4d7ff86f37 | READ | text | Wifi Status |
| 80fd2b0d-5ed0-4e17-8ca5-e76dae36eaa1 | READ/WRITE | text (1 = Auto, 2 = off, 3 = scroll, 4 = full screen) | Alert Mode |
| 3c760a76-d46d-412c-8a2a-60f4ae84e4cb | READ/WRITE | text | API Url (default = https://api.stationdisplay.com/station/departure-arrival) |
| 4d62760b-2221-457c-beb3-f0ac3191d7de | WRITE | text | Check for OTA |



