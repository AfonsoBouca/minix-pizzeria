# Papa's Pizzeria

> A C remake of the classic Papa's Pizzeria game, running on MINIX 3 and
> communicating directly with low-level hardware.

## About

This project is a low-level systems programming remake of the browser game
*Papa's Pizzeria*. The game runs on MINIX 3 and uses custom interrupt-driven
drivers for the timer, keyboard, mouse, real-time clock, and graphics
hardware.

Game logic, rendering, input handling, and timing are implemented in C without
external game frameworks or high-level operating-system abstractions. The
codebase follows a Model-View-Controller (MVC) structure:

- `src/model/` contains the game state and gameplay rules.
- `src/view/` contains rendering, sprites, and drawing utilities.
- `src/game/` contains startup, event handling, and the main loop.
- `include/` contains the public interfaces shared by these components.

## Features

- Graphical interface rendered through direct video-memory access
- Mouse support for menus and gameplay
- Keyboard navigation and shortcuts
- Timer-driven game loop with consistent frame pacing
- RTC integration for date and time information
- Gameplay loop for taking orders, preparing pizzas, and serving customers
- Main menu, options screen, and in-game HUD

## Hardware Interfaces

| Interface | Device | Purpose |
|-----------|--------|---------|
| RTC | Real-time clock | Reads date and time information |
| Timer | i8254 | Drives periodic interrupts and frame timing |
| Keyboard | i8042 / KBC | Handles keyboard scan codes |
| Mouse | PS/2 via KBC | Controls the in-game cursor |
| Graphics | Video card | Sets video mode, maps VRAM, and renders the UI |

## Screenshots

### Main Menu

<img src="project/images/1.jpg" width="600">

### Options Screen

<img src="project/images/2.jpg" width="600">

### Gameplay

<img src="project/images/3.jpg" width="600">
<img src="project/images/4.jpg" width="600">
<img src="project/images/5.jpg" width="600">
<img src="project/images/6.jpg" width="600">
<img src="project/images/7.jpg" width="600">
<img src="project/images/8.jpg" width="600">
<img src="project/images/9.jpg" width="600">
<img src="project/images/10.jpg" width="600">
<img src="project/images/11.jpg" width="600">
<img src="project/images/12.jpg" width="600">
<img src="project/images/13.jpg" width="600">
<img src="project/images/14.jpg" width="600">
<img src="project/images/15.jpg" width="600">

## Build and Run

The project must be compiled and run inside a MINIX 3 environment because it
accesses hardware I/O ports, interrupt vectors, and video memory directly.

```bash
make
lcom_run proj
```

To remove generated build files:

```bash
make clean
```

## Credits and License

Created by:

- Afonso Bouça
- Bruno Dias
- Diogo Coelho
- Guilherme Silva

This project is a non-commercial educational remake. The Papa's Pizzeria
concept and original assets belong to their respective owners, Flipline
Studios.
