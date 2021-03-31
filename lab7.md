# การทดลองที่7. _การทำงานของเซนเซอร์และส่งสัญญาณแจ้งเตือน LINE _

## วัตถุประสงค์
1. ส่งสัญญาณเตือนเมื่อมีเซนเซอร์ทำการการปิดไฟ
2. การทำงานเพื่ออาศัยเซนเวอร์เป็นตัวควบคุมการทำงาน 
3. ESP8285 มาทำการเชื่อมต่อ WiFi และส่งข้อมูลไปที่ Line ของผู้ใช้ ผ่านทาง API  โดยสามารถส่งแจ้งเตือนได้เฉพาะผู้ที่ขอใช้ หรือกลุ่มที่ผู้ขอใช้เป็นสมาชิกเท่านั้น
## อุปกรณ์ที่ใช้
1. ESP-01 (microcontrolor)
2. USB2Serial converter
3. adaptor ที่มี 2 port
4. เซนเซอร์ ไฟเลี้ยง

## ศึกษาข้อมูลเบื้อต้น
1.คำสั่งการทำงานของเซนเซอร์ https://www.myarduino.net/article/100/%E0%B8%AA%E0%B8%AD%E0%B8%99%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-arduino-%E0%B9%80%E0%B8%8B%E0%B9%87%E0%B8%99%E0%B9%80%E0%B8%8B%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%95%E0%B8%A3%E0%B8%A7%E0%B8%88%E0%B8%88%E0%B8%B1%E0%B8%9A%E0%B8%A7%E0%B8%B1%E0%B8%95%E0%B8%96%E0%B8%B8-ir-infrared
2. โค้ดดการแจ้งเตือนเข้า LINE https://www.ioxhop.com/article/47/esp8266-esp8285-%E0%B8%81%E0%B8%B1%E0%B8%9A%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%AA%E0%B9%88%E0%B8%87%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%81%E0%B8%88%E0%B9%89%E0%B8%87%E0%B9%80%E0%B8%95%E0%B8%B7%E0%B8%AD%E0%B8%99%E0%B9%80%E0%B8%82%E0%B9%89%E0%B8%B2-line
## วิธีการทำการทดลอง
1. set up port 0 เป็น input (สายไฟสีขาว) และ port 2 เป็น output (สายไฟสีเขียว) วนลูป อ่านข้อมูล digitalread จาก port 0

2. ปรมวลผลว่าถ้าผลเป็น 1 ให้ LOW ไปที่port 2 (ไฟดับ) ถ้าผลเป็น 1 ออกเป็น HIGH ไปที่ port2 (ไฟสว่าง) โดยสัญญาณ อินพุตจาก port 0 จะควบคุมให้ไฟเปิด-ปิด 
![1 loop](https://user-images.githubusercontent.com/80879653/112177448-8226df00-8c2b-11eb-8213-85b78c2b12a8.png)

3. pio run -t upload
![2  pio run](https://user-images.githubusercontent.com/80879653/112177504-923ebe80-8c2b-11eb-9131-e108e53a9768.png)
![3  กดอัพ](https://user-images.githubusercontent.com/80879653/112323210-2704f300-8ce4-11eb-9203-f0ffd1d6f2ac.png)


4. pio device mornitor
 ![4  pio mornitor](https://user-images.githubusercontent.com/80879653/112177736-c4502080-8c2b-11eb-825a-1c5fee839130.png)
5. ขึ้นเป็น read 1
 ![5 read1](https://user-images.githubusercontent.com/80879653/112177835-db8f0e00-8c2b-11eb-9350-61fc8a69992d.png)

6. สายไฟสีขาว output จิ้มไปที่ สายสีดำที่ input เป็น 0
7. outout เป็น 0 และมีไฟสว่างขึ้น เมื่อเอาสายไฟสีขาวออก หรือ จิ้มไปที่ input 1 (สายไฟสีแดง) ผลลัพธ์1 ไฟดับ
![6 สายไฟขาว ต่อจะสายไฟดำ 0](https://user-images.githubusercontent.com/80879653/112178377-43ddef80-8c2c-11eb-8d07-84690d45e4fa.png)
8. ลองกดปุ่มดูปรกฏว่าไฟสว่าง 
![7 กดปุ่มดำอ่าน0](https://user-images.githubusercontent.com/80879653/112181437-07f85980-8c2f-11eb-8309-bf032eb1a02c.png)
9. นำเซนเซอร์มาต่อกับตัวต้านทานและเอา สายไฟสีขาวที่เป็น output ต่อเข้ากับเซนเซอร์ 
![8 นำเซ้นเซอต่อกับตัวต้นทาน](https://user-images.githubusercontent.com/80879653/112181615-2c543600-8c2f-11eb-8695-e2ea000b0366.png)
![9 ไฟสีขาวต่อ](https://user-images.githubusercontent.com/80879653/112181642-31b18080-8c2f-11eb-95fb-cfbdf7f0481b.png)
10. เมื่อมีผลผลการทดลอง ออกมาเป็น 0 คือไฟสว่าง จะมีการแจ้งเตือนไปที่ แอปพลิเคชั่น line 
11. การขอ Access Token
ในการใช้งาน API ในทุก ๆ บริการ จะมีสิ่งที่เรียกว่า Access Token ไว้สำหรับเป็นรหัสที่ใช้ตอนจะเข้าใช้งาน API โดยรหัสนี้จะเป็นข้อความแทนอีเมล์ และพาสเวิคของเรา ดังนั้นหาก Access Token ถูกเปิดเผย เรายังสามารถใช้งานแอ๊กเค้าได้ปกติ (แต่หากรู้ตัวว่า Access Token ถูกเปิดเผย ควรยกเลิก แล้วขอ Access Token ใหม่ทันที)
เข้าไปที่หน้าเว็บ https://notify-bot.line.me/my/ จากนั้นระบบจะให้เราล็อกอินด้วยแอ๊คเค้า LINE โดยกรอกอีเมล์ และรหัสผ่านที่ได้ตั้งไว้ลงไป
![image](https://user-images.githubusercontent.com/80879653/113088819-97de6a80-9210-11eb-925e-213e4a039154.png)
12. พอมาถึงส่วนนี้ให้เราทำความเข้าใจก่อนว่า เมื่อเราส่งข้อความไปแล้ว ข้อความที่ขึ้นจะปรากฏในรูปแบบ

[ชื่อ Token]: [ข้อความ]

ดังนั้นในช่องที่ 1 สามารถกรอกเป็นอะไรก็ได้ และสิ่งที่กรอกนั้นจะติดไปพร้อมกับข้อความเสมอ เช่น หากกรอกว่า ESP8266 เมื่อใช้ API ส่งข้อความว่า "สวัสดี" ข้อความจะขึ้นว่า "ESP8266:สวัสดี"

ในช่องที่ 2 จะให้เลือกว่าเราจะส่งข้อความเข้าไปในกลุ่มไหน หรือส่งให้ตัวเองเท่านั้น

เมื่อกรอกครบแล้ว ให้กดปุ่ม ออก Token
![image](https://user-images.githubusercontent.com/80879653/113088864-b47aa280-9210-11eb-96d6-21d9ee6181f4.png)
13. เมื่อกดปุ่มแล้ว จะปรากฏรหัส Token ให้ท่านเก็บรหัสนี้ไว้ให้ดีเพราะจะออกให้เพียงครั้งเดียว แต่หากลืม ท่านสามารถเริ่มต้นทำขั้นตอนใหม่เพื่อขอ Token ใหม่ได้
![image](https://user-images.githubusercontent.com/80879653/113088918-cf4d1700-9210-11eb-8629-d7318a16e676.png)
14. ส่วนใน LINE ก็จะมีการแจ้งเตือนว่าออก Access Token ใหม่แล้ว
![image](https://user-images.githubusercontent.com/80879653/113088956-de33c980-9210-11eb-8520-508b59537b20.png)
15. ต่อวงจรสวิตซ์ให้ NodeMCU v1.0

ในบทความนี้จะเลือกใช้ NodeMCU เนื่องจากเป็นบอร์ดที่ค่อนข้างได้รับความนิยมเป็นส่วนใหญ่

ในการทดลอง จะใช้สวิตซ์ในการแทนเซ็นเซอร์อื่น ๆ เมื่อมีการกดสวิตซ์แล้ว จะมีการส่งแจ้งเตือนไปทาง LINE ท่านสามารถเปลี่ยนสวิตซ์เป็น PIR Sensor เพื่อตรวจจับผู้บุกรุกได้ หรือเปลี่ยนเป็นสวิตซ์แม่เหล็กติดกับประตูเพื่อแจ้งเตือนมีการเปิดประตูได้

16. Coding

ในโค้ดด้านล่างนี้ ท่านสามารถคัดลอกไปวางในโปรแกรม Arduino IDE ได้เลย แล้วแก้ไข , ให้เป็นค่าที่ถูกต้อง ส่วน ให้นำ Access Token จากในขั้นตอนที่แล้วมาวาง

void Line_Notify(String message) ;

#include <ESP8266WiFi.h>
#include <WiFiClientSecureAxTLS.h> // กรณีขึ้น Error ให้เอาบรรทัดนี้ออก

// Config connect WiFi
#define WIFI_SSID "YOUR WIFINAME"
#define WIFI_PASSWORD "YOUR WIFIPASSWORD"

// Line config
#define LINE_TOKEN "LINE ACCESS TOKEN"

#define SW D2

String message = "ไฟเปิด"; // ArduinoIDE เวอร์ชั่นใหม่ ๆ ใส่ภาษาไทยลงไปได้เลย

void setup() {
  pinMode(SW, INPUT);

  Serial.begin(9600);

  WiFi.mode(WIFI_STA);
  // connect to wifi.
  WiFi.begin(WIFI_SSID, WIFI_PASSWORD);
  Serial.print("connecting");

  while (WiFi.status() != WL_CONNECTED) {
    Serial.print(".");
    delay(500);
  }
  Serial.println();
  Serial.print("connected: ");
  Serial.println(WiFi.localIP());
}

void loop() {
  if (digitalRead(SW) == HIGH) {
    while(digitalRead(SW) == HIGH) delay(10);

    Serial.println("Enter !");
    Line_Notify(message);
    // Serial.println();
  }
  delay(10);
}

void Line_Notify(String message) {
  axTLS::WiFiClientSecure client; // กรณีขึ้น Error ให้ลบ axTLS:: ข้างหน้าทิ้ง

  if (!client.connect("notify-api.line.me", 443)) {
    Serial.println("connection failed");
    return;   
  }

  String req = "";
  req += "POST /api/notify HTTP/1.1\r\n";
  req += "Host: notify-api.line.me\r\n";
  req += "Authorization: Bearer " + String(LINE_TOKEN) + "\r\n";
  req += "Cache-Control: no-cache\r\n";
  req += "User-Agent: ESP8266\r\n";
  req += "Connection: close\r\n";
  req += "Content-Type: application/x-www-form-urlencoded\r\n";
  req += "Content-Length: " + String(String("message=" + message).length()) + "\r\n";
  req += "\r\n";
  req += "message=" + message;
  // Serial.println(req);
  client.print(req);
    
  delay(20);

  // Serial.println("-------------");
  while(client.connected()) {
    String line = client.readStringUntil('\n');
    if (line == "\r") {
      break;
    }
    //Serial.println(line);
  }
  // Serial.println("-------------");
}

17. จากนั้นอัพโหลดลง NodeMCU ไปได้เลย
![image](https://user-images.githubusercontent.com/80879653/113089071-16d3a300-9211-11eb-8d02-bd02ffe12a04.png)

การทดสอบ

หลังจาก ESP8266 เชื่อมต่อ WiFi ได้แล้ว ทดลองกดสวิตซ์ จะมีข้อความว่า "ไฟเปิด" มาปรากฏในห้องแชทของ LINE Notify เป็นอันจบการทดสอบ
![image](https://user-images.githubusercontent.com/80879653/113089083-1dfab100-9211-11eb-822e-b55e9da9a41b.png)

การแก้ไขข้อความที่ส่ง
ท่านสามารถแก้ไขข้อความได้โดยแก้ไขคำในตัวแปร message ในบรรทัดที่ 12 ได้เลย
## อภิปรายผลการทดลอง
กรทดลองนี้จะทำให้ได้ศึกษารการทำงานของเซนเซอร์ควบคุมinput เมื่อมี output ก็จะทำการเชื่อมต่อเข้าที่microcontrollor ESP-01 ที่มีการเชื่อมเข้ากับสัญญาณไวไฟ และทำการส่งการแจ้งเตือนเมื่อ เซนเซอร์มีการทำงาน output เป็น 0 ก็จะส่งเข้าไปทำห้ line ส่งการแจ้งเตือนว่าไฟเปิด  
