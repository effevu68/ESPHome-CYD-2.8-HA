# ESPHome Configuration for CYD 2.8" (Cheap Yellow Display)

Benvenuti! Questa è una configurazione completa e pronta all'uso per il **Cheap Yellow Display (CYD) da 2.8 pollici** (basato su ESP32-2432S028R) integrato con **Home Assistant** tramite **ESPHome**.

---

## 📸 Anteprima del Progetto (Screenshots)

Ecco come si presenta l'interfaccia divisa sulle 3 schermate:

| 🏠 1. Schermata Home | 💡 2. Plancia Luci | 🕒 3. Orologio Analogico |
| :---: | :---: | :---: |
| <img src="CYD 1.jpg" width="250"> | <img src="CYD 2.jpg" width="250"> | <img src="CYD 3.jpg" width="250"> |

---

## 🚀 Funzionalità incluse
1. **Home:** Orologio digitale (Ore, Minuti, Secondi), data corrente, temperatura/umidità esterna e consumo elettrico della casa in tempo reale preso da Home Assistant.
2. **Plancia Luci:** Controllo interattivo per 8 interruttori/luci di casa con feedback visivo dello stato (giallo se acceso, grigio/azzurro se spento) e pulsanti rapidi `+` e `-` negli angoli bassi della Home per il dimmer della retroilluminazione dello schermo.
3. **Orologio Analogico:** Un quadrante analogico completo disegnato via codice matematico (linee e cerchi) con lancette dinamiche per ore, minuti e secondi, e un timer di ritorno automatico alla schermata principale per non usurare lo schermo.

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
