# ESPHome Configuration for CYD 2.8" (Cheap Yellow Display)

Benvenuti! Questa è una configurazione completa e pronta all'uso per il **Cheap Yellow Display (CYD) da 2.8 pollici** (basato su ESP32-2432S028R) integrato con **Home Assistant** tramite **ESPHome**.

Il progetto include un'interfaccia a 3 pagine:
1. **Home:** Orologio digitale (Ore, Minuti, Secondi), data, temperatura/umidità esterna e consumo elettrico della casa in tempo reale.
2. **Plancia Luci:** Controllo per 8 interruttori/luci di casa con feedback visivo dello stato (acceso/spento) e pulsanti per il dimmer della retroilluminazione dello schermo.
3. **Orologio Analogico:** Un quadrante analogico completo di lancette per ore, minuti e secondi con timer di ritorno automatico alla Home.

---

## 📌 Mappatura dei Pin (Hardware Pinout)

Se state impazzendo a cercare i pin corretti per far funzionare lo schermo e il touch, eccoli qui:

### 🖥️ Display (ILI9341 via SPI)
* **MOSI:** GPIO13
* **MISO:** GPIO12
* **CLK:** GPIO14
* **CS:** GPIO15
* **DC:** GPIO2
* **RESET:** GPIO4
* **Backlight (Retroilluminazione PWM):** GPIO21

### 👆 Touchscreen (XPT2046 via SPI)
* **MOSI:** GPIO32
* **MISO:** GPIO39
* **CLK:** GPIO25
* **CS:** GPIO33
* **IRQUER (Interrupt):** GPIO36

---

## ⚙️ Note sulla Calibrazione del Touch
La calibrazione del touchscreen inserita nel file `.yaml` è già testata e funzionante con l'asse X e Y invertito (`swap_xy: true`) per l'orientamento orizzontale (`rotation: 90`). 

## 🚀 Come usarlo
1. Copiate il file `cyd-28-ha.yaml` nella vostra cartella di ESPHome.
2. Create o verificate il vostro file `secrets.yaml` inserendo le credenziali Wi-Fi e le chiavi API richieste.
3. **Importante:** Ricordatevi di sostituire gli `entity_id` dei sensori e delle luci con quelli reali presenti nel vostro Home Assistant!
