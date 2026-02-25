
 INTERFACING DAC WITH 8086 KIT AND GENERATING SAWTOOTH AND SQUARE WAVEFORMS

## AIM
To write an assembly language program in 8086 to generate Sawtooth and Square waveforms using DAC.

---

## APPARATUS REQUIRED

| S. No | Item              | Specification   | Quantity |
|-------|------------------|-----------------|----------|
| 1     | Microprocessor kit | 8086            | 1        |
| 2     | Power Supply      | +5 V DC, +12 V DC | 1      |
| 3     | DAC Interface board | -              | 1        |

---

## ALGORITHM

### Measurement of Analog Voltage
1. Send the digital value to DAC.  
2. Read the corresponding analog value at its output.  

### Waveform Generation

#### Square Waveform
1. Send low value (00) to the DAC.  
2. Introduce suitable delay.  
3. Send high value to DAC.  
4. Introduce delay.  
5. Repeat the above procedure.  

#### Sawtooth Waveform
1. Load low value (00) to accumulator.  
2. Send this value to DAC.  
3. Increment the accumulator.  
4. Repeat step (ii) and (iii) until accumulator value reaches FF.  
5. Repeat the above procedure from step 1.  

---

## PROGRAMS

# 8086 Assembly Programs – DAC Interfacing

## Program: Square Wave

| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1000            | MOV AL,00H  | Load 00H in Accumulator           |
| 1003            |  OUT 0C8H,AL | Send through output port         |
| 1005            |  CALL DELAY(1100)  | CALL PROGRAM TO 1100      |
| 1008            |  MOV AL,0FFH |   Load 00H in Accumulator       |
| 100A            |   OUT 0C8H,AL|  Send through output port       |
| 100D            |  CALL DELAY(1100) | CALL PROGRAM TO 1100       |


| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1100            | MOV CX,0505  | Load 0505H in Accumulator           |
| 1103            |  DEC CX | Decrement CX        |
| 1105           |  JNZ 1104  | RPEAT UNTILL ZERO      |
| 1108            |   RET |   RETURN TO MAIN PROGRAM      |


# Program: Sawtooth wave

## Assembly Program

| Memory Location | Program Instruction   | Comments                        |
|-----------------|-----------------------|---------------------------------|
| `1000`          | `START: MOV AL,00H`  | Load `00H` in accumulator       |
| `1003`          | `LOOP : OUT 0C8H,AL` | Send through output port        |
| `1005`          | `INC AL`             | Increment contents of accumulator |
| `1007`          | `JNC LOOP`           | Jump if no carry (continue loop) |
| `1009`          | `JMP START`          | Go to starting location         |

---

## Tabulation

![WhatsApp Image 2026-02-25 at 10 48 09 AM](https://github.com/user-attachments/assets/696dd5d1-7f83-4b17-9669-51c337ee9409)


## Model Graph
Square Wave
<img width="1280" height="686" alt="553334749-b4416ced-059a-4b18-916d-c2c84903a4d2" src="https://github.com/user-attachments/assets/4df515dc-80ee-491c-843e-4dec17d24324" />

Sawtooth Wave

<img width="1280" height="730" alt="553334822-d15b554f-a5fe-49e0-b87e-005fc2b04af2" src="https://github.com/user-attachments/assets/453b3c21-90eb-4a17-825b-480545e45f95" />



## OUTPUT IMAGE OF DAC(SAWTOOTH WAVE FROM DSO AND SQUARE WAVE FROM DSO)
Square Wave
<img width="1174" height="657" alt="553334897-de492995-fac7-48f3-9fd5-25433d71606d" src="https://github.com/user-attachments/assets/9af8b746-ab94-4073-8750-e5d97c9bca92" />
Sawtooth Wave
<img width="950" height="572" alt="553334976-9e53a8f3-bcf6-4696-893d-44b3292b8088" src="https://github.com/user-attachments/assets/b901de9a-6811-43b4-be2a-e4349307717e" />


## Result


Thus, the **DAC was interfaced with 8086** and different **waveforms** were successfully generated.




