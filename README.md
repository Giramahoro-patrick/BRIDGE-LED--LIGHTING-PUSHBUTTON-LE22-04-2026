# BRIDGE-LED--LIGHTING-PUSHBUTTON-LE22-04-2026
int buttonPin = 2;

int led1 = 8;
int led2 = 9;
int led3 = 10;

int buttonState = 0;
int lastButtonState = 0;
bool ledState = false;

void setup() {
  pinMode(buttonPin, INPUT);

  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
}

void loop() {

  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH && lastButtonState == LOW) {
    ledState = !ledState; 
    delay(200);            
  }

  lastButtonState = buttonState;

  if (ledState == true) {
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, HIGH);
  } 
  else {
    digitalWrite(led1, LOW);
    digitalWrite(led2, LOW);
    digitalWrite(led3, LOW);
  }

}
