# stm32-sistem-securitate-locuinta
Sistem de securitate și control acces cu STM32 și Wokwi realizat în echipă

 Prezentare Generală
Acest sistem simulează o alarmă de locuință completă, incluzând control acces pe bază de PIN, senzori digitali de prezență, avertizare sonoră/vizuală și o arhitectură bazată pe o mașină de stări (FSM). Proiectul a fost conceput modular, sarcinile fiind împărțite echilibrat între membrii echipei.

# Stack Tehnic & Hardware Simulat
* **Microcontroler:** STM32F103C6 (ARM Cortex-M3)
* **Interfață de Control:** Tastatură matricială 4x4
* **Afișaj:** LCD 16x2 cu modul I2C
* **Securitate & Detecție:** Butoane digitale pentru senzori PIR și contacte magnetice (uși/geamuri)
* **Alerte:** Buzzer activ și LED-uri de status (RGB)

## Structura Echipei și Responsabilități
 Modul | Responsabil | Descriere Sarcină 
 **1. Input (Keypad)**       | Botezatu Daria-Maria | Citirea tastaturii matriciale 4x4, validarea buffer-ului de tastare și logica de introducere a PIN-ului. 
 **2. Senzori (Securitate)** | Biro Irina | Configurarea pinilor pentru senzorii de mișcare și contacte de uși/geamuri, gestionarea stărilor de detecție. 
 **3. UI & Audio (Feedback)**| Bahrim Miruna-Alexandra | Gestionarea mesajelor pe ecranul LCD I2C și controlul frecvențelor/tonurilor emise de buzzer. 
 **4. Core Logic (FSM)**     | Crismaru Emilia-Elena | Implementarea mașinii de stări (Finite State Machine), integrarea modulelor și gestionarea timpilor de armare/alarmă. 

## Logica Sistemului (Finite State Machine)
Sistemul funcționează pe baza a 3 stări principale:
1. **DISARMED (Dezarmat):**      Sistemul este inactiv; senzorii sunt ignorați. Se așteaptă introducerea PIN-ului corect de pe tastatură pentru armare.
2. **ARMED (Armat):**            Sistemul monitorizează activ senzorii. Orice activare declanșează imediat starea de alarmă.
3. **ALARM_TRIGGERED (Alarmă):** Sirena (buzzerul) pornește intermitent, LED-ul roșu clipește, iar accesul este restricționat până la introducerea PIN-ului de dezarmare.

## Link-uri Utile
* [Simulare Wokwi *(Adaugă link-ul aici)*]

