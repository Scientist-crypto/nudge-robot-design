# The Posture Robot
#Nudge: the posture robot for your desk
Nudge is a little desk buddy that keeps an eye on your posture while you work. Your webcam watches how you sit, a dashboard in your browser shows how you’re doing, and a small ESP32 robot reacts right there on your desk.
It works on Windows, macOS and Linux with any normal webcam. The robot connects over USB or Wi-Fi. A few extras only work on macOS for now, and I’ve marked those with **(macOS)**
## What it does
- **Posture coaching:** It notices when you slouch, lean in, tilt your shoulders or crane your head. The robot’s face turns worried, then grumpy, and its light goes amber, then red.
- **Water reminders:** Every 30 minutes, with a daily goal of 8 glasses.
- **Eye breaks (20-20-20):** Every 30 minutes, look at something about 20 feet away for 20 seconds.
- **Stretch breaks:** After 45 minutes of sitting without a break. If you leave your desk for more than a minute, that counts as a break.
- **Focus timer:** 25 minutes of work, then a 5 minute break (Pomodoro style).
- **Achievements and high fives:** When you hit a goal, the robot asks for a high five. Tap the touch sensor on its head to give it one.
- **Daily stats:** Good-posture percentage, time at your desk, best streak, a posture chart for the day and an activity log.
- **Desktop notifications** for reminders and achievements **(macOS)**.
- **Spoken messages and sounds (macOS):** Posture warnings, praise, reminders and timer events are said out loud, and the robot’s sounds play through your speakers. The dashboard’s own click sounds work in any browser.
- **Nudge, the robot’s AI assistant:** Say *”Hey Nudge”*. It’s the robot’s personality, powered by Claude. It speaks up on its own (reminders, welcome-backs, meeting heads-ups), and it can control the robot, phone you, search the web and remember things about you. On macOS it can also run your computer (terminal, apps, your screen). It can also run on its own, without the camera. [More below](#3-nudge-ai-assistant).
- You can change all of these in the dashboard’s **Settings**.
- Computer (brain/) 
## Features
Here’s what Nudge does today, and what’s still on the way.
| Feature | Status |
|—-|—-|
| **Private posture detection.** Your laptop’s webcam is analysed on the laptop itself. No video or pictures ever leave your computer, and nothing is recorded. | Working |
| **No false alarms for normal movement.** Looking down at the keyboard, reaching for a drink or turning to a second screen doesn’t count as slouching. A problem has to last for a while before Nudge reacts. | Working |
| **A face that reacts.** A 1.8”” colour screen shows happy, calm, worried, grumpy,sleepy, love, thinking and surprised faces, with smooth animation and blinking. | Working |
| **A glowing, touch-sensitive top.** An RGB LED lights up a translucent panel in the colour of Nudge’s mood. A touch sensor underneath feels taps, double-taps and holds. | Working |
| **Nudge, the voice assistant.** Say *”Hey Nudge”* to ask questions, set timers, control your laptop or check your day. It talks through your own speakers, so the robot itself needs no speaker or microphone. | Working (laptop app) |
| **Smart breaks.** Water, stretch and 20-20-20 eye break reminders, plus a heads-up before calendar events so it doesn’t interrupt a meeting. | Partly built : reminders and calendar heads-ups work, planning breaks around meetings is next |
| **Thunking moment” check-ins.** When you lean back or stare away from the screen for a whole, Nudge waits, then checks in gently instead of telling you off. | Planned |
| **Keyboard and mouse signals.** Typing and mouse activity show whether you’re focused, reading or away, so Nudge picks a good moment to speak up. It only sees activity levels, never what you type. | Planned |
| **A tough 3D-printed body.** A 5-part design: shell, bezel, glowing top panel, base and display mount. | Printed |
| **One USB-C cable.** An ESP32-c3 gets power and data over the same cable, so there’s no battery and no parking. |Working |
