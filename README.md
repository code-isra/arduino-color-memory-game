# Arduino Color Memory Game

An interactive memory puzzle game built with Arduino. The system generates increasingly complex pattern sequences using colored LEDs and custom sound tones to test and train the user's short-term recall.

---

## Overview & Features

* **Dynamic Sequence Generation:** Uses pseudo-random seeds (`randomSeed(millis())`) to generate unpredictable color sequences up to 10 rounds.
* **Attract Mode:** Displays a continuous rotating light animation while idle until any button is pressed to initiate a game.
* **Push-Pull Sound Synthesis:** Drives two output pins in opposing phase to maximize piezo buzzer volume without extra amplification.
* **Serial Telemetry:** Outputs current game status, round progress, and user results in real time to the Serial Monitor at 9600 baud.
* **Timeout Enforcement:** Provides a strict 3-second window (`ENTRY_TIME_LIMIT`) for the player to input each move.

---

## Hardware Components 

* 1x Arduino Uno 
* 4x Push Buttons (Red, Green, Blue, Yellow)
* 4x LEDs (Red, Green, Blue, Yellow)
* 4x 220Ω Resistors (for LEDs)
* 1x 5v Passive Buzzer 
* Breadboard & Jumper Wires

---

## Pin Mapping 

| Component | Arduino Pin | Function / Description |
| :--- | :--- | :--- |
| **Red LED** | Pin 10 | Visual indicator for Red choice |
| **Green LED** | Pin 3 | Visual indicator for Green choice |
| **Blue LED** | Pin 13 | Visual indicator for Blue choice |
| **Yellow LED** | Pin 5 | Visual indicator for Yellow choice |
| **Red Button** | Pin 9 | Input for Red choice |
| **Green Button** | Pin 2 | Input for Green choice |
| **Blue Button** | Pin 12 | Input for Blue choice |
| **Yellow Button** | Pin 6 | Input for Yellow choice |
| **Buzzer (+)** | Pin 4 | Push-pull differential output 1 |
| **Buzzer (-)** | Pin 7 | Push-pull differential output 2 |

---

## How to Play

1. **Start:** When powered on, the LEDs cycle in Attract Mode. Press any button to start a new game.
2. **Observe:** The LEDs flash all at once, then play the target sequence along with corresponding audio tones.
3. **Repeat:** Repeat the sequence by pressing the corresponding colored buttons in order. You have 3 seconds per input.
4. **Win Condition:** Successfully complete 10 consecutive rounds to trigger the winner victory sequence!

---

## Setup & Running

1. Upload `src/main.ino` to your Arduino using the Arduino IDE.
2. Open the **Serial Monitor** at **9600 baud** to view live game diagnostics.
3. Wire the circuit according to the Pin Mapping table above.
