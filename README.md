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
