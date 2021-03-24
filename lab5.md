# การทดลองที่5. _ การเขียนโปรแกรมเชื่อมต่อไวไฟและเว็บเซอร์เวอร์_

## วัตถุประสงค์
เขียนโปรแกรมเชื่อมต่อไวไฟทำหน้าที่ทดสอบ web เบราเซอร์
## อุปกรณ์ที่ใช้
1. ESP-01 (microcontrolor)
2. USB2Serial converter

## ศึกษาข้อมูลเบื้อต้น
1. การใช้งาน platformio https://platformio.org/
2. การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
3. เรียนรู้ ESP-01 https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
4. การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
5. run wifi https://www.youtube.com/watch?v=VX-QNQcO-b4&feature=youtu.be
## วิธีการทำการทดลอง 
1. เปิดตัวอย่างโปรแกรมที่5
2. เนื่องจากต้องเชื่อมต่อกับไวไฟ ต้องใส่ชื่อไวไฟ และรหัสผ่าน ดังรูป
![1   coad](https://user-images.githubusercontent.com/80879653/112203861-91b32180-8c45-11eb-92b0-54bb56147253.png)
![Uploading 2. set up.png…]()
3. โปรแกมมี2 ส่วนคือ set up เป้นการเชื่อมต่อไวไฟที่เลือกไว้ เซตอับเว็บเซฟ โดยจะแสดงผลเป็ฯ hello cnt โดยแสดงผลเพิ่มละ 1 เรื่อยๆ 
![3](https://user-images.githubusercontent.com/80879653/112204122-e6ef3300-8c45-11eb-822d-7b548aacb567.png)
4. pio -t upload อัปโหลดโปรแกรมไว้ที่ microcotrollor โดยเสียบไปที่ USB2Serial converter และทำการกดปุ่ม เพื่ออัปโหลด
![4](https://user-images.githubusercontent.com/80879653/112204250-08e8b580-8c46-11eb-969f-2bdc316aab27.png)
![5 เสียบไมโคกับUSB2](https://user-images.githubusercontent.com/80879653/112204386-2f0e5580-8c46-11eb-9857-caf37a9c0e55.png)
![6 กดอับโหลดโปรแกรม](https://user-images.githubusercontent.com/80879653/112204394-30d81900-8c46-11eb-8a50-3194d9dcc8f4.png)
5. ทดสอบโดย เข้า เวบเบราเซอร์
![7  ทดสอบไวไฟ](https://user-images.githubusercontent.com/80879653/112204496-4e0ce780-8c46-11eb-96d2-0a1b8319ae2e.png)




## การบันทึกผลการทดลอง
ทดลองเข้าเวปเบราเซอร์เพื่อทดสอบไวไฟที่่ทำการเชื่อมไวไฟ
## อภิปรายผลการทดลอง
เมื่อทำการอับโหลดโปรแกรมลง ไมโครคอนโทลเลอร์แล้ว ทำการเชื่อมต่อกับไวไฟที่กำหนด พบว่าสามาถเข้าเว็บได้ หมายถึงต่อไวไฟสำเร็จและสามารถใช้งานอินเตอร์เน็ตได้
## คำถามหลังการทดลอง
หากทำการเปลี่ยนไวไฟการเชื่อมต่อจะเกิดอะไรขึ้น
* หากเปลี่ยนไวไฟจะต้องกรอกข้อมูลรหัสไวไฟ และเชื่อมต่อเบราเซอร์ได้ขึ้นอยู่กับอินเตอร์เน็ตของผู้ให้เชื่อมต่อ
