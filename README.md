##라인센서 시스템

#define ledPin 13
#define inPin   7
int val = 0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(inPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  val = digitalRead(inPin);

  Serial.print("Input date=");
  Serial.println(val);
  digitalWrite(ledPin, val);
}
디지털리드 시스템


------
#define ledPin 13
int linesensor_data[5] = {0,0,0,0,0};
int linesensor_pin[5] = {2,3,4,5,6};

void setup() {
  int i;
  pinMode(ledPin, OUTPUT);
  for(i=0;i<5;i++)
  {
  pinMode(linesensor_pin[i], INPUT);
  }
  Serial.begin(9600);
}

void loop() {
  int i;
  for(i=0;i<5;i++)
  {
    linesensor_data[i] = digitalRead(linesensor_pin[i]);
  }
  Serial.print("Input date=");
  for(i=0;i<5;i++)
  {
    Serial.print(linesensor_data[i]);
    Serial.print("   ");
  }
  Serial.println("   ");
}
