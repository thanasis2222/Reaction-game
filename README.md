# Arduino Reaction Game

A 2-player reaction game built with Arduino that tests how quickly each player can react to visual cues (LEDs). The game uses buttons, LEDs, and a 16x2 I2C LCD to display rounds, scores, and game instructions.

## 🕹 Features

- Two-player reaction-based gameplay
- Randomized delay to keep players guessing
- Early button press penalties
- Real-time scoring displayed on an LCD
- Game plays for a maximum of 5 rounds
- Start/reset game by pressing both buttons

## 📦 Components Required

- Arduino Uno (or compatible board)
- 2 Push buttons
- 2 LEDs with resistors
- 16x2 I2C LCD display (I2C address: `0x27` by default)
- Breadboard and jumper wires

## ⚡ Wiring Guide

| Component       | Arduino Pin |
|----------------|-------------|
| Button 1       | D2          |
| Button 2       | D3          |
| LED 1          | D4          |
| LED 2          | D5          |
| LCD (SDA)      | A4          |
| LCD (SCL)      | A5          |
| GND and VCC    | GND / 5V    |

> Note: Use pull-down resistors for buttons or enable internal pull-ups and reverse logic.

## 🚀 Getting Started

1. Clone or download this repository.
2. Open the sketch in the Arduino IDE.
3. Upload it to your Arduino board.
4. Connect the components as per the wiring guide.
5. Open the Serial Monitor at 9600 baud to monitor debug output.
6. Press both buttons simultaneously to start the game.

## 🧠 Game Logic

- **Start Game:** Press both buttons together.
- **Countdown Phase:** Both LEDs turn on and turn off one-by-one after a random delay.
- **Reaction Phase:** After all LEDs turn off, first to press wins the round.
- **Penalty:** Pressing a button before LEDs are off gives a point to the other player.
- **End Game:** After 5 rounds, the player with the most points wins.

## 📺 LCD Display

- First line: Displays game status (`Round`, `Player X Won`, etc.)
- Second line: Displays current score for both players (`P1:x P2:y`)

## 🐞 Debugging

- Serial Monitor outputs current game state and button presses
- Helps with testing responsiveness and catching input issues

## 🛠 To-Do / Improvements

- Add buzzer for sound feedback
- Customize number of rounds via input
- Save high score using EEPROM
- Improve debounce logic with `millis()` instead of `delay()`

## 📃 License

This project is open-source and free to use under the [MIT License](LICENSE).

---

Enjoy challenging your reflexes with this simple but fun Arduino game!
