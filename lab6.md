# การทดลองที่6. _การเขียนโปรแกรมสร้างไวไฟแอคเซสพอยต์ (Wifi AP)_

## วัตถุประสงค์
1. สามารถต่อไวไฟที่เราสร้างขึ้นมาเองได้จากโทรศัพท์มือถือ 
## อุปกรณ์ที่ใช้
1. ESP-01 (microcontrolor)
2. USB2Serial converter
## ศึกษาข้อมูลเบื้อต้น
1. การใช้งาน platformio https://platformio.org/
2. การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
3. เรียนรู้ ESP-01 https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
4. การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
5. 06 run wiri AP https://www.youtube.com/watch?v=T26DVHePlTs
## วิธีการทำการทดลอง
1. เปิดโปรแกรม ตัวอย่างที่6 
2. สร้างชื่อไวไฟและรหัสผ่าน ดังรูป
3. กำหนด IP Address ในตัวESP-01
4. สร้าง access point โดยrun WiFi.softAP กำหนด ssid และ password 
![8](https://user-images.githubusercontent.com/80879653/112207571-e22c7e00-8c49-11eb-81d6-41c4e967b8ca.png)
5. pio run -t upload
![9](https://user-images.githubusercontent.com/80879653/112208035-739bf000-8c4a-11eb-8f27-6adedf3731ed.png)
6. กดปุ่ม set เพื่อ upload
![10](https://user-images.githubusercontent.com/80879653/112208088-86162980-8c4a-11eb-952d-fcc508dcd191.png)
7. pio device mornitor
![11](https://user-images.githubusercontent.com/80879653/112208315-cb3a5b80-8c4a-11eb-8569-fa84f6c5dadc.png)
8. ใช้คอมพิวเตอร์ชคการเชื่อมจากโทรศัพท์ค้นหาไวไฟจาก EPS-01
![12](https://user-images.githubusercontent.com/80879653/112208673-32581000-8c4b-11eb-8132-0b27191109b6.png)



## การบันทึกผลการทดลอง
การทดสอบโดยการเชื่อต่อไวไฟทางโทรศัพท์ ทำการใส่รหัสผ่านและเข้าใช้งานอินเตอร์เน็ตได้
## อภิปรายผลการทดลอง
การเขียนโปรแกรมสร้างไวไฟแอคเซสพอยต์ (Wifi AP) โดยเราทำการสร้างไวไฟจาก ESP-01 โดยเปลื่อยชื่อเป็นชื่อที่ต้องการและกำหนดรหัสผ่านตามที่กำหนด โดยเราจะกำหนด IP Address และ สร้าง access point 
การทดสอบโดยการเชื่อต่อไวไฟทางโทรศัพท์ ทำการใส่รหัสผ่านและเข้าใช้งานอินเตอร์เน็ตได้
## คำถามหลังการทดลอง
หากเราทำการเปลี่ยน IP Address จะให้ให้เกิดอะไรขึ้น
ตอบ อาจจะทำให้เกิดการกระจายไวไฟได้ตาม IP Address ที่เรากำหนด
