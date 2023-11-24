
### Set Pins
```cpp 
  pinMode(2, INPUT); // set pin 2 as INPUT
  pinMode(13, OUTPUT); // set pin 13 as OUTPUT

  digitalWrite(13, HIGH); //writes 1 to the pin 13
  digitalRead(13); //reads the value of the port 13
```


The Arduino UNO board is using the **ATmega328p-PU** microcontroller.
![[Arduino.png]]
*port map of the ATmega328 microcontroller*

### Port Manipulation;

```c
void setup() {  
  DDRD = B00010100;         //Sets D2 and D4 as OUTPUT and the rest as INPUT (not recommended)
  DDRD = DDRD | B00010100;  //This is safer as it sets ONLY pins D2 and D4 as OUTPUT
  
  //Other exampoles
  DDRB |= B00000101;        //Sets only D8 and D10 as OUTPUT
  DDRB &= B11100111;        //Sets only D11 and D12 as INPUT
  DDRC &= B11110110;        //Sets only A0 and A3 as INPUT
}

void loop() { 
	PORTD |= B00000100; //Sets only D2 to HIGH
	PORTB &= !B00000100; //Sets only B2 to LOW (we use ! to invertt the byte)
}
```

[Port manipulation Tutorial](https://electronoobs.com/eng_arduino_tut130.php)

### CD4511

[https://www.build-electronic-circuits.com/4000-series-integrated-circuits/ic-4511/](https://www.build-electronic-circuits.com/4000-series-integrated-circuits/ic-4511/)



```cpp

/*
** Exercice:
**   - The goal of this practical is to let you use everything
**	   you learned in the previous ones to design a usefull circuit
**   - Your task is to design a circuit to manage a digicode lock
**   - The lock is represented by the green LED: when it is on the
**     lock is open, when it is off the lock is closed.
**   - Your program must handle the following features:
**      - When a numeric key is pressed, you must push everyting
**		  on the displays to the left and write the key value on
**		  left-most display.
**      - When the 'D' key is pressed, you must reset the display to '0000'
**		- When the 'C' key is pressed, you must delete the last
**		  entered number and push everything else to the left
**		- When the '#' key is pressed, you must verify the code and
**        unlock the lock if the entered code is correct
**      - Bonus: When the lock is opened and the 'A' key is pressed,
**		  you may change the password to be whatever is on the 
**		  display, lock the lock and reset the display to '0000'
**        
**
*/

#include <Keypad.h>

// TODO: Write the pin configuration of the registers and the keypad configuration

const byte PIN_DS = 10; // Input PIN of the shift register
const byte PIN_STCP = 11; // Clock PIN of the shift register
const byte PIN_SHCP = 12; // Write clock PIN of the shift register
const byte PIN_LOCK = 13;

bool unlocked = false;


// Keypad configurationconst byte ROWS = 4; 
const byte ROWS = 4; 
const byte COLS = 4; 

char hexaKeys[ROWS][COLS] = {
  {'1', '2', '3', 'A'},
  {'4', '5', '6', 'B'},
  {'7', '8', '9', 'C'},
  {'*', '0', '#', 'D'}
};

byte rowPins[ROWS] = {9, 8, 7, 6}; 
byte colPins[COLS] = {5, 4, 3, 2}; 

Keypad customKeypad = Keypad(makeKeymap(hexaKeys), rowPins, colPins, ROWS, COLS);

// The currently displayed numbers
char currentCode[] = {'0', '0', '0', '0'};

// The password of the lock
char code[] = {'4', '2', '4', '2'};

void setup()
{
//  Serial.begin(9600); // Debug
  // TODO: Write the setup function
  pinMode(PIN_DS, OUTPUT);
  pinMode(PIN_STCP, OUTPUT);
  pinMode(PIN_SHCP, OUTPUT);
  pinMode(PIN_LOCK, OUTPUT);
}

bool compare_code(){
  for (int i = 0; i < 4; i++){
  	if (currentCode[i] != code[i])
      return false;
  }
  return true;
}

void change_code(){
  for (int i = 0; i < 4; i++)
  	code[i] = currentCode[i];
}

void push_key(int nb) {
  // TODO: Write the push_key() function, you can use the same
  //       algorithm as in previous exercice, but keep in mind that
  //       you now need to be able to write numbers up to 15
  
  int a[4];
  
  for (int i = 3; i >= 0; i--)
  {
    a[i] = nb%2;
    nb /= 2;
  }
  
  for (int i = 0; i < 4; i++)
  {
  	digitalWrite(PIN_DS, a[i]);
    digitalWrite(PIN_SHCP, HIGH);
    digitalWrite(PIN_SHCP, LOW);
    digitalWrite(PIN_DS, LOW);
    digitalWrite(PIN_STCP, HIGH);
    digitalWrite(PIN_STCP, LOW);
  }
}

void push_code() {
	for (int i = 0; i < 4; i++)
      push_key(currentCode[i] - '0');
}

void loop()
{
  char key = customKeypad.getKey();
  
  if (!key){
  	delay(50);
    return;
  }
  
  switch(key)
  {
  	case 'A':
    	if (unlocked)
          change_code();
    	break;
    case 'B':
    	//
    	break;
    case 'C':
    	// TODO revert
    	for (int i = 3; i >= 1; i--)
          currentCode[i] = currentCode[i - 1];
    
    	currentCode[0] = '0';
        push_code();
    	break;
    case 'D':
    	for (int i = 0; i < 4; i++)
    		currentCode[i] = '0';
        push_code();
    	break;
    case '#':
    	if (compare_code()){
        	unlocked = true;
          	digitalWrite(PIN_LOCK, HIGH);
        } else {
        	unlocked = false;
          	digitalWrite(PIN_LOCK, LOW);
            for (int i = 0; i < 4; i++)
                currentCode[i] = '0';
            push_code();
        }
    	break;
    default:  
        for (int i = 1; i< 4; i++)
            currentCode[i-1] = currentCode[i];
  
  		currentCode[3] = key; 
    	push_key(key - '0');
  }
  
  delay(50); // For performances
}

```