
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


