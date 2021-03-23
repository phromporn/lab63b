# การทดลองที่4. _เรื่อง การเขียนโปรแกรมอินพุทสัญญาณดิจิทัล_

## วัตถุประสงค์
1. นำ input ภายนอกเข้ามาใน microcontrollor 
2. สามารถดู input output ผ่านเซนเซอร์ของสภาพแวดล้อม
## อุปกรณ์ที่ใช้
อุปกรณต่อ USB
1. ESP-01 (microcontrolor)
2. USB2Serial converter
3. adaptor ที่มี 2 port
4. เซนเซอร์
ไฟเลี้ยง
## ศึกษาข้อมูลเบื้อต้น
* การใช้งาน platformio https://platformio.org/
* การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
* เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
* การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
* การใช้เซนเซอร์ http://horizon.sti.or.th/node/53
## วิธีการทำการทดลอง
1. set up port 0 เป็น input (สายไฟสีขาว) และ port 2 เป็น output (สายไฟสีเขียว) วนลูป อ่านข้อมูล digitalread จาก port 0

2. ปรมวลผลว่าถ้าผลเป็น 1 ให้ LOW ไปที่port 2 (ไฟดับ) ถ้าผลเป็น 1 ออกเป็น HIGH ไปที่ port2 (ไฟสว่าง) โดยสัญญาณ อินพุตจาก port 0 จะควบคุมให้ไฟเปิด-ปิด 
![1 loop](https://user-images.githubusercontent.com/80879653/112177448-8226df00-8c2b-11eb-8213-85b78c2b12a8.png)

3. pio run -t upload
![2  pio run](https://user-images.githubusercontent.com/80879653/112177504-923ebe80-8c2b-11eb-9131-e108e53a9768.png)
![3  กดอัพ](https://user-images.githubusercontent.com/80879653/112177532-99fe6300-8c2b-11eb-9ebc-0f9e47bc1264.png)

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


## การบันทึกผลการทดลอง
การเขียนโปรแกรมอินพุทสัญญาณดิจิทัลเมื่อ run โปรแกรมจะขึ้นเป็น 1 (off ไฟดับ) แต่เมื่อลองต่อไฟสีขาว output กับพอตสีดำแล้วกดปุ่มไฟจะสว่าง (on) และเมื่อลองทดสอบกับเซนเซอร์ต่อกับตัวต้านทานแล้วต่อ output พบว่าเมื่อเอามือบังเซนเซอร์ ไฟจะดับ และเอามือออกไฟจะสว่าง
## อภิปรายผลการทดลอง
เมื่อเรากำหนดโปรแกรมให้ output ขึ้นอยู่กับ input เมื่อนำ input(สายไฟสีขาว)ไปต่อเข้ากับ เอ้าท์พุต 1 ที่ให้ผลลัพธ์คือไฟดับ และมื่อนำไปต่อกับ เอ้าท์พุต 0 ผลลัพธ์คืออหลอดไฟสว่าง และเมื่อทดลองนำเซนเซอร์มาต่อเข้ากับตัวต้านทานและไมโครคอนโทลเลอร์ พบว่าหากนำมือไปปิดเซนเซอร์ไฟจะดับ(1) เพราะมีความต้านทานมาก และเมื่อปล่อยมือออกไฟจะสว่าง(0) เพราะมีตัวต้านทานน้อย
## คำถามหลังการทดลอง
