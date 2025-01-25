# PCB schematic
coming soon

## Components
- 230VAC --> 24VDC
- 8x relay board (used for 24VDC)
- 4x relay board (used for 230VAC)
- 2x Analog/I2C sensor board
- 24VDC -> 5VDC
- 8x DC socket for grow lights, ventilation etc.
- 5VDC --> 3.3VDC
- ESP32 board
- 2x snubber for pump relay
- 2x 2 pin pump 230VAC socket
- 1x AC in 3 pin
- 1x 3 pin 230VAC out (26W growlight)

## Wiring 60x60
- 24VDC always on for extractor
- 24VDC 1 -> 2 for ventilation
- 24VDC 1 -> 5 for main light
- 24VDC for UV
- 24VDC for IR
- 230VAC for pump
- 2x I2C Sensor (BME280+MLX90614)
- 1x analog Sensor water temp (DS18B20)
- Air stone hose
- Total relays needed: 5x: 4x 24VDC, 1x 230VAC

## Wiring 60x40
- 24VDC always on for extractor
- Total relays needed: 5x: 3x 24VDC, 2x 230VAC

### Wiring 60x40 Cutlings
- 230VAC for pump
- 230VAC for main light (with PE)
- 2x relay 230VAC

### Wiring 60x40 Mother Plant
- 24VDC 1 -> 2 for main light
- 24VDC for IR
- 24VDC for ventilation
- I2C Sensor (BME280)
- 1x analog Sensor water temp (DS18B20)
- Air stone hose
- 3x relay 24VDC

## Wiring of the electronics box

230VAC in --> needed for the 2 230VAC pumps and the 230VAC grow light. 4x relay board used for that (proper montage is important here!). Apart from that
only 24V downwards is needed.
24V is needed for:
- the extractors which are running permanently
- the remainder of the grow lights + ventilation (connected to 8x relay board)

5V is needed for:
- the 2 relay boards (4x/8x)
- the ESP32
- the 2 I2C / sensor boards

3.3V is needed for the DS18B20 sensors (`4.7k` pull up resistor from analog signal to 3.3VDD)

### Wire strengths
16 AWG from 24V converter to distributor clamp. Should be able to handle all the load simultaneously. 
Go directly to the relay board where there is the highest load (main grow lights) present - check if setup can be improved with t-clamps.
Use cable ties to keep the cables in place and the space tidy.
maybe some relay and/or sensor boards are stackable --> check that if space usage can be optimized (with the plastic distance holders maybe)
