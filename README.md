arduino-potentiometer-dht11-lcd-display

# Arduino LCD Display with Potentiometer and DHT11 Sensor

This Arduino project reads the analog voltage from a **potentiometer** and sensor data from a **DHT11** (temperature and humidity sensor), then displays the results on a **16x2 LCD** using the `LiquidCrystal` library.

---

## Features

- Displays potentiometer analog voltage
- Measures and displays temperature (°C) and humidity (%)
- Updates values on a 16x2 LCD in real-time
- Also sends data to Serial Monitor

---

## 🔧 Components Required

| Component        | Quantity |
|------------------|----------|
| Arduino Uno/Nano | 1        |
| 16x2 LCD         | 1        |
| Potentiometer    | 1        |
| DHT11 Sensor     | 1        |
| 10K Ohm Resistor | 1 (optional, for contrast) |
| Breadboard & Wires | As needed |

---

## 🛠️ Circuit Connections

### LCD (16x2) to Arduino:
| LCD Pin | Arduino Pin |
|---------|-------------|
| RS      | 12          |
| EN      | 10          |
| D4      | 5           |
| D5      | 4           |
| D6      | 3           |
| D7      | 2           |
| RW      | GND         |
| VSS     | GND         |
| VDD     | 5V          |
| VO      | Middle pin of potentiometer |

### Others:
- **DHT11 Data Pin** → Pin 8  
- **Potentiometer** → Middle pin to A5, other two to 5V and GND

---

## How It Works

1. The **potentiometer** gives an analog value between 0–1023.
2. It's converted to voltage using the formula:
voltage = (analogValue * 5) / 1024

yaml
Copy
Edit
3. The **DHT11 sensor** gives temperature and humidity.
4. These values are displayed on the LCD and printed to the Serial Monitor in a loop every second.

---

## 🧾 Code Breakdown

- `LiquidCrystal` library is used to control the LCD.
- `DHT` library reads temperature and humidity.
- LCD cycles through 3 displays: Potentiometer Voltage, Temperature, Humidity.

---

## How to Use

1. Connect all components as per the schematic.
2. Upload the code to your Arduino using the Arduino IDE.
3. Open the Serial Monitor (9600 baud) to also view live data.

---

## Libraries Required

Install the following from Library Manager in Arduino IDE:
- `DHT sensor library` by Adafruit
- `Adafruit Unified Sensor`
- `LiquidCrystal` (built-in)

---

## License

This project is open-source under the [MIT License](LICENSE).

---

## Author

**Your Name Here**  
Contributions and suggestions are welcome!
