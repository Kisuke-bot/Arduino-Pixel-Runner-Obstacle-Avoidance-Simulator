# Arduino-Pixel-Runner-Obstacle-Avoidance-Simulator
# Pixel Runner 🏃‍♂️

**Pixel Runner** is an Arduino-based endless runner game inspired by retro handheld LCD games.  
The player controls a pixelated runner who must jump over obstacles 🌵 while the terrain scrolls endlessly.  
The game is displayed on a **16x2 I2C LCD** using custom sprites for smooth animation.

---

## 🎯 Features
- Procedural terrain generation 🌵 (randomized obstacle positions)
- Collision detection (game ends on impact)
- Score tracking ⭐ with optional persistent high-score storage
- Button-controlled jumping (interrupt-based for fast response)

---

## 🛠 Hardware Requirements
- Arduino Uno (or compatible microcontroller)
- 16x2 I2C LCD Display
- Tactile push button 🔘
- Pull-up resistor circuit for stable button input

---

## 💻 Software Design

### Custom Character Sprites
- Up to **7 custom 5x8 pixel sprites** stored in LCD CGRAM:
  - Runner animations 🏃
  - Jump frame
  - Obstacles 🌵
  - Optional star ⭐ for collectibles
- Smooth animation by cycling sprite states each frame.

### Game Engine
- **Main loop**: handles terrain scrolling, collision checks, and score updates.
- **Interrupt Service Routine (ISR)**: ensures fast and responsive jumps.
- **Finite State Machine (FSM)**: manages states – running, jumping, falling, game over.

### Procedural Terrain
- Randomized obstacle spawning with adjustable difficulty.
- Circular buffer for memory-efficient terrain storage.

### Scoring & Persistence
- Score increases over distance traveled.
- Optional **EEPROM** save for high scores across power cycles.
- Game over screen shows high score before restart.

