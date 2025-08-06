# Aesthetic Keyboard 
Minimal 65% custom keyboard with dual encoders, OLED.

---

It all started when I was bored of the flashy, RGB-overloaded prebuilt boards. I didn’t want anything too loud or gamer coded just a clean, minimal board that I could carry, code on, or chill and type without distractions. So one night, while playing around on EasyEDA, I decided to just go for it.I started off by drafting a clean schematic. Nothing fancy—just sixty-something keys, standard matrix setup, and a few extras. I placed footprints for 61 hot-swap switches, 1N4148 diodes, and rotary encoders on the right. I also added an OLED screen bang in the middle top so I could use it to show layers, typing speed, or whatever random pixel art I wanted.


<img width="897" height="585" alt="Screenshot 2025-07-21 225141" src="https://github.com/user-attachments/assets/7c9e73f3-a7df-401a-9c3e-6087a5bca293" />





Once the schematic was locked, I poured around 5 hours laying out the PCB manually. I kept the traces tidy, respected the row-column rules, and made sure the diodes weren’t flipped—because trust me, debugging that later is a headache. I used the Pro Micro as the brain again, because it’s affordable and works well with QMK. For extra support, I added mounting holes around the edges, just in case I decide to go screw-mount later. Once done, I exported the Gerbers and sent the board off to JLCPCB with a matte black solder mask. It cost me peanuts for 5 boards.

---

This board has a solid layout that feels like a cross between a 65% and a productivity board. I kept the encoder knobs top right they’re handy for media, volume, or layer switching. The OLED is 0.91" and uses I²C, wired directly to SDA/SCL on the Pro Micro. It’s compact, but adds a lot of charm. Just seeing something on screen makes the board feel alive.





<img width="901" height="474" alt="Screenshot 2025-07-21 225630" src="https://github.com/user-attachments/assets/9a7df957-6370-4281-8d77-79a7f8ebbe53" />






<img width="968" height="719" alt="Screenshot 2025-07-21 225657" src="https://github.com/user-attachments/assets/bacb35a6-1edd-46f7-aefb-d57aee825c07" />







<img width="944" height="730" alt="Screenshot 2025-07-21 225725" src="https://github.com/user-attachments/assets/70c57037-383c-41be-8bbb-4020b4d3e830" />







## 3D Printed Case

For the enclosure, I opened up Fusion 360 and made a simple two-part shell—just a base and a low-profile top. I left cutouts for the encoders and OLED, and slots on the side for USB access






<img width="999" height="603" alt="Screenshot 2025-07-21 225959" src="https://github.com/user-attachments/assets/9b4d242c-aa6f-43f1-81c2-3689df419d47" />





<img width="1042" height="651" alt="Screenshot 2025-07-21 225935" src="https://github.com/user-attachments/assets/79275eab-4cd6-4dc3-9d93-f20aab08fa11" />







<img width="1007" height="540" alt="Screenshot 2025-07-21 225858" src="https://github.com/user-attachments/assets/43e3b8b4-2496-4487-9db1-f297215b2e7e" />







---


<img width="978" height="453" alt="Screenshot 2025-07-21 222644" src="https://github.com/user-attachments/assets/69e7e6ff-0d3f-430e-9797-6ef968f3e2a9" />





# updated Case

ive added a cool pattern for base , and added a secret code on top which says keval is cool

<img width="846" height="519" alt="Screenshot 2025-08-06 122605" src="https://github.com/user-attachments/assets/f129295a-6d97-4b4b-bce1-c64a3b061d65" />

<img width="841" height="360" alt="Screenshot 2025-08-06 122623" src="https://github.com/user-attachments/assets/ab6de233-adae-49dc-a3c8-f5b65e5ceb89" />

<img width="883" height="580" alt="Screenshot 2025-08-06 122615" src="https://github.com/user-attachments/assets/08311c0d-b99f-4c51-a357-9e48e86e7d35" />





---

## 🧾 Bill of Materials

| Component                         | Source & Link        | Qty | Total Cost (INR) | Total Cost (USD) |
|-----------------------------------|----------------------|----:|-----------------:|-----------------:|
| Gateron Blue Mechanical Switches  | CosmicByte.in        |  61 | ₹2,250           | $27              |
| PBT Keycaps (Black)               | Neomacro.in          |  61 | ₹2,300           | $28              |
| Kailh Hot-swap Sockets            | Neomacro.in          |  61 | ₹1,275           | $15              |
| Rotary Encoders                   | ShaarviElectronics   |   2 | ₹350             | $4.2             |
| Encoder Knobs                     | ShaarviElectronics   |   2 | ₹200             | $2.4             |
| 0.91″ OLED Display                | Amazon.in            |   1 | ₹600             | $7.2             |
| Pro Micro (ATmega32U4)            | Amazon.in            |   1 | ₹850             | $10.2            |
| 1N4148 Diodes (100 pcs)           | ShaarviElectronics   |   1 | ₹85              | $1               |
| Custom PCB (5 pcs, Black)         | JLCPCB               |   5 | ₹2,450           | $29              |
| Shipping                          | JLCPCB               |   1 | ₹420             | $5               |
| **Total**                         |                      |     | ₹11,330          | **~$129**        |

---

##  Firmware
uhmm  running a custom QMK build with:

- Layer 0: Standard QWERTY
- Layer 1: Media controls, encoder scroll
- Layer 2: Function + macros
- OLED: Layer display, typing animation
- Encoders: One for volume (tap = mute), one for scroll (tap = layer toggle)

QMK source files are added

---


