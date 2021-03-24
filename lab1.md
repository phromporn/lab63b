# การทดลองที่1. _เรื่อง การเขียนโปรแกรมเพื่อรันบนไมโครคอนโทรเลอร์_

## วัตถุประสงค์
1. เข้าใจองค์ประกอบพื้นฐานของวงจรสมองกลฝังตัว
2. ทดลองต่อวงจรไมโครคอนโทรเลอร์อย่างง่ายโดยใช้ชิพไมโครคอนโทรเลอร์ตระกูล ESP-01 เป็นกรณีศึกษา
3. เข้าใจหลักการติดตั้ง Firmware ลงในไมโครคอนโทรล์เลอร์ผ่าน Hardware Programmer และผ่าน Bootloader
4. ได้ทดลองเขียนโปรแกรมภาษา C ในการควบคุมการทำงานของวงจรในเบื้องต้น

## อุปกรณ์ที่ใช้
1. อุปกรณต่อ USB
2. ESP-01 (microcontrolor)
3. USB2Serial converter

## ศึกษาข้อมูลเบื้อต้น
* การใช้งาน platformio https://platformio.org/
* การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
* เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
* การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198

## วิธีการทำการทดลอง
 * การเขียนโปรแกรมเพื่อรันบนไมโครคอนโทรเลอร์ ต่อmicrocontrollor กับ USB เชื่อมเข้ากับคอมพิวเตอร์เพิ่เขียนโปรแกรมรันบน ESP-01 
 ![microcontrollor ](https://user-images.githubusercontent.com/80879653/111916742-06078c80-8aaf-11eb-9f64-52493c9adb5d.jpg)
![S__2433184](https://user-images.githubusercontent.com/80879653/111916643-74981a80-8aae-11eb-9cc3-c3861b5cc43a.jpg)

 * ทำการเปิดโพเดอร์เพื่อที่จะรันโปรแกรมภาษาซีภายใน

 * เขียนโค้ดภาษา C โดยโค้ดจะมี2ลูป
  ![S__2433182](https://user-images.githubusercontent.com/80879653/111916809-54b52680-8aaf-11eb-9c8a-01fec6e87ef5.jpg)
 * pio run เพื่ออัปโหลดโปรแกรมลงใน ESP-01 
 ![S__2433180](https://user-images.githubusercontent.com/80879653/111916856-8928e280-8aaf-11eb-96c8-60e0fb7c6ff6.jpg)

 * เมื่อสำเร็จ ทำการ pio divice monitor เพื่อแสดงผล
![1](https://user-images.githubusercontent.com/80879653/111916941-ecb31000-8aaf-11eb-8332-e37ab026b35c.png)

## การบันทึกผลการทดลอง
ค่าที่รันออกมาจาก ESP-01 จะเป็นค่าcount ที่นับไปเรื่อยๆโดยมีระยะห่างที่1 วินาที เมื่อกดปุ่มรีเซ็ตก็จะมีการเริ่มนับ 1ใหม่
 
## อภิปรายผลการทดลอง
ค่าโปรแกรมที่รันผลอกมาจะเป็นโปรแกรมที่ถูกเขียนจากภาษาซีจากคอมพิวเตอร์แล้วนำมาลงใน microcontrollor ในการทดลองนี้คือESP-01  แล้วนำมาประมวลผลรันค่าที่ได้ออกมา
 

## คำถามหลังการทดลอง
ถ้าต้องการให้มีการนับที่ไวขึ้นต้องทำอย่างไร
* ปรับ delay ตามที่เราต้องการ
