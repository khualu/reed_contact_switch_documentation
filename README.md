# reed_contact_switch_documentation
How to use the reed contact switch for the minor Makerslab at the Hogeschool van Amsterdam

## For each component your researched, include in your documentation: 
- Name and image of component
- Is it a sensor or an actuator?
- Datasheet and link to a supplier
- Links to libraries needed
- (Fritzing) schematic of the working circuit
- Links to tutorials used
- Working, annotated Arduino code for this component
- GIFs of the working components and output in serial monitor
- Common use case as well as less common use case that especially interests you
- Problems encountered, solutions found

## Reed contact Switch:
![Reed contact switch](https://i.imgur.com/0R3LZ6w.jpg)

- Sensor
- Where to buy: https://www.kiwi-electronics.nl/magneetcontact-schakelaar-deur-sensor&search=reed%20contact&description=true
- Links to libraries needed: No libraries needed
- Fritzing schematics
![Reed contact schematics](https://i.imgur.com/bOzx0Ou.png)
- Code:
```
//Defining the pin the Reed Contact is on
#define kliko D1

void setup() {
  Serial.begin(115200); // it's a convention to put on which channel the console reads as first
  pinMode(kliko, INPUT_PULLUP); //from: https://learn.sparkfun.com/tutorials/reed-switch-hookup-guide/all
}

void loop(){
    if (digitalRead(kliko)==LOW){ // 'if circuit is closed then do the next'
      Serial.println("kliko is dicht"); //print to the console the message
      delay(500); // stop the code for 500ms
    }
    
    else { //'if the circuit is NOT closed then'
      Serial.println("kliko is open");
      delay(500);
} 
```
