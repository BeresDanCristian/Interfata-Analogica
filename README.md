# Interfata-Analogica
# Proiectarea unei Interfețe Analogice - SCIA 

Acest proiect reprezintă implementarea și simularea unei interfețe analogice complexe, structurată pe patru etaje de procesare a semnalului, realizat pentru disciplina **Sisteme cu Circuite Integrate Analogice**.

## 🏗️ Arhitectura Sistemului

Sistemul este compus din următoarele etaje corelate:

### 1. Amplificator de Intrare (Etajul 1)
- **Tip:** Amplificator neinversor.
- **Parametri:** Câștig liniar constant de **6**.
- **Sursă semnal:** Amplitudine minimă 0.0734V / Amplitudine maximă 0.147V.
- **Funcție:** Preluarea semnalului mic și aducerea lui la un nivel optim pentru filtrare.

### 2. Filtru Activ (Etajul 2)
- **Topologie:** Filtru Trece-Jos (LPF).
- **Specificații:**
  - Câștig în banda de trecere ($H_0$): 1.
  - Frecvența de tăiere (Banda): 7000 Hz.
  - Factor de calitate ($Q$): 0.707.
  - Rezistență de intrare minimă: 750 Ω.

### 3. Amplificator cu Câștig Programabil - PGA (Etajul 3)
- **Funcție:** Ajustarea nivelului semnalului în trepte discrete.
- **Trepte de câștig:**
  - Pas 1 (Maxim): 18 dB (8 liniar).
  - Pas 2: 16 dB (6.3 liniar).
  - Pas 3: 14 dB (5 liniar).
  - Pas 4 (Minim): 12 dB (4 liniar).
- **Implementare:** Control prin comutatoare analogice (U5, U6, U7).

### 4. Detector de Vârf / Redresor (Etajul 4)
- **Tip:** Redresor de precizie monoalternanță.
- **Rol:** Extragerea anvelopei semnalului procesat pentru monitorizare sau conversie ulterioară.

## 📊 Performanțe și Simulări
- **Analiza Transient:** Verificarea liniarității (THD < 1%) pentru extremele de câștig și intrare.
- **Analiza AC:** Confirmarea benzii de trecere a filtrului și a pașilor de câștig ai PGA-ului.
- **Componente utilizate:** LT1679 (Op-Amp), ADG1311 (Analog Switch), 1N4148 (Diode).

---
**Autor:** Beres Dan-Cristian
**Grupa:** 2133/3
**Coordonator:** prof. ing. Alessandro Battigelli
**Instituție:** Universitatea Tehnică din Cluj-Napoca (ETTI)
