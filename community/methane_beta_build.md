
# RRIV Methane Beta Setup
## Overview
Beta version RRIV loggers with methane (CH<sub>4</sub>) and carbon dioxide (CO<sub>2</sub>). Methane sensors use a Figaro XXX metal oxide sensor and CO<sub>2</sub> sensors use a Atlas Scientific infrared carbon dioxide sensor. Sensors were encased in segments of 2" PVC pipe with one end covered by a XXX" thick PTFE diaphragm to permit gas exchange with the water.

## Tools
* 2 adjustable wrench 3/8” to 1 ¼”
* Pliers 3/8” to 1 ¼”
* [Molykote Grease](https://www.dupont.com/molykote.html)
* Mini USB to USB cable
* [Programming header](https://www.st.com/en/evaluation-tools/nucleo-f103rb.html)(Figure 1)

![Figure 1: ST Nucleo programming header](graphics/programmingBoard.jpg "Figure 1: ST Nucleo programming header")

*Figure 1: ST Nucleo programming header*

## Included components
* RRIV Data Logger (V0.21)
* Enclosed CH<sub>4</sub> sensor
* Enclosed CO<sub>2</sub> sensor
* ABS sonde housing (add link to instructions on how to build one yourself)

## Off the shelf components to purchase
| Item | Number Needed per Device| Source & Part Number |
| ----------- | ----------- | ----------- |
| EPDM O-Ring (Size: Dash Number 341) | 2 | [McMaster-Carr 9557K316](https://www.mcmaster.com/9557K316/) |
| 18-8 stainless steel threaded rod 3/8” – 16 [2']   | 6 | [McMaster-Carr 98804A031](https://www.mcmaster.com/98804A031/) |
| 18-8 stainless steel hex nuts 3/8” -16 | 24 | [McMaster-Carr 91845A031](https://www.mcmaster.com/91845A031/) |
| 18-8 stainless steel washers 3/8” | 24 | [McMaster-Carr 92141A031](https://www.mcmaster.com/92141A031/) |
| Tenergy rechargeable NiMH D cell batteries | 6 | [Tenergy D Cell Batteries](https://power.tenergy.com/8pcs-tenergy-centura-lite-nimh-d-1-2v-3000mah-rechargeable-batteries/) |
| Tenergy NiMH D cell battery charger | 1 | [Tenergy Battery Charger](https://www.tenergy.com/01480) |
| Dupont jumper cables | 8 | [Digikey 1528-1961-ND](https://www.digikey.com/en/products/detail/adafruit-industries-llc/1950/6827084?utm_adgroup=Jumper%20Wire&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Product_Prototyping%2C%20Fabrication%20Products_NEW&utm_term=&utm_content=Jumper%20Wire&gclid=Cj0KCQjwmZejBhC_ARIsAGhCqnfnwVrB9Qzxf5KKnGFd_KI0TyKxzOzWoKUWDibQ6rWHKfjT-iwHqIwaAmCSEALw_wcB) |

## Sensor assembly
![Figure 2: Assembly of the sensor housing](graphics/caseAssembly.png "Figure 2: Assembly of the sensor housing")
*Figure 2: Assembly of the sensor housing*

* place bolts through the solid acrylic plate that forms the back of the sonde and fix washers and nuts on the short side acrylic plate to holid it in place.


## Initial sensor setup and configuration
* Load VS Code or install CLI
* Plug in sensor
* use following configuration commands: set-config<>
* test sensor performance using the command start-logging
