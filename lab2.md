# การทดลองที่2. _การเขียนโปรแกรมค้นหาไวไฟ_

## วัตถุประสงค์
1. เพื่อใช้ในการค้นหาไวไฟรอบๆ
2. 
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
1. เตรียมอัปโหลดโปรแกรมลง microcontrollor  มี2 ส่วน คือส่วนset up wifi และส่วน loop วนเมื่อมีไวไฟ
![1 set ระบบ](https://user-images.githubusercontent.com/80879653/111917477-c8a4fe00-8ab2-11eb-98fa-1d8bce043554.png)
2. รออัปโหลดโปรแกรมจนครบ แล้วรัน pio device mornitor 
![pio device](https://user-images.githubusercontent.com/80879653/111917498-e5d9cc80-8ab2-11eb-881e-f6024f087761.png)

3. จะแสดงผลกรค้นหาไวไฟรอบๆจะเห็นได้ว่าบางครั้งปรากฏ 2-4ตัว ขึ้นอยู่กับความแรงของสัญญาณที่ได้รับ 
![ผลลัพธ์การเจอไวไฟ](https://user-images.githubusercontent.com/80879653/111917532-06a22200-8ab3-11eb-9b60-d4ebdaf34a03.png)

4. ทดลองกดปุ่ม รีเซ็ตเพื่อรีเซ็ตการค้นหาไวไฟ
![ผลลัพธ์การเจอไวไฟ](https://user-images.githubusercontent.com/80879653/111917547-20436980-8ab3-11eb-8c5d-3590a3624f32.png)

## การบันทึกผลการทดลอง
การทดลองค้นหาไวไฟบริเวณรอบๆ microcontrollor ปรากฏว่าบางครั้งพบ 2ตัว บางครั้งพบ 4ตัว ขึ้นกับความแรงของสัญญาณที่ได้รับ จากที่ปราฏกให้เห็นจะมี MASTER BEDROOM 2.4GHz (-89),TEN (-80) , Homiebody(-90) เป็นต้น
## อภิปรายผลการทดลอง
การทดลองค้นหาสัญญาณไวไฟบริเวณรอบๆพบว่ามีข้อผิดพลาดในการต่อวงจรทำให้วงจรไม่สมบูรณ์ในตอนแรกจึงต้องทำการต่อให้และรันโปรแกรมใหม่ เพื่อให้ได้ผลลัพธ์ตามที่ต้องการ โดยโปรแกรมที่เขียนจะให้เป็นภาษา C ซึ้งต้องเขียนนออกมา 2loop คือใช้ในการset up และ loop ใช้ในการค้นหาไวไฟไปเรื่อยๆ
## คำถามหลังการทดลอง