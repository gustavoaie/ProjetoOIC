# [OBJETOS INTELIGENTES CONECTADOS] 05K sem. 2018

## Turma 05K
## Projeto: "SOS"
## Integrantes do grupo:

* Gustavo Milena Abril Santos 41504763
* Vitor Malvezzi 31515411
* Vitor Hugo Tamashiro 31524362
* João Braga 3154339

## Descrição resumida do projeto
Por meio do aplicativo blynk usando conexão com a internet através do módulo ESP8266, ativamos os leds para transmitir mensagens em código morse.

## Hardware: 
mini Protoboard 400 furos
nodeMCU
ESP8266
Resistor 220 ohm
LED

## Protocolo:
TCP/IP
SPI

## Interface: 
Blynk

## Software:
Arduino IDE 1.8.7


_______________________________________
## Referencias:
https://www.youtube.com/watch?v=Q363NtYWgjA
https://www.youtube.com/watch?v=iueWEkM6cuQ&t=150s
http://www.comofazerascoisas.com.br/projeto-arduino-pisca-led.html




## CÓDIGO:

#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

// You should get Auth Token in the Blynk App.
// Go to the Project Settings (nut icon).
char auth[] = "b2566a3ba6934728adf406b34a1f33b7";

// Your WiFi credentials.
// Set password to "" for open networks.
char ssid[] = "jaozete";
char pass[] = "acesso123";


void setup()
{
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  // Debug console
  Serial.begin(9600);

  Blynk.begin(auth, ssid, pass);
  // You can also specify server:
  //Blynk.begin(auth, ssid, pass, "blynk-cloud.com", 80);
  //Blynk.begin(auth, ssid, pass, IPAddress(192,168,1,100), 8080);
}

BLYNK_WRITE(V5)
{
  int pinValue = param.asInt();
    if (pinValue == 1) {
    
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    digitalWrite(5,HIGH);
    delay(500);
    digitalWrite(5,LOW);
    delay(2000);

    
    digitalWrite(4,HIGH);
    delay(1600);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(1600);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    
    digitalWrite(5,HIGH);
    delay(500);
    digitalWrite(5,LOW);
    delay(2000);

    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    digitalWrite(5,HIGH);
    delay(500);
    digitalWrite(5,LOW);
    
    }else{
      digitalWrite(4,LOW);
      digitalWrite(5,LOW);
      }
      Serial.println(pinValue);
  }


BLYNK_WRITE(V6){
  int pinValue = param.asInt();
    while (pinValue == 1){
        digitalWrite(4,HIGH);
        delay(1000);
        digitalWrite(4,LOW);
        digitalWrite(5,HIGH);
        delay(1000);
        digitalWrite(5,LOW);
         if (pinValue == 0 ){
      digitalWrite(4,LOW);
      digitalWrite(5,LOW);
      }
      Serial.println(pinValue);
  }
      }
   

  BLYNK_WRITE(V7)
{
  int pinValue = param.asInt();
    if (pinValue == 1) {
   
    digitalWrite(4,HIGH);
    delay(1600);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(1600);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    
    digitalWrite(5,HIGH);
    delay(500);
    digitalWrite(5,LOW);
    delay(2000);

    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    delay(200);
    digitalWrite(4,HIGH);
    delay(800);
    digitalWrite(4,LOW);
    digitalWrite(5,HIGH);
    delay(500);
    digitalWrite(5,LOW);

    
    }else{
      digitalWrite(4,LOW);
      digitalWrite(5,LOW);
      }
      Serial.println(pinValue);
  }

  
void loop()
{
  Blynk.run();

    
}

`doc/` documentação do projeto
