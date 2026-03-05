# JAMMMBOT

Before anything: huge shoutout to Dorian Todd and JustCallMeKoko, their work is the foudnation for this project and I couldn't have done any of this without their repos and guides.

Description: A quadrupedal robot that will detect nearby Wi-Fi devices, disrupt targeted connections, generate numerous spoofed networks, and overwhelm or mislead wireless scanning tools. Built for educational purposes.

Why I made this: I wanted to build a quadrapedal robot that can crawl, but also wanted to make it special in someway. So, I attached hacking hardware so it can penetrate test networks and do other cool things including but not limited to: staging deauthentication attacks, beacon spam, making fake wifi logins to capture credentials, run packet injections, bluetooth spam, and impersonate SSIDs.

Pictures:

Full Robot CAD
<img width="868" height="758" alt="Screenshot 2026-03-04 at 9 39 10 PM" src="https://github.com/user-attachments/assets/1eb07c10-4c26-42f6-ab36-7a5158918539" />
<img width="616" height="531" alt="Screenshot 2026-03-05 at 9 21 15 AM" src="https://github.com/user-attachments/assets/b2311d28-e17b-4952-96c0-18cad12c0350" />

PCB for Power Distrubution
<img width="296" height="146" alt="Screenshot 2026-03-05 at 9 07 09 AM" src="https://github.com/user-attachments/assets/ec7cfeb6-3fc3-447d-8fa6-7fe9f4ee72c6" />

Hacking Board
<img width="155" height="194" alt="Screenshot 2026-03-05 at 9 25 23 AM" src="https://github.com/user-attachments/assets/ce240ba7-4e55-42de-8a04-1aaadd751415" />

BOM for Entire Project
| Name                                  | Purpose                       | Cost (USD) | Qty | Total  |
| ------------------------------------- | ----------------------------- | ---------- | --- | ------ |
| Power distribution board + components | Powering all components       | $29.00     | 1   | $29.00 |
| Filament                              | 3D printed robot frame        | $13.99     | 1   | $13.99 |
| Soldering iron kit                    | Assembly of electronics       | $9.99      | 1   | $9.99  |
| Hacking Board PCB + components        | ESP32 control electronics     | $18.00     | 1   | $18.00 |
| Control PCB Components (LCSC BOM)     | All SMD parts for ESP32 board | $6.64      | 1   | $6.64  |
| M2 screw kit                          | Structural assembly           | $6.55      | 1   | $6.55  |
| XT30 female pigtail                   | Battery connection            | $3.50      | 2   | $7.00  |
| 2-slot 10440 Li-ion charger           | Charging battery cells        | $9.99      | 1   | $9.99  |
| 10440 Li-ion cells                    | Robot power supply            | $2.49      | 4   | $9.96  |
| AAA holder                            | Battery mounting              | $1.59      | 4   | $6.36  |
| Small zip ties                        | Cable management              | $6.98      | 1   | $6.98  |
| 30AWG silicone wire kit               | Dense electronics wiring      | $10.09     | 1   | $10.09 |
| 22AWG silicone wire kit               | Power wiring                  | $9.99      | 1   | $9.99  |
| Rocker power switch                   | Main system power             | $0.59      | 5   | $2.95  |
| 0.96" SSD1306 OLED                    | Robot face display            | $5.00      | 2   | $10.00 |
| MG90 Servos                           | Quadruped locomotion          | $2.99      | 8   | $23.92 |

BOM for Power Distrubution PCB
| ID | Component                   | Designators    | Footprint            | Qty | Manufacturer Part      | Manufacturer    | Supplier | Supplier Part | Unit Price |
| -- | --------------------------- | -------------- | -------------------- | --- | ---------------------- | --------------- | -------- | ------------- | ---------- |
| 1  | 22 nF Capacitor             | C3, C9, C11    | C0603                | 3   | CL10B223KB8NNNC        | Samsung         | LCSC     | C21122        | $0.004     |
| 2  | 100 nF Capacitor            | C4, C8, C10    | C0603                | 3   | CC0603KRX7R9BB104      | Yageo           | LCSC     | C14663        | $0.002     |
| 3  | 10 nF Capacitor             | C5             | C0603                | 1   | C0603B103M500NT        | Torch           | LCSC     | C17702744     | $0.005     |
| 4  | 3.3 µH Inductor             | L1             | IND-SMD L7.3-W6.6    | 1   | MHCI06030-3R3M-S8      | Chilisin        | LCSC     | C285713       | $0.147     |
| 5  | Red LED                     | LED1           | LED0603-RD           | 1   | KT-0603R               | KENTO           | LCSC     | C2286         | $0.007     |
| 6  | 5.1 kΩ Resistor             | R1, R5         | R0603                | 2   | 0603WAF5101T5E         | UNI-ROYAL       | LCSC     | C23186        | $0.001     |
| 7  | 56 kΩ Resistor              | R2             | R0603                | 1   | 0603WAF5602T5E         | UNI-ROYAL       | LCSC     | C23206        | $0.001     |
| 8  | 10 kΩ Resistor              | R3, R4, R8, R9 | R0603                | 4   | RCT0310KJLF            | HKR             | LCSC     | C177337       | —          |
| 9  | 3.5 mm 2-Pin Screw Terminal | 5-12V          | ScrewTerm-3.5mm-2Pin | 1   | 1984617                | Phoenix Contact | Digi-Key | —             | —          |
| 10 | JST-XH 4-Pin Connector      | JST-XH         | JST-XH-4PIN-2.5      | 1   | —                      | —               | —        | —             | —          |
| 11 | Tactile Switch              | RESET, BOOT    | KEY-SMD L4.0-W3.0    | 2   | HX 3x4x2-2P-1.6N       | Hanxia          | LCSC     | C49234124     | $0.02      |
| 12 | Large Solder Pad            | U5, U7         | SOLDERPAD LG         | 2   | —                      | —               | —        | —             | —          |
| 13 | 1 µF Capacitor              | C1             | C0805                | 1   | AC0805KKX7R9BB105      | Yageo           | LCSC     | C726584       | $0.035     |
| 14 | 470 µF Capacitor            | C7             | Large SMD Cap        | 1   | XT470UF25V90RV0111     | KNSCHA          | LCSC     | C3445244      | $0.128     |
| 15 | Schottky Diode SS34         | D1, D2         | SMA                  | 2   | SS34                   | MDD             | LCSC     | C8678         | $0.03      |
| 16 | 3-Pin Headers               | P1–P8          | 2.54mm Pin Header    | 8   | HDR1X8-2.54            | BOOMELE         | LCSC     | C27438        | $0.088     |
| 17 | ESP32-S3 Module             | U1             | ESP32-S3-WROOM-1     | 1   | ESP32-S3-WROOM-1-N16R8 | Espressif       | LCSC     | C2913202      | $5.613     |
| 18 | 3.3 V LDO Regulator         | U2             | SOT-223-3            | 1   | AMS1117-3.3            | AMS             | LCSC     | C6186         | $0.197     |
| 19 | Buck Converter IC           | U3             | SOT-23-6             | 1   | MSTPS563200DDCR        | MSKSEMI         | LCSC     | C49208508     | $0.177     |
| 20 | 10 µF Capacitor             | U4             | SMD Electrolytic     | 1   | RST10UF25V014          | KNSCHA          | LCSC     | C4747969      | $0.025     |

BOM For Hacking ESP PCB
| ID | Component                  | Designator     | Package          | Qty | Manufacturer Part      | Supplier | Unit Price | Total  |
| -- | -------------------------- | -------------- | ---------------- | --- | ---------------------- | -------- | ---------- | ------ |
| 1  | 22nF capacitor             | C3, C9, C11    | 0603             | 3   | CL10B223KB8NNNC        | LCSC     | $0.004     | $0.012 |
| 2  | 100nF capacitor            | C4, C8, C10    | 0603             | 3   | CC0603KRX7R9BB104      | LCSC     | $0.002     | $0.006 |
| 3  | 10nF capacitor             | C5             | 0603             | 1   | C0603B103M500NT        | LCSC     | $0.005     | $0.005 |
| 4  | 3.3uH inductor             | L1             | SMD              | 1   | MHCI06030-3R3M-S8      | LCSC     | $0.147     | $0.147 |
| 5  | Red LED                    | LED1           | 0603             | 1   | KT-0603R               | LCSC     | $0.007     | $0.007 |
| 6  | 5.1kΩ resistor             | R1, R5         | 0603             | 2   | 0603WAF5101T5E         | LCSC     | $0.001     | $0.002 |
| 7  | 56kΩ resistor              | R2             | 0603             | 1   | 0603WAF5602T5E         | LCSC     | $0.001     | $0.001 |
| 8  | 10kΩ resistor              | R3, R4, R8, R9 | 0603             | 4   | RCT0310KJLF            | LCSC     | ~$0.001    | $0.004 |
| 9  | 3.5mm 2-pin screw terminal | 5-12V input    | Through-hole     | 1   | 1984617                | Digi-Key | ~$0.50     | $0.50  |
| 10 | JST-XH 4-pin connector     | JST-XH         | 2.5mm            | 1   | JST-XH-4P              | LCSC     | ~$0.10     | $0.10  |
| 11 | Tactile switch             | RESET, BOOT    | SMD              | 2   | HX 3x4x2-2P            | LCSC     | $0.02      | $0.04  |
| 12 | Solder pads                | U5, U7         | PCB pad          | 2   | —                      | —        | —          | —      |
| 13 | 1µF capacitor              | C1             | 0805             | 1   | AC0805KKX7R9BB105      | LCSC     | $0.035     | $0.035 |
| 14 | 470µF capacitor            | C7             | SMD electrolytic | 1   | XT470UF25V90RV0111     | LCSC     | $0.128     | $0.128 |
| 15 | SS34 Schottky diode        | D1, D2         | SMA              | 2   | SS34                   | LCSC     | $0.030     | $0.060 |
| 16 | 3-pin headers              | P1-P8          | 2.54mm           | 8   | HDR1X8-2.54            | LCSC     | $0.088     | $0.704 |
| 17 | ESP32-S3-WROOM-1-N16R8     | U1             | RF module        | 1   | ESP32-S3-WROOM-1-N16R8 | LCSC     | $5.613     | $5.613 |
| 18 | AMS1117-3.3 LDO            | U2             | SOT-223          | 1   | AMS1117-3.3            | LCSC     | $0.197     | $0.197 |
| 19 | Buck converter IC          | U3             | SOT-23-6         | 1   | MSTPS563200DDCR        | LCSC     | $0.177     | $0.177 |
| 20 | 10µF capacitor             | U4             | SMD              | 1   | RST10UF25V014          | LCSC     | $0.025     | $0.025 |


