# TEC-284-Quiz1
Create a RGB LED program that allows the buttons to display color when pushed.
//Pin definitions
const int redPin = 9;
const int greenPin = 10;
const int bluePin = 11;

const int buttonPinRed = 2;    //Button for red color
const int buttonPinGreen = 3;  //Button for green color
const int buttonPinBlue = 4;   //Button for blue color

//Variables to store button states
bool redState = 0;
bool greenState = 0;
bool blueState = 0;


void setup() {
  Serial.begin(9600);

  //Initialize RGB LED pins as output
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);

  //Initialize buutton pins as input
  pinMode(buttonPinRed, INPUT_PULLUP);
  pinMode(buttonPinGreen, INPUT_PULLUP);
  pinMode(buttonPinBlue, INPUT_PULLUP);


}

void loop() {
  //Read button states
  displayRGBLED();
}
  void displayRGBLED() {
  bool redState = digitalRead(buttonPinRed);
  bool greenState = digitalRead(buttonPinGreen);
  bool blueState = digitalRead(buttonPinBlue);
  
  //Check if button 1 is pressed(Red color)
  if (redState == LOW && greenState == HIGH && blueState == HIGH) {
    digitalWrite(redPin, HIGH);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, LOW);
    Serial.println("RED");
  }

  //Check if button 2 is pressed(Green color)
  else if (redState == HIGH && greenState == LOW && blueState == HIGH) {
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, HIGH);
    digitalWrite(bluePin, LOW);
    Serial.println("GREEN");
  }

  //Check if button 3 is pressed(Blue color)
  else if (redState == HIGH && greenState == HIGH && blueState == LOW) {
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, HIGH);
    Serial.println("BLUE");
  }

  else (redState == HIGH && greenState == HIGH && blueState == HIGH);
  {
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, LOW);
    //Serial.println("OFF");
  }

  if (redState == LOW && greenState == LOW && blueState == HIGH) {
    digitalWrite(redPin, HIGH);
    digitalWrite(greenPin, HIGH);
    digitalWrite(bluePin, LOW);
  }

    else if (redState == HIGH && greenState == LOW && blueState == LOW) {
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, HIGH);
    digitalWrite(bluePin, HIGH);
    }

    else if (redState == LOW && greenState == HIGH && blueState == LOW) {
    digitalWrite(redPin, HIGH);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, HIGH);
    }
    
}
