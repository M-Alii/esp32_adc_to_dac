//# esp32_adc_to_dac



const int ADC_In = 15; //ESP32 ADC2_3(GPIO 15)
int POT_VALUE_IN = 0;

int DAC_OUTPUT_PIN = 25;// ESP32 DAC1(GPIO 25)
int POT_VALUE_OUT = 0;

float DAC_OUTPUT_VALUE = 0.0;
void setup() {
  Serial.begin(115200);
}

void loop() {
  POT_VALUE_IN = analogRead(ADC_In); //ADC_ın min:0 , max:4095
  Serial.print("ADC_INPUT = ");
  Serial.println(POT_VALUE_IN);
  delay(1000);

 DAC_OUTPUT_VALUE = POT_VALUE_IN * (3.3 / 4095);
  Serial.print("DAC_ANALOG_OUTPUT =");
  Serial.print(DAC_OUTPUT_VALUE); // DAC_OUTPUT_VALUE min:0, max:3.3 Vdc
  Serial.println(" Vdc");
  delay(1000);
}
