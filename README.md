<center><img src="https://svg-banners.vercel.app/api?type=glitch&text1=GATE LOCK&width=800&height=200" alt"title"></center>

---

# What is gate lock?

Are you looking to lock your door + take attendance in some cloud storage so that you make sure your office is secure and attendance is retrieved without any hassle?

This project aims at solving this problem by using ESP8266 microcontroller and MFRC522 RFID Reader/Writer + buzzer and lock.

# Required Tools

1. ESP8266 based micro-controller [In this project - Wemos D1 R2]
2. MFRC522 RFID module
3. OLED Display
4. Buzzer
5. Gate Lock
6. LEDs
7. Wire
8. Casing

# Intial Setup

- MFRC522 connected to wemos d1 with this scheme:

| MFRC522 | Wemos D1 R2           
| ------- |:-------------:
| 3.3v    | 3.3v 
| RESET   | D3      
| GND     | GND
| MISO    | D6
| MOSI    | D7
| SCK     | D5
| SDA     | D8      

- OLED connected to wemos d1 with this scheme:

| OLED    | Wemos D1 R2           
| ------- |:-------------:
| GND     | GND 
| VCC     | 5v      
| SCL     | SCL
| SDA     | SDA

# To take data in tabular form in Google Docs

1. Make 2 blank sheets
    - Name one as log and other as main
2. Open main sheet
3. Navigate to tools --> Script Editor
4. Copy from `script.js` to this script editor and change following
    - `timeZone="YOUR_TIME_ZONE";` In case of India, it will be IST
    - `logSpreadSheetId="log_sheet_id";` Here enter id of sheet named log made earlier in step 1 which will look like `1easdasdip-O5wxABsHiDap0YV-lDXQ_U4y6y8tuvueM1` like this
5. Now navigate to publish --> deploy as web app and follow on screen instructions.
 - Give access to anyone
6. Copy web app URL that contains ID for connection to google sheet.

Further step will be take place in arduino code

# Arduino Code

All big thanks to [unreeeal](https://github.com/unreeeal) for starting code/video tutorial.

There are some changes to make code work for you:
1. `const char* ssid = "YOUR_SSID_HERE";`
2. `const char* password = "YOUR_WIFI_PASSWORD";`
3. `String GOOGLE_SCRIPT_ID = "ENTER_WEB_APP_URL_ID"` which will look something like this `AKfycJIasdasddfyGQy9DZ1xhtnjTbyECKnm6POfHcscCBfWU_bIdZprPk`
4. Other changes might be due to hardware changes and other changes are mentioned in code itself.
5. Once everything is ready, read blank cards and data will log in log sheet made in earlier steps.
6. Copy Card UID to main sheet to make them authenticated and give suitable name for data.

# Hardware

Make 3D printed case or use old cardboard box and use suitable screw-bolt comination to make rigid connections and enhance aesthetics.

<center><img src="https://svg-banners.vercel.app/api?type=glitch&text1=DISCLAIMER&width=800&height=100" alt"title"></center>

# This project is for DIY lock/attendance system, do not use this project for applications requring high security.
