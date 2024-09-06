# Simple Traffic Light on Arduino

This project simulates a basic traffic light system using an Arduino. The traffic light consists of red, yellow, and green LEDs, each controlled by the Arduino to represent the different states of a traffic signal.

## Components Used

- Arduino Uno
- Red LED (connected to pin 11)
- Yellow LED (connected to pin 10)
- Green LED (connected to pin 9)
- Resistors (220Ω recommended for each LED)
- Jumper wires
- Breadboard

## How It Works

- The traffic light system consists of three LEDs representing the red, yellow, and green lights.
- Each LED turns on for a specific duration to simulate the operation of a real traffic light.
  - **Red light**: stays on for 10 seconds.
  - **Yellow light**: stays on for 2 seconds.
  - **Green light**: stays on for 8 seconds.
- The cycle repeats indefinitely.

## Pin Configuration

- **Red LED**: connected to pin 11.
- **Yellow LED**: connected to pin 10.
- **Green LED**: connected to pin 9.

## Code Explanation

- Each LED is assigned to a pin and set as an output in the `setup()` function.
- In the `loop()` function, the LEDs are turned on and off in sequence using `digitalWrite()`, with `delay()` used to control how long each LED stays on.
  - The delay is set in seconds (converted to milliseconds in the code).
  
## Code

```cpp
const int PIN_MERAH = 11;
const int PIN_KUNING = 10;
const int PIN_HIJAU = 9;

const int DURASI_MERAH = 10; // detik
const int DURASI_KUNING = 2; // detik
const int DURASI_HIJAU = 8; // detik

void setup() {
    pinMode( PIN_MERAH, OUTPUT );
    pinMode( PIN_KUNING, OUTPUT );
    pinMode( PIN_HIJAU, OUTPUT );
}

void loop() {
    digitalWrite( PIN_MERAH, HIGH ); // nyalakan lampu merah
    delay( DURASI_MERAH * 1000 ); // 1 detik = 1000ms
    digitalWrite( PIN_MERAH, LOW ); // matikan lampu merah
    digitalWrite( PIN_KUNING, HIGH ); // nyalakan lampu kuning
    delay( DURASI_KUNING * 1000 ); // pause 2 detik
    digitalWrite( PIN_KUNING, LOW ); // matikan lampu kuning
    digitalWrite( PIN_HIJAU, HIGH ); // nyalakan lampu hijau
    delay( DURASI_HIJAU * 1000 ); // pause 8 detik
    digitalWrite( PIN_HIJAU, LOW ); // matikan lampu hijau
}
```

## How to Use

1. Connect the LEDs to the respective pins on the Arduino as described in the pin configuration.
2. Upload the provided code to the Arduino.
3. The traffic light system will automatically start, cycling between red, yellow, and green lights.

## Features

1. Simulates a real-world traffic light system.
2. Easy-to-understand and implement for beginners.
2. Adjustable timing for each light to match your needs.

## License
- This project is open-source and can be modified or distributed freely.