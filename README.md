# 🚦 Embedded Traffic Light Controller Using STM32

## 📌 Project Overview

The **Embedded Traffic Light Controller** is a microcontroller-based project developed using the STM32F446RE microcontroller.

It simulates a traffic light system with two operating modes:

- **Automatic Mode:** Red, Yellow, and Green LEDs turn ON sequentially, with a 1-second delay between each state.
- **Manual Mode:** The user controls the traffic light sequence using the onboard push button.

The project uses GPIO interfacing and External Interrupts (EXTI) to control traffic light operation.

## 🎯 Objectives

- Understand STM32 GPIO configuration.
- Implement LED interfacing using GPIO output pins.
- Understand external interrupt handling.
- Implement automatic and manual operating modes.
- Develop basic Embedded C programming skills.
- Understand state-based control logic.

## 🛠️ Hardware Components

| Component | Quantity |
|---|---:|
| STM32 Nucleo-F446RE Board | 1 |
| Red LED | 1 |
| Yellow LED | 1 |
| Green LED | 1 |
| Current-limiting resistors | As required |
| Onboard Push Button (B1) | 1 |
| Connecting wires | As required |

## 🔌 Pin Configuration

| Component | STM32 Pin | Configuration |
|---|---|---|
| Red LED | PA5 | GPIO Output |
| Yellow LED | PA6 | GPIO Output |
| Green LED | PA7 | GPIO Output |
| Onboard Push Button (B1) | PC13 | External Interrupt |
| USART2 TX | PA2 | UART Transmit |
| USART2 RX | PA3 | UART Receive |

**Note:** USART2 is initialized in the current program, but UART transmission and reception are not implemented.

## ⚙️ Working Principle

### 1. Automatic Mode

Initially, the system starts in automatic mode.

The LEDs operate in the following sequence:

| Sequence | LED | Duration |
|---|---|---|
| 1 | Red | 1 second |
| 2 | Yellow | 1 second |
| 3 | Green | 1 second |

The sequence continuously repeats.

### 2. Manual Mode

The onboard B1 push button connected to PC13 is used to switch from automatic mode to manual mode.

Each subsequent button press changes the LED state.

| Button Action | LED State |
|---|---|
| First Press | Red |
| Second Press | Yellow |
| Third Press | Green |
| Fourth Press | Red |

The sequence continues with each subsequent button press.

## 🔄 External Interrupt (EXTI)

The onboard push button uses the STM32 External Interrupt feature.

- Button pin: PC13
- Interrupt line: EXTI13
- Interrupt vector: EXTI15_10_IRQn
- Trigger configuration: Falling Edge

When the button is pressed, the `HAL_GPIO_EXTI_Callback()` function is called.

The callback updates the operating mode and LED state.

## 🧠 Program Logic

1. Initialize the STM32 HAL library.
2. Configure the system clock.
3. Initialize GPIO and USART2.
4. Start the traffic light in automatic mode.
5. Turn ON the Red LED for 1 second.
6. Turn ON the Yellow LED for 1 second.
7. Turn ON the Green LED for 1 second.
8. When the onboard button is pressed, switch to manual mode.
9. Each subsequent button press changes the LED state.

## 📚 Concepts Used

- Embedded C Programming
- STM32 Microcontroller
- STM32 HAL Library
- GPIO Input and Output
- External Interrupts (EXTI)
- Interrupt Callback Functions
- State Management
- Conditional Statements
- Switch-Case Statements
- Hardware-Software Integration

## 💻 Software Requirements

- STM32CubeIDE
- STM32CubeMX
- STM32 HAL Library

## 🚀 Applications

- Basic traffic light simulation.
- Learning microcontroller-based control systems.
- Understanding interrupt-driven applications.
- Embedded systems training and experimentation.

## ⭐ Key Features

- Automatic traffic light operation.
- Manual control using an onboard push button.
- Interrupt-based button handling.
- GPIO-based LED control.
- State-based LED switching.

## 🔮 Future Enhancements

- Add pedestrian crossing functionality.
- Implement configurable traffic light timing.
- Add a countdown display using an LCD.
- Add UART-based monitoring and control.
- Implement a more realistic traffic management sequence.

## 📖 Learning Outcomes

Through this project, I gained practical experience in:

- STM32 GPIO configuration and LED interfacing.
- Configuring and handling external interrupts.
- Using STM32 HAL functions.
- Implementing automatic and manual control logic.
- Understanding state transitions in embedded applications.

## 🔗 Project on LinkedIn

I have also shared this project and its key learnings on LinkedIn.

**LinkedIn Project Post:** https://www.linkedin.com/posts/rebisha-rl-9441a734b_stm32-embeddedsystems-embeddedc-activity-7489593952627503104-2cPH?utm_medium=ios_app&rcm=ACoAAFdqWoQBpxP8EiwA1aGoJjvUpxgCz0F-aTI&utm_source=social_share_video_v2&utm_campaign=whatsapp

## 👩‍💻 Author

**Rebisha R L**

Electronics and Communication Engineering

GitHub: rebisha8

LinkedIn: Rebisha R L

## 🏁 Conclusion

This project helped me understand the fundamentals of STM32 microcontroller programming, GPIO interfacing, and external interrupt handling. It provided practical experience in developing a simple embedded control system using Embedded C.
