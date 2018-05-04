# Ultrasound-Motion-Sensor.arduino
This code is for an Ultrasound Motion Sensor device which alerts when and if there's any motion is detected in front of the sensor. watch https://www.youtube.com/watch?v=RlCRH8zNRC8&t=5s

    int trigger_pin = 2;  
    int echo_pin = 3;
    int buzzer_pin = 10;
    int time;
    int distance;
    void setup ( ) {
        Serial.begin (9600);
        pinMode (trigger_pin, OUTPUT);
        pinMode (echo_pin, INPUT);
        pinMode (buzzer_pin, OUTPUT);
                    }
    void loop ( ) {
        digitalWrite (trigger_pin, HIGH);
        delayMicroseconds (10);
        digitalWrite (trigger_pin, LOW);
        time = pulseIn (echo_pin, HIGH);
        distance = (time * 0.035) / 2;
    if (distance <= 10)
        {
        Serial.println (" Door Open ");
        Serial.print (" Distance= ");
        Serial.println (distance);
        digitalWrite (buzzer_pin, HIGH);
        delay (500);
        }
    else {
        Serial.println (" Door closed ");
        Serial.print (" Distance= ");
        Serial.println (distance);
        digitalWrite (buzzer_pin, LOW);
        delay (500);
        }
        }﻿
