## How to Use the GIO Port B LED Control Code

This code demonstrates how to control General Input/Output (GIO) pins on the Hercules TMS570LC43x LaunchPad (LAUNCHXL2-570LC43). The code specifically initializes GIO Port B, configures Pin 6 as an output, and sets it to a high state to turn on an LED.

### Steps to Run the Code:

1. **Install HALCoGen and CCS (Code Composer Studio):**
   - Ensure you have **Texas Instruments HALCoGen** and **Code Composer Studio (CCS)** installed on your system.

2. **Set Up the Development Environment:**
   - Open **HALCoGen** and generate the necessary drivers and files for the TMS570LC43x LaunchPad.
   - Import the project into **CCS**.

3. **Add the Code to Your Project:**

   - Copy the code into the `HL_sys_main.c` file or any main source file for your project.

4. **Understand the Key Code Sections:**

   - **GIO Module Initialization:**
     ```c
     gioInit(); 
     ```
     This function initializes the GIO module, preparing it for input/output operations.
   
   - **Set GIO Pin Direction:**
     ```c
     gioSetDirection(gioPORTB, 0x40);
     ```
     This sets Pin 6 of GIO Port B as an output (0x40 in binary = 01000000), where only bit 6 is set to `1` (output), and other bits are `0` (input).
   
   - **Set GIO Pin to High (Turn On LED):**
     ```c
     gioSetBit(gioPORTB, 6, 1);
     ```
     This command sets GIO Port B, Pin 6 to a high state (`1`), which typically turns on the LED connected to that pin.

   - **Infinite Loop:**
     ```c
     while (1);
     ```
     The infinite loop ensures the microcontroller continues running indefinitely. Future logic can be added here for more operations.

5. **Build and Run the Project:**
   - Compile the code in CCS.
   - Flash the binary to the Hercules LaunchPad.
   - Upon execution, the LED connected to GIO Port B, Pin 6 should turn on.

6. **Modify as Needed:**
   - You can modify the code to control different GIO pins by adjusting the pin number in `gioSetDirection()` and `gioSetBit()`.

### Additional Notes:
- This code is a basic example of GIO port control and can be expanded to include more complex logic or additional peripherals.
- Ensure the hardware is correctly set up and that an LED is connected to GIO Port B, Pin 6 for visual feedback.
