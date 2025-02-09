# UART Palindrome Checker  

## Project Overview  
This project is a **PLP assembly program** that receives a string of characters via **UART (Universal Asynchronous Receiver-Transmitter)**, checks if the string is a **palindrome**, and prints either **"Yes"** or **"No"** accordingly.  

A **palindrome** is a word or phrase that reads the same **forward and backward**, ignoring spaces and case differences. Strings are **terminated with a period ('.')**, and multiple strings can be processed sequentially.

---

## Features  
**Receives input via UART**  
**Ignores spaces** when checking for palindromes  
**Case insensitive** (converts lowercase to uppercase)  
**Processes multiple strings in sequence**  
**Uses a provided print function** to display results  

---

## How It Works  
1. **Receives Characters via UART**  
   - The program continuously reads characters from UART until it detects a **period ('.')**, marking the end of a string.  

2. **Processes the Input**  
   - **Ignores spaces**  
   - **Converts lowercase letters to uppercase**  
   - **Stores characters in an array**  

3. **Checks for a Palindrome**  
   - Compares characters from **both ends of the array**  
   - If all pairs match → **Prints "Yes"**  
   - If any mismatch occurs → **Prints "No"**   

---

## Code Structure  
The program is divided into six main functions:

| Function Name     | Description |
|------------------|-------------|
| `poll_UART`      | Polls UART for new characters and reads them. |
| `period_check`   | Checks for a period (`.`) and calls `palindrome_check`. |
| `space_check`    | Ignores spaces in the input. |
| `case_check`     | Converts lowercase letters to uppercase. |
| `array_push`     | Stores valid characters in an array. |
| `palindrome_check` | Compares characters and determines if the string is a palindrome. |

---

## Setup Instructions  
1. Open **PLPTool** and load the **.plp file** (`PalindromeChecker.plp`).  
2. Ensure **project3_lib.asm** is included.  
3. Run the simulation and input test strings via UART.  
4. Check the **CPU Memory Visualization** and **Watcher Window** for debugging:  
   - Watch **$v0, $s1, $s2** in the Watcher Window.  
   - Ensure the **start of the array** is visible in CPU Memory Visualization.  

---

## Example Input & Output  

**Input:**  
  abba. data. A nut for a jar of Tuna.

**Output:**  
  Yes No Yes
