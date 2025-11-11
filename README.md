# Multi-Level Security Access System

A multi-level security system using LPC2148 that ensures high protection through three-tier authentication—RFID verification, password entry, and fingerprint recognition. It controls access via EEPROM-stored credentials and a DC motor lock, integrating peripherals like LCD, keypad, and UART for secure, real-time access control.

## Features

- **Three-Tier Authentication**:
  - **RFID Verification**: Only users with valid RFID cards are allowed to proceed.
  - **Password Entry**: Verified RFID users must enter a correct password via the keypad.
  - **Fingerprint Recognition**: Final authentication using a fingerprint sensor.
- **EEPROM Integration**: Credentials for users (RFID numbers, passwords, fingerprints) are securely stored and managed in EEPROM.
- **Access Control Hardware**:
  - DC motor-driven lock for physical access control
  - LCD display for system feedback and status updates
  - Keypad for manual input
  - UART for communication/logging
- **Security & Logging**: Alerts for unauthorized access and logs all access attempts.
- **Real-Time Operation**: Immediate feedback and responses based on input authentication.

## Hardware Requirements

- LPC2148 microcontroller
- RFID reader & compatible cards/tags
- 4x4 Matrix Keypad
- Fingerprint sensor module (e.g., R305 or equivalent)
- 16x2 LCD display
- DC Motor (for lock mechanism)
- EEPROM (for credential storage)
- UART communication interface
- Power supply (suitable for LPC2148 and peripherals)

## Software (Firmware) Information

- **Language**: C (100%)
- **Platform**: Keil uVision (for ARM7/LPC2148)
- **IDE**: Keil, with appropriate flash loader for LPC2148
- **Files**:
  - Main firmware source code files (`main.c`, etc.)
  - Peripheral handling (`lcd.c`, `keypad.c`, `rfid.c`, `fingerprint.c`, `eeprom.c`, etc.)
  - Hardware abstraction and configuration

## How the System Works

1. **Idle State**: System waits for RFID tag to be shown.
2. **RFID Authentication**: If recognized, prompts for password input.
3. **Password Verification**: If correct, requests fingerprint scan.
4. **Fingerprint Recognition**: Grants access and unlocks door if matched.
5. **Logging**: Each step and access attempt is logged via UART and (optionally) EEPROM.
6. **Failure Scenarios**: Three failed attempts trigger an alert and lock the system temporarily.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/sandeep-643/Multi-Level-Security-Access-System.git
```

### 2. Open Project in Keil uVision

1. Launch Keil uVision.
2. Import or open the provided project/workspace file (if present).
3. Ensure all source files are included in your project.

### 3. Build & Flash

1. Connect your LPC2148 board via appropriate programmer.
2. Build the project.
3. Flash the firmware to the board.

### 4. Set Up Hardware

- Connect all listed peripherals as per schematic (see included PDF documentation).
- Power up the system and observe the LCD for the startup screen.

### 5. Add User Credentials

- Use the admin/master card to enroll new users (RFID, password, fingerprint).
- Instructions for enrolling/updating users are displayed on LCD during setup.

## Project Documentation

Full system details, schematics, user flow diagrams, and hardware setup instructions are provided in the project report:

- [📄 Project Documentation (PDF)](./YOUR_PROJECT_DOCUMENTATION.pdf)

*(Update the file name/path above with your actual PDF location in the repo)*

## Repository Structure

```text
/
├── src/                 # Source code
│   ├── main.c
│   ├── lcd.c
│   ├── keypad.c
│   ├── rfid.c
│   ├── fingerprint.c
│   ├── eeprom.c
│   └── ...other files
├── include/             # Header files (if applicable)
├── docs/                # Additional documentation (schematics, diagrams)
│   └── YOUR_PROJECT_DOCUMENTATION.pdf
├── README.md            # This file!
└── ...                  # Other configuration and project files
```

## Credits

- Developed by: [Sandeep Sri krishna]
- Institution/Organization: [vector india]


---

**Note:**  
- For detailed setup, workflows, and troubleshooting, refer to the documentation PDF.
- Contributions and issues welcome!
