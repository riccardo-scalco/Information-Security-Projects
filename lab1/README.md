# Information Security - Lab 1: Simplified AES-like Ciphers & Cryptanalysis

Questo repository contiene l'implementazione e l'analisi crittografica condotte durante il primo laboratorio del corso di **Information Security** presso l'**Università degli Studi di Padova** (A.A. 2024/2025).

## 👥 Gruppo: CyberDucks
* **Andrea Andreozzi**
* **Riccardo Scalco** 
* **Sergio Cibecchini** 
* **Luca Ferrari** 

## 🎯 Obiettivi del Laboratorio
L'obiettivo del laboratorio è lo sviluppo di un cifrario iterato semplificato basato sulla struttura **Substitution-Transposition-Linear (S-T-L)**, tipica dell'AES, e l'esplorazione delle sue vulnerabilità attraverso diverse metodologie di attacco.

## 🛠️ Task e Implementazione

### 1. Fondamenta del Cifrario (Task 1 & 2)
Implementazione delle componenti essenziali per la cifratura e la decifratura:
* **Key Schedule**: Generazione di 6 sottochiavi a partire da una chiave master.
* **Round Functions**: Somma delle sottochiavi in modulo $p=11$, sostituzione degli elementi, trasposizione simmetrica e trasformazione lineare tramite moltiplicazione matriciale.

### 2. Analisi della Linearità (Task 3 & 4)
* **Identificazione Vulnerabilità**: Dimostrazione matematica della natura lineare del sistema. Calcolo delle matrici di trasformazione $A$ e $B$ tali che l'operazione sia esprimibile come $x = Ak + Bu \pmod{p}$.
* **Recupero della Chiave**: Utilizzo di un attacco a testo in chiaro noto (Known Plaintext Attack) per invertire la trasformazione e isolare la chiave segreta $k$.

### 3. Cifrario Quasi-Lineare (Task 5 & 6)
* **Obfuscation**: Introduzione di una tabella di sostituzione specifica per rompere la linearità diretta.
* **Hybrid Attack**: Calcolo di una chiave approssimata tramite analisi lineare, seguita da un ciclo di **brute force** mirato (basato sulla distanza dalla chiave approssimata) per trovare l'esatta chiave segreta in tempi ridotti (circa 15-20 minuti contro le oltre 6 ore necessarie per un attacco esaustivo).

### 4. Sistemi Non Lineari e Ottimizzazioni (Task 7 & 8)
* **Inverso Modulare**: Implementazione di un sistema di sostituzione non lineare basato sull'inverso degli elementi nel gruppo ciclico $\mathbb{Z}_{11}$.
* **Meet-in-the-Middle Attack**: Implementazione di un attacco per sistemi a doppia cifratura. Utilizzando dizionari di "guesses" intermedi, la complessità dell'attacco viene ridotta drasticamente, permettendo il recupero di chiavi multiple in tempi brevissimi.

## 💻 Tecnologie e Strumenti
* **Linguaggio**: Python
* **Librerie Core**: `NumPy` per la gestione efficiente di matrici e calcoli modulari.
* **Piattaforma**: Google Colab / Jupyter Notebook.

## 📂 Organizzazione del Progetto
* `LAB_1_CyberDucks.ipynb`: Codice sorgente documentato con test di validazione per ogni task.
* `report_CyberDucks.pdf`: Relazione tecnica con analisi matematica dei risultati.
* `KPApairsH_*.txt`: File di input contenenti le coppie plaintext-ciphertext per le simulazioni di attacco.
