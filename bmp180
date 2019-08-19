#include <Wire.h>
#include <Adafruit_BMP085.h>

Adafruit_BMP085 bmp; // objeto da classe Adafruit_BMP085 (I2C)
   
void setup(){
  Serial.begin(9600); // inicia comunicação serial.
  bmp.begin();
  if (!bmp.begin()){ // verifica se o sensor está ligado corretamente.
  Serial.println("Sensor BMP180 não foi identificado! Verifique as conexões.");
  while(1){} // para tudo caso o sensor não está bem conectado no inicio do programa.
  }
}
   
void loop(){
    
    bmpTemperature();
     
    Serial.print("Altitude: "); //IMPRIME O TEXTO NO MONITOR SERIAL
    Serial.print(bmp.readAltitude()); //IMPRIME NO MONITOR SERIAL A ALTITUDE APROXIMADA
    Serial.println(" m (Metros)"); //IMPRIME O TEXTO NO MONITOR SERIAL
    
    Serial.print("Pressão a nível do mar (calculada): ");
    Serial.print(bmp.readSealevelPressure());
    Serial.println(" Pa (Pascal)"); 
 
    Serial.print("Altitude real baseada em 1 atm: "); //IMPRIME O TEXTO NO MONITOR SERIAL
    Serial.print(bmp.readAltitude(101325)); //IMPRIME NO MONITOR SERIAL A ALTITUDE REAL
    Serial.println(" m (Metros)"); //IMPRIME O TEXTO NO MONITOR SERIAL

    Serial.print("Altitude real baseada na pressao a nivel do mar calculada: ");
    Serial.print(bmp.readAltitude(bmp.readSealevelPressure()));
    Serial.println(" m");
     
    Serial.println("-----------------------------------"); //IMPRIME UMA LINHA NO MONITOR SERIAL
    delay(2000); // 2 segundos de espera
}

void bmpTemperature(){
  Serial.print("Temperatura: ");
  Serial.print(bmp.readTemperature());
  Serial.println(" *C");
}

void bmpPressure(){
  Serial.print("Pressão: "); //IMPRIME O TEXTO NO MONITOR SERIAL
  Serial.print(bmp.readPressure()); //realiza a leitura e exibe no monitor serial a pressao em pascal.
  Serial.println(" Pa"); //IMPRIME O TEXTO NO MONITOR SERIAL
}

//void 
