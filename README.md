# EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD

### NAME: GANESH G
### REG NO.: 212223230059

## Aim: 
To Interface a 4X4 matrix keypad and show the output on 16X2 LCD display to ARM controller , and simulate it in Proteus
## Components required: 
STM32 CUBE IDE, Proteus 8 simulator .
## Theory:

![image](https://github.com/vasanthkumarch/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/36288975/2a4a795e-1674-4329-ae07-3f5e8d5073e2)

4×4 Keypad Module Pin Diagram
 
4x4 Keypad module Pin Diagram
4×4 Keypad module Pin Diagram
Pin Number	Pin Name	Description
1	R1	Taken out from 1st  ROW
2	R2	Taken out from 2nd  ROW
3	R3	Taken out from 3rd  ROW
4	R4	Taken out from 4th  ROW
5	C1	Taken out from 1st  COLUMN
6	C2	Taken out from 2nd COLUMN
7	C3	Taken out from 3rd  COLUMN
8	C4	Taken out from 4th  COLUMN
4×4 Matrix Keypad Module Hardware Overview
These Keypad modules are made of thin, flexible membrane material. The 4 x4 keypad module consists of 16 keys, these Keys are organized in a matrix of rows and columns. All these switches are connected to each other with a conductive trace. Normally there is no connection between rows and columns. When we will press a key, then a row and a column make contact.

## Procedure : 
 ## LCD 16X2 
   16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like,
   8×1, 8×2, 10×2, 16×1, etc. But the most used one is the 16*2 LCD, hence we are using it here.

All the above mentioned LCD display will have 16 Pins and the programming approach is also the same and hence the choice is left to you. 
Below is the Pinout and Pin Description of 16x2 LCD Module:

![image](https://user-images.githubusercontent.com/36288975/233858086-7b1a88a2-f941-475c-86c2-b3bae68bdf7e.png)
![image](https://user-images.githubusercontent.com/36288975/233857710-541ac1c2-786c-4dfc-b7b5-e3a4868a9cb6.png)
![image](https://user-images.githubusercontent.com/36288975/233857733-05df5dbf-1a1e-479e-85bb-8014a39ad878.png)

4-bit and 8-bit Mode of LCD:

The LCD can work in two different modes, namely the 4-bit mode and the 8-bit mode. In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble. For those of you who don’t know what a nibble is: a nibble is a group of four bits, so the lower four bits (D0-D3) of a byte form the lower nibble while the upper four bits (D4-D7) of a byte form the higher nibble. This enables us to send 8 bit data.

Whereas in 8 bit mode we can send the 8-bit data directly in one stroke since we use all the 8 data lines.

 8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs 8 data lines connected to the microcontroller. This will make us run out of I/O pins on our MCU, so 4-bit mode is widely used. No control pins are used to set these modes. 
 LCD Commands:

There are some preset commands instructions in LCD, which we need to send to LCD through some microcontroller. Some important command instructions are given below:

Hex Code

Command to LCD Instruction Register

0F

LCD ON, cursor ON

01

Clear display screen

02

Return home

04

Decrement cursor (shift cursor to left)

06

Increment cursor (shift cursor to right)

05

Shift display right

07

Shift display left

0E

Display ON, cursor blinking

80

Force cursor to beginning of first line

C0

Force cursor to beginning of second line

38

2 lines and 5×7 matrix

83

Cursor line 1 position 3

3C

Activate second line

08

Display OFF, cursor OFF

C1

Jump to second line, position 1

OC

Display ON, cursor OFF

C1

Jump to second line, position 1

C2

Jump to second line, position 2
 
## Procedure:
 1. click on STM 32 CUBE IDE, the following screen will appear 
 ![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)

 2. click on FILE, click on new stm 32 project 
 ![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)
![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)
3. select the target to be programmed  as shown below and click on next 

![image](https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png)

4.select the program name 
![image](https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png)


5. corresponding ioc file will be generated automatically 
![image](https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png)

6.select the appropriate pins as gipo, in or out, USART or required options and configure 
![image](https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png)
![image](https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png)


7.click on cntrl+S , automaticall C program will be generated 
![image](https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png)
![image](https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png)
8. edit the program and as per required 
![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)

9. Add necessary library files of LCD 16x2 , write the program and use project and build  

![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)
10. once the project is bulild 
![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)

11. click on debug option 
![image](https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png)


12.  Creating Proteus project and running the simulation
We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.

13. Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE. 
14. After creation of the circuit as per requirement as shown below 

![image](https://user-images.githubusercontent.com/36288975/233856847-32bea88a-565f-4e01-9c7e-4f7ed546ddf6.png)

14. Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes.
https://engineeringxpert.com/wp-content/uploads/2022/04/26.png

15. click on debug and simulate using simulation as shown below 

![image](https://user-images.githubusercontent.com/36288975/233856904-99eb708a-c907-4595-9025-c9dbd89b8879.png)

## CIRCUIT DIAGRAM 
![image](https://github.com/user-attachments/assets/0bdf85da-c089-4589-a5c0-a82e86a4c1c2)
 

## STM 32 CUBE PROGRAM :
#include "main.h"
#include <stdbool.h>
#include "lcd.h"
bool col1,col2,col3,col4;
void SystemClock_config(void);
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1){
    key();
    HAL_Delay(1000);}}
void key(){
	 Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
	  Lcd_PinType pins[] = { GPIO_PIN_3, GPIO_PIN_2, GPIO_PIN_1, GPIO_PIN_0 };
	  Lcd_HandleTypeDef lcd;
	  lcd = Lcd_create(ports, pins, GPIOB, GPIO_PIN_0, GPIOB, GPIO_PIN_1, LCD_4_BIT_MODE);
	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_RESET);
	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);
	  col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	  col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	  col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	  col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);
	  if(!col1){
		  Lcd_cursor(&lcd, 0,1);
		  Lcd_string(&lcd, " 7\n");
		  col1=1;}
	  else if(!col2){
	  		  Lcd_cursor(&lcd, 0,1);
	  		  Lcd_string(&lcd, " 8\n");
	  		  col2=1;}
	  else if(!col3){
	  	  		  Lcd_cursor(&lcd, 0,1);
	  	  		  Lcd_string(&lcd, "9\n");
	  	  		  col3=1;}
	  else if(!col4)
{
	  	  		  Lcd_cursor(&lcd, 0,1);
	  	  		  Lcd_string(&lcd, "/ \n");
	  	  		  col4=1;}
	  HAL_Delay(200);
	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	  	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_RESET);
	  	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	  	  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);
	  	  col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	  	  col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	  	  col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	  	  col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);
	  	  if(!col1){
	  		  Lcd_cursor(&lcd, 0,1);
	  		  Lcd_string(&lcd, " 4\n");
	  		  col1=1;}
	  	  else if(!col2){
	  	  		  Lcd_cursor(&lcd, 0,1);
	  	  		  Lcd_string(&lcd, " 5\n");
	  	  		  col2=1;}
	  	  else if(!col3){
	  	  	  		  Lcd_cursor(&lcd, 0,1);
	  	  	  		  Lcd_string(&lcd, " 6\n");
	  	  	  		  col3=1;}
	  	  else if(!col4){
	  	  	  		  Lcd_cursor(&lcd, 0,1);
	  	  	  		  Lcd_string(&lcd, " X\n");
	  	  	  		  col4=1;}
	  	HAL_Delay(200);
	  	HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	  		  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	  		  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_RESET);
	  		  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_SET);
	  		  col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	  		  col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	  		  col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	  		  col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);
	  		  if(!col1){
	  			  Lcd_cursor(&lcd, 0,1);
	  			  Lcd_string(&lcd, "1\n");
	  			  col1=1;}
	  		  else if(!col2){
	  		  		  Lcd_cursor(&lcd, 0,1);
	  		  		  Lcd_string(&lcd, " 2\n");
	  		  		  col2=1;}
	  		  else if(!col3){
	  		  	  		  Lcd_cursor(&lcd, 0,1);
	  		  	  		  Lcd_string(&lcd, "3\n");
	  		  	  		  col3=1;}
	  		  else if(!col4){
	  		  	  		  Lcd_cursor(&lcd, 0,1);
	  		  	  		  Lcd_string(&lcd, "-\n");
	  		  	  		  col4=1;}
	  		  HAL_Delay(200);
	  		HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0, GPIO_PIN_SET);
	  			  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_1, GPIO_PIN_SET);
	  			  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_2, GPIO_PIN_SET);
	  			  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_3, GPIO_PIN_RESET);
	  			  col1 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_4);
	  			  col2 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_5);
	  			  col3 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_6);
	  			  col4 = HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_7);
	  			  if(!col1){
	  				  Lcd_cursor(&lcd, 0,1);
	  				  Lcd_string(&lcd, "ON/C\n");
	  				  col1=1;}
	  			  else if(!col2){
	  			  		  Lcd_cursor(&lcd, 0,1);
	  			  		  Lcd_string(&lcd, " 0\n");
	  			  		  col2=1;}
	  			  else if(!col3){
	  			  	  		  Lcd_cursor(&lcd, 0,1);
	  			  	  		  Lcd_string(&lcd, " =\n");
	  			  	  		  col3=1;}
	  			  else if(!col4){
	  			  	  		  Lcd_cursor(&lcd, 0,1);
	  			  	  		  Lcd_string(&lcd, " +\n");
	  			  	  		  col4=1;}
	  			  else{
	  				  Lcd_cursor(&lcd,0,1);
	  				  Lcd_string(&lcd,"no key pressed");}}
void SystemClock_Config(void){
  RCC_OscInitTypeDef RCC_OscInitStruct = {0};
  RCC_ClkInitTypeDef RCC_ClkInitStruct = {0};
  __HAL_RCC_PWR_CLK_ENABLE();
  __HAL_PWR_VOLTAGESCALING_CONFIG(PWR_REGULATOR_VOLTAGE_SCALE2);
  RCC_OscInitStruct.OscillatorType = RCC_OSCILLATORTYPE_HSI;
  RCC_OscInitStruct.HSIState = RCC_HSI_ON;
  RCC_OscInitStruct.HSICalibrationValue = RCC_HSICALIBRATION_DEFAULT;
  RCC_OscInitStruct.PLL.PLLState = RCC_PLL_NONE;
  if (HAL_RCC_OscConfig(&RCC_OscInitStruct) != HAL_OK){
    Error_Handler();}
  RCC_ClkInitStruct.ClockType = RCC_CLOCKTYPE_HCLK|RCC_CLOCKTYPE_SYSCLK
                              |RCC_CLOCKTYPE_PCLK1|RCC_CLOCKTYPE_PCLK2;
  RCC_ClkInitStruct.SYSCLKSource = RCC_SYSCLKSOURCE_HSI;
  RCC_ClkInitStruct.AHBCLKDivider = RCC_SYSCLK_DIV1;
  RCC_ClkInitStruct.APB1CLKDivider = RCC_HCLK_DIV1;
  RCC_ClkInitStruct.APB2CLKDivider = RCC_HCLK_DIV1;
  if (HAL_RCC_ClockConfig(&RCC_ClkInitStruct, FLASH_LATENCY_0) != HAL_OK){
    Error_Handler();}}
static void MX_GPIO_Init(void){
  GPIO_InitTypeDef GPIO_InitStruct = {0};
  __HAL_RCC_GPIOC_CLK_ENABLE();
  __HAL_RCC_GPIOA_CLK_ENABLE();
  __HAL_RCC_GPIOB_CLK_ENABLE();
  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2, GPIO_PIN_RESET);
  HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3, GPIO_PIN_RESET);
  HAL_GPIO_WritePin(GPIOB, GPIO_PIN_0|GPIO_PIN_1, GPIO_PIN_RESET);
  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOC, &GPIO_InitStruct);
  GPIO_InitStruct.Pin = GPIO_PIN_3;
  GPIO_InitStruct.Mode = GPIO_MODE_ANALOG;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  HAL_GPIO_Init(GPIOC, &GPIO_InitStruct);
  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOA, &GPIO_InitStruct);
  GPIO_InitStruct.Pin = GPIO_PIN_4|GPIO_PIN_5|GPIO_PIN_6|GPIO_PIN_7;
  GPIO_InitStruct.Mode = GPIO_MODE_INPUT;
  GPIO_InitStruct.Pull = GPIO_PULLUP;
  HAL_GPIO_Init(GPIOC, &GPIO_InitStruct);
  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOB, &GPIO_InitStruct);}
void Error_Handler(void){
  __disable_irq();
  while (1)
  {
  }
}#ifdef  USE_FULL_ASSERT
void assert_failed(uint8_t *file, uint32_t line){
}
#endif


## Output screen shots of proteus  :
![image](https://github.com/user-attachments/assets/917c825d-64c2-4272-9ad2-ad1cdae8fd59)

## CIRCUIT DIAGRAM (EXPORT THE GRAPHICS TO PDF AND ADD THE SCREEN SHOT HERE): 
![image](https://github.com/user-attachments/assets/8b3286f1-58d1-45a0-8e4b-573f0ec0f904)
 
 
## Result :
Interfacing a 4x4 keypad with ARM microcontroller are simulated in proteus and the results are verified.
