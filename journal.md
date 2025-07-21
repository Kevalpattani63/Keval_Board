---


Title: “Aesthetic Keyboard Build”
Total Time Logged: 22 hours
Author: Keval
Description: A clean, minimal custom keyboard with rotary encoders and OLED. Designed entirely from scratch.


---

## Day 1 – July 17  Tthe Schematic Start (4 hours)
So I was just chilling with lo-fi beats on the speaker and scrolling through keyboard setups on Pinterest, and damn those minimal boards just hit different. No RGB naach gaana, no extra keys everywhere. Just that clean, sharp layout and a few clever upgrades. I immediately opened my sketchpad and started roughing out something simple and elegant. Not overkill, but still solid for daily typing and coding. I knew I wanted rotary encoders on the top right, because volume and scrolling should be knob-controlled, bro. Also, an OLED screen for some nice touch—a clock, layer display, or even a little animation. The main layout was around 65%, but cleaner—no extra gaps, no clutter.

---

<img width="433" height="361" alt="image" src="https://github.com/user-attachments/assets/0e0c89ea-a2b3-4338-be55-e84dba2c3e89" />

---


Then I jumped into EasyEDA and started building out the schematic. I laid down the Pro Micro clone first like always, it's the backbone. Next, I placed a 9-row, 6-column matrix. Switches all got diodes 1N4148s, standard. I used SW footprints labeled neatly and began routing each row and column connection logically. Took time, but I wanted it to be sahi from the start. Ended the night with the first version of the schematic mostly wired. Phew, brain fried but excited.

---


<img width="399" height="352" alt="image" src="https://github.com/user-attachments/assets/f0f9bb5d-a90a-420a-a91f-fb79a9326195" />



---



<img width="485" height="351" alt="image" src="https://github.com/user-attachments/assets/4dc71d7b-378c-4707-ba6d-4c19458ae740" />




---




---

<img width="1194" height="442" alt="image" src="https://github.com/user-attachments/assets/f979468d-7656-4da1-acf9-a5c0a5154cd1" />


---


## Day 2 – July 18  Finishing the Schematic & Encoder Logic (5 hours)
Today was all about refining. I started with the encoder section. I had placed two EC11 rotary encoders in the schematic yesterday, but now I had to hook them up properly. I assigned three pins for each A,B Classic setup, but works every time. I took extra care that the encoder push-buttons didn’t share switch matrix lines those need direct GPIO access.

---

<img width="721" height="292" alt="image" src="https://github.com/user-attachments/assets/fce2d37d-c7f3-4211-af8c-8860e559f684" />





---

After this, I worked on the OLED part. The 0.91" display uses I²C, so just SDA and SCL from the Pro Micro. I added two pull-up resistors (10kΩ again) and made sure the power line was clean, with a 100nF decoupling cap between VCC and GND. Routing all that on schematic level looked solid by now. I ran ERC once and got like 4 warnings, mostly unconnected pins—I fixed all of them by evening.

---

<img width="621" height="398" alt="image" src="https://github.com/user-attachments/assets/6fa17394-c47d-4224-8f9a-b122afe2578d" />



---


---


<img width="897" height="585" alt="image" src="https://github.com/user-attachments/assets/3eecb6fd-4fc8-4fea-b9fe-0dcbe11c8470" />


---




Closed the schematic tab with a smile. Board’s brain was officially sorted.



## Day 3 – July 19  PCB Layout  (5 hours)
Aaj ka mission was PCB layout. Imported my schematic netlist into the PCB editor. Saw the messy cloud of footprints floating—pure chaos, but also kinda satisfying. I started anchoring the switch matrix first. Took some time to get alignment right. I set grid snapping to 19.05 mm to match the standard key spacing and then laid out all the switches row by row. Each switch footprint also had holes for the hot-swap sockets honestly, best decision ever. No soldering switches, just plug-n-play.

Then came the diodes. I placed them nice and close to the switch pads, all facing the right direction. Diode orientation is a headache if you mess it up, so I triple-checked it. I started routing the rows first, used top layer with 10mil traces. It was a bit tight near the corners, but managed to snake everything around cleanly.

I left enough spacing for keycaps to travel without interference, and before logging off, I exported a 3D preview to just vibe. The layout looked clean, neat, no overlapping signals or weird trace angles. So satisfying.


---

<img width="884" height="413" alt="image" src="https://github.com/user-attachments/assets/d2438325-de99-4ba7-8d9b-6e28d7a80178" />

---


## Day 4 – July 20  Routing Columns, OLED, and Encoders (4 hours)
Today’s grind was intense. I focused completely on the bottom layerspecifically routing all the columns. It’s a 6-column design, and routing them through the tight switch grid was like playing Tetris in real life. I used 10mil traces again, switching layers only when absolutely needed with vias. Didn’t want too many drill holes cluttering the board. Each column line had to weave between the switches, avoid diode pads, and land on the right GPIO on the Pro Micro.Then came the OLED section. I took extra care with the SDA and SCL lines, made them short and direct to avoid I²C noise issues.
Finally, I wired the rotary encoder pins. Routed the A/B signal lines as 8mil traces to avoid crowding. I also placed the debounce components as close to the Pro Micro as possible. End result: a board that looked elegant even in PCB view. Less is more, and I could see that working here.

---

<img width="901" height="474" alt="image" src="https://github.com/user-attachments/assets/eadd6223-ded9-4a54-a4c8-4a5945d0b1cb" />


---

---

<img width="968" height="719" alt="image" src="https://github.com/user-attachments/assets/8f622bd1-2f75-477d-b41d-ee8fd8b4507b" />



---

---

<img width="944" height="730" alt="image" src="https://github.com/user-attachments/assets/8e1717ad-cd0a-4b5c-bc32-11c03389f45c" />



---



## Day 5 – July 21 Fusion Case Modelling & OLED Cutouts (4 hours)
This part always feels the most real, bro. You take the flat PCB and suddenly it’s this physical object you can touch (well, almost). I opened up Fusion 360 and started sketching the base plate. Dimensions were 295 mm wide and about 100 mm tall, matching the board outline from EasyEDA. I extruded the plate 1.6 mm, same as PCB thickness, and then started designing the walls—about 12 mm tall to give enough space for the socket legs and components underneath.




---
<img width="1042" height="651" alt="image" src="https://github.com/user-attachments/assets/f8b9be0b-35d2-4f7e-98a1-dce4d035f092" />



---

---


<img width="999" height="603" alt="image" src="https://github.com/user-attachments/assets/27baaec6-82c4-4c99-b516-f494bfe09615" />


---



---

<img width="951" height="493" alt="image" src="https://github.com/user-attachments/assets/deef22e5-8f81-457c-b3da-8f8a3cf1bf8a" />


---


I then made the keycap cutouts using the keyboard layout I had exported. Each hole was 14x14 mm, just enough for switch travel and keycap clearance. Took extra time on the OLED screen window. It was 13×7 mm and had to sit between the encoders on the top right. Speaking of which I added two 6 mm encoder holes, aligned with their shafts.


---



<img width="976" height="580" alt="image" src="https://github.com/user-attachments/assets/f8695047-6d89-4533-9dd4-2df04c51f443" />



---





---

<img width="1007" height="540" alt="image" src="https://github.com/user-attachments/assets/0aeac2a8-9f47-4b06-bcfd-85b4c612c39d" />


---


---

<img width="852" height="446" alt="image" src="https://github.com/user-attachments/assets/e0c80755-0935-4fb1-9f70-e89d6fb7da6b" />



---

Rounded corners on the case gave it that smooth, Apple-ish vibe. Also added four M2 screw holes that matched the PCB mount points. Fusion preview looked chef’s kiss. 










