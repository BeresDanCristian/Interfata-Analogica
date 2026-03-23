# Interfata-Analogica
# Proiectarea unei Interfețe Analogice - SCIA 

Acest proiect reprezintă implementarea și simularea unei interfețe analogice complexe, structurată pe patru etaje de procesare a semnalului. [cite_start]Proiectul a fost realizat pentru disciplina **Sisteme cu Circuite Integrate Analogice (SCIA)** la Facultatea de Electronică, Telecomunicații și Tehnologia Informației din cadrul Universității Tehnice din Cluj-Napoca.

## 📋 Tema Proiectului
[cite_start]Obiectivul principal este proiectarea unui sistem analogic capabil să preia un semnal de intrare de nivel mic și să îl proceseze prin amplificare, filtrare, ajustare programabilă a câștigului și redresare de precizie[cite: 3].

## 🏗️ Arhitectura Sistemului

Sistemul este compus din următoarele etaje corelate:

### 1. Etajul de Amplificare (Amplificator neinversor)
* [cite_start]**Rol:** Preluarea semnalului de intrare ($V_{in}$ max 147 mV) și amplificarea acestuia cu un factor liniar de 6[cite: 4, 6].
* [cite_start]**Componente cheie:** Amplificator operațional LT1679[cite: 4].
* [cite_start]**Funcționalități:** Include o rețea de compensare a tensiunii de offset (DC Offset) pentru calibrarea fină a punctului de funcționare[cite: 5, 10].
* [cite_start]**Specificații:** Câștig teoretic calculat prin $Av = 1 + R_2/R_1$; valoarea $R_2$ a fost ajustată experimental la 60k pentru a compensa pierderile[cite: 7, 8].

### 2. Etajul de Filtrare (Filtru Trece-Jos KHN)
* [cite_start]**Topologie:** Kerwin-Huelsman-Newcomb (KHN), utilizând trei amplificatoare operaționale (un sumator și două integratoare)[cite: 12, 13].
* [cite_start]**Parametri:** * Banda de frecvență: 7 kHz[cite: 14].
    * [cite_start]Factor de calitate ($Q$): 0.707[cite: 14].
    * [cite_start]Câștig în banda de trecere ($|H0|$): 1[cite: 14].
* [cite_start]**Avantaj:** Stabilitate superioară și sensibilitate scăzută la variațiile componentelor[cite: 13].

### 3. Amplificator cu Câștig Programabil (PGA)
* [cite_start]**Funcție:** Ajustarea discretă a amplificării în 4 pași[cite: 20, 21].
* [cite_start]**Implementare:** Realizat cu un comutator analogic multiplu (ADG1311) și o rețea rezistivă de precizie[cite: 20, 22].
* [cite_start]**Trepte de câștig:** 12 dB, 14 dB, 16 dB și 18 dB (rezoluție de 2 dB/pas)[cite: 21, 24].

### 4. Redresor de Precizie
* [cite_start]**Tip:** Redresor monoalternanță de precizie[cite: 27].
* [cite_start]**Tehnologie:** Utilizează diode de comutație rapidă 1N4148 montate în bucla de reacție pentru a compensa căderea de tensiune de prag (0.6V)[cite: 28, 34].
* [cite_start]**Rezultat:** Extrage informația de amplitudine (doar componenta pozitivă) cu un câștig liniar unitar[cite: 29, 30].

## 🛠️ Instrumente Utilizate
* [cite_start]**LTspice:** Pentru simulările de regim static (DCOP), analiza în frecvență (AC) și analiza în regim tranzitoriu (Transient)[cite: 6, 37, 39].
* [cite_start]**Microsoft Excel:** Pentru dimensionarea componentelor și calculul rețelelor rezistive[cite: 16, 19].

## 📊 Rezultate Obținute
* [cite_start]**Liniaritate:** Distorsiuni armonice totale (THD) sub 1% pentru toate treptele de câștig[cite: 43].
* [cite_start]**CMRR:** Aproximativ 100 dB la frecvența de 1 MHz[cite: 37].
* [cite_start]**PSRR:** Aproximativ 11.72 dB[cite: 38].

---
**Autor:** Beres Dan-Cristian  
**Grupa:** 2133/3  
**Coordonator:** prof. ing. [cite_start]Alessandro Battigelli
