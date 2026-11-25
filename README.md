# The Posture Robot
# Nudge: the posture robot for your desk
Nudge is a little desk buddy that keeps an eye on your posture while you work. Your webcam watches how you sit, a dashboard in your browser shows how you’re doing, and a small ESP32 robot reacts right there on your desk.
It works on Windows, macOS and Linux with any normal webcam. The robot connects over USB or Wi-Fi. A few extras only work on macOS for now, and I’ve marked those with **(macOS)**
## What it does
- **Posture coaching:** It notices when you slouch, lean in, tilt your shoulders or crane your head. The robot’s face turns worried, then grumpy, and its light goes amber, then red.
- **Water reminders:** Every 30 minutes, with a daily goal of 8 glasses.
- **Eye breaks (20-20-20):** Every 20 minutes, look at something about 20 feet away for 20 seconds.
- **Stretch breaks:** After 45 minutes of sitting without a break. If you leave your desk for more than a minute, that counts as a break.
- **Focus timer:** 25 minutes of work, then a 5 minute break (Pomodoro style).
- **Achievements and high fives:** When you hit a goal, the robot asks for a high five. Tap the touch sensor on its head to give it one.
- **Daily stats:** Good-posture percentage, time at your desk, best streak, a posture chart for the day and an activity log.
- **Desktop notifications** for reminders and achievements **(macOS)**.
- **Spoken messages and sounds (macOS):** Posture warnings, praise, reminders and timer events are said out loud, and the robot’s sounds play through your speakers. The dashboard’s own click sounds work in any browser.
- **Nudge, the robot’s AI assistant:** Say *”Hey Nudge”*. It’s the robot’s personality, powered by Claude. It speaks up on its own (reminders, welcome-backs, meeting heads-ups), and it can control the robot, phone you, search the web and remember things about you. On macOS it can also run your computer (terminal, apps, your screen). It can also run on its own, without the camera. [More below](#3-nudge-ai-assistant).
- You can change all of these in the dashboard’s **Settings**.
   
## Features
Here’s what Nudge does today, and what’s still on the way.
| Feature | Status |
|—-|—-|
| **Private posture detection.** Your laptop’s webcam is analysed on the laptop itself. No video or pictures ever leave your computer, and nothing is recorded. | Working |
| **No false alarms for normal movement.** Looking down at the keyboard, reaching for a drink or turning to a second screen doesn’t count as slouching. A problem has to last for a while before Nudge reacts. | Working |
| **A face that reacts.** A 1.8” colour screen shows happy, calm, worried, grumpy, sleepy, love, thinking and surprised faces, with smooth animation and blinking. | Working |
| **A glowing, touch-sensitive top.** An RGB LED lights up a translucent panel in the colour of Nudge’s mood. A touch sensor underneath feels taps, double-taps and holds. | Working |
| **Nudge, the voice assistant.** Say *”Hey Nudge”* to ask questions, set timers, control your laptop or check your day. It talks through your own speakers, so the robot itself needs no speaker or microphone. | Working (laptop app) |
| **Smart breaks.** Water, stretch and 20-20-20 eye break reminders, plus a heads-up before calendar events so it doesn’t interrupt a meeting. | Partly built : reminders and calendar heads-ups work, planning breaks around meetings is next |
| **Thinking moment” check-ins.** When you lean back or stare away from the screen for a whole, Nudge waits, then checks in gently instead of telling you off. | Planned |
| **Keyboard and mouse signals.** Typing and mouse activity show whether you’re focused, reading or away, so Nudge picks a good moment to speak up. It only sees activity levels, never what you type. | Planned |
| **A tough 3D-printed body.** A 5-part design: shell, bezel, glowing top panel, base and display mount. | Printed |
| **One USB-C cable.** An ESP32-c3 gets power and data over the same cable, so there’s no battery and no parking. |Working |
## How it works
The way I think about it: your laptop is the brain and the robot is the body. The laptop does all the heavy thinking. The robot just gets short text commands over USB, things like “look worried” or “show a water reminder”, and sends back touches like “tapped” or “held”. That keeps the robot cheap and simple, and the hard work runs on a computer you already own.
### How it spots bad posture
1. A pose model runs on your laptop and finds your head, shoulders and face in every webcam frame.
2. You sit up straight once so Nudge can calibrate. It learns what your good posture looks like from where your camera sits, so it never compares you to some average body.
3. Every frame is checked against that: how far your head has dropped toward your shoulders, how far it’s pushed forward, whether you’re leaning in or tilting, and how close you are to the screen.
4. The readings are smoothed out, and a problem has last a few seconds before anything happens. That’s why reaching for a drink or glancing at a second screen doesn’t set it off.
5. The result is one simple state: good, warning, bad or away. That state decides the robot’s face and light.
6. ### The Nudge assistant
7. The wake word and speech-to-text run on your laptop, so your voice gets uploaded. Only the text of what you asked goes to a language model, along with a bit of context like the time and today’s posture summary. It can use tools like timers, reminders, your calendar and web search. Anything risky needs you to say “yes” first. It talks back through your laptop speakers




## Hardware
### Bill of materials
These are rough single-unit prices from AliExpress or Amazon, in US dollars.
|# | Part | Qty | Price | Notes |
|—-|——|——|——|——|
| 1| Carrier board with an ESP32-C3 SuperMini module (USB-C) | 1 | $3 | The brain of the robot, with native USB serial. This is my stage 1 prototype. The final product will be a custom PCB with the ESP32-C3 chip soldered straight on. |
| 2| 1.8” 128x160 ST7735 colour TFT (SPI) | 1 | $5 | The face. It sits in the TFT mount. |
| 3| TTP223 capacitive touch module | 1 | $0.50 | Goes under the top panel and can feel a touch through 1 to 2 mm of plastic. |
| 4| WS2812B 5050 RGB LED (3 pads: VCC, GND, DIN) | 1 | $0.50 | Lights up the top panel. Just one data wire. |
| 5| USB-C data cable | 1 | $3 | Gives power and serial. Careful, some cheap cables only charge. |
| 6| PLA filament (shell, bezel, base, mount) | about 90 g | $2 | Any opaque colour works. |
| 7| Translucent or white PLA or PETG (top panel) | about 12 | $1 | Or solder thin silicone wire instead. |
| 8| Dupont jumper wires, female to female | about 12 | $1 | Or solder thin silicone wire instead. |
| 9| M2 screws, 6 to 8 mm | 4 to 6 | $1 | For the mount and the base. |
| 10| 330 ohm resistor (LED data line), optional | 1 | $0.05 | Protects the LED’s data pin. |
| | Total | | about $17 | |
