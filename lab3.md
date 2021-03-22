# การทดลองที่3. _การเขียนโปรแกรมเอ้าพุทสัญญาณดิจิทัล_

## วัตถุประสงค์
1.เพื่อเขียนโปรแกรมการส่งออกเอ้าพุทใน pot0
2.ศึกษาภาษา C ในการเขียนโปรแกรม output
## อุปกรณ์ที่ใช้
1. อุปกรณต่อ USB
2. ESP-01 (microcontrolor)
3. USB2Serial converter
4. adaptor ที่มี 2 port 
## ศึกษาข้อมูลเบื้อต้น
* การใช้งาน platformio https://platformio.org/
* การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
* เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
* การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
## วิธีการทำการทดลอง
1.ทำการต่อ adaptor เข้ากับ USB2Serial converter และ microcontrollor ESP-01 เนื่องจากส่งออกข้อมูลทางport 0
![1](https://user-images.githubusercontent.com/80879653/111967951-37be3900-8b2b-11eb-859d-2fb92a257cb2.png)
![2 adatop](https://user-images.githubusercontent.com/80879653/111968168-76ec8a00-8b2b-11eb-976b-60961352996c.png)

2. adaptor มี output 2 ช่องทางคือ port0 ที่มีoutput  เป็นหลอดไฟสีเขียว และ port1 ที่มีหลอดไฟสีน้ำเงิน
![3 adaptor แบ่ง2 port](https://user-images.githubusercontent.com/80879653/111968197-7ce26b00-8b2b-11eb-9720-bf285dd0acc2.png)
![4 ต่อmicro](https://user-images.githubusercontent.com/80879653/111968443-bca95280-8b2b-11eb-9bed-1598b1ce050d.png)

3.เปิดโฟเดอร์แล้วเข้าไปที่คสั่งเพื่อที่จะลงโปรแกรมใน microcontrollor ESP-01 พบว่ามี 2 คำสั่งการ คือ set ให้port 0 เป็นoutput และวนลูปไปทุกๆครึ่งวินาที (500ms)
![5 หน้าโปรแกรม](https://user-images.githubusercontent.com/80879653/111969219-92a46000-8b2c-11eb-804b-d044cbe22bba.png)
4. pio run t- upload
![pio run device](https://user-images.githubusercontent.com/80879653/111969311-abad1100-8b2c-11eb-8931-81ffde63618e.png)
5.pio divice mornitor เพื่อแสดงผล
![จะเปล่งแสงตอนon](https://user-images.githubusercontent.com/80879653/111969575-fb8bd800-8b2c-11eb-821c-3e3d105d88c1.png)

## การบันทึกผลการทดลอง
 out put ที่ต่อเข้ากับ port 0 จะแสดงผลลัพธ์ค่าศุงสุดทุกการนับcount เลขคี่(on) หรือหลอดไฟสีเขียวจะติดไฟ และ ผลลัพธ์ต่ำสุดทุกการนับต่ำสุดทุกการนับcount เลขคู่(off) หรือหลอดไฟสีเขียวจะดับ โดยผลลัพธ์ทั้งสองจะสลับกับทุกๆ1 วินาที สังเกตได้ว่าหลอดไปสีน้ำเงินไม่มีแสดงผลเนื่องจาก โปรแกรมที่เขียนสั่งให้แสดงผลแค่ port 0 เท่านั้นคือ หลอดไฟสีเขียว
 ## อภิปรายผลการทดลอง
 การเขียนโปรแกรมเอ้าพุทสัญญาณดิจิทัลต้องการต่อเข้ากับadaptor ก่อนต่อเข้ากับmicrocontollorโดยตรงโดย outputจะแสดงผลลัพธ์ที่ adaptor ที่มีหลอดไฟเป็นตัวแสดงผลลัพธ์ให้เห็น และมีการเซตการทดลองให้โปรแกรมส่งออกoutput ที่port 0 เพียงอย่างเดียวนั้นคือส่งผลลัพธ์ออกทางหลอดไฟสีเขียว
## คำถามหลังการทดลอง
