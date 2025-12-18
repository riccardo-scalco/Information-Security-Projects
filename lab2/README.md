# Information Security - Lab 2: Wiretap Channel, Random Binning & Security Analysis

Questo repository contiene il lavoro svolto per il secondo laboratorio del corso di **Information Security** presso l'**Università degli Studi di Padova** (A.A. 2024/2025). Il progetto si focalizza sulla simulazione di canali di comunicazione sicuri e sull'implementazione di tecniche di codifica per garantire la segretezza.

## 👥 Gruppo: CyberDucks
* **Andrea Andreozzi** 
* **Riccardo Scalco** 
* **Sergio Cibecchini** 
* **Luca Ferrari**

## 🎯 Obiettivi del Laboratorio
L'obiettivo principale è stato lo studio e la simulazione di un **Wiretap Channel** (canale con intercettatore), implementando schemi di codifica basati su **Random Binning** per proteggere il messaggio trasmesso dall'ascolto di un utente malintenzionato (Eve), garantendo al contempo l'affidabilità per l'utente legittimo (Bob).

## 🛠️ Task e Implementazione

### 1. Simulazione del Wiretap Channel (Task 1)
Implementazione di un canale che accetta parole a 7 bit. Il sistema è stato configurato per simulare diverse condizioni di errore:
* **Canale Legittimo**: Introduce al massimo 1 errore binario.
* **Canale Eavesdropper**: Introduce fino a 3 errori binari.
* Verifica empirica dell'uniformità e dell'indipendenza degli output tramite simulazioni su larga scala ($10^4$ trasmissioni).

### 2. Random Binning Encoder & Decoder (Task 2 & 3)
Sviluppo di un sistema di codifica e decodifica per messaggi a 3 bit utilizzando codici di Hamming:
* **Encoder**: Implementazione di un meccanismo di Random Binning che associa ogni messaggio a diverse possibili parole di codice (codeword) in modo stocastico, aumentando l'incertezza per l'intercettatore.
* **Decoder**: Sviluppo di un decodificatore a minima distanza in grado di ricostruire il messaggio originale e correggere singoli errori introdotti dal canale.

### 3. Verifica della Segretezza Perfetta (Task 4)
Analisi statistica per dimostrare l'indipendenza tra il messaggio segreto $u$ e l'output ricevuto dall'intercettatore $z$:
* Calcolo empirico della **Mutua Informazione** $\hat{I}(u,z)$, risultata prossima allo zero ($\approx 0.0008$).
* Analisi della velocità di trasmissione: il sistema trasmette 3 bit segreti per uso del canale ($\approx 0.43$ bit segreti per bit trasmesso).

### 4. Analisi delle Performance e Canale AWGN (Task 7 & 8)
Valutazione del sistema in presenza di rumore bianco gaussiano additivo (AWGN):
* **BER vs SNR**: Studio del Bit Error Rate al variare del rapporto segnale-rumore (SNR) per l'intera catena di trasmissione (Encoder + Modulazione PAM + AWGN + Decoder).
* **Security Evaluation**: Analisi comparativa della sicurezza tra Bob ed Eve. Sono stati valutati parametri quali Mutua Informazione, Distanza di Variazione Totale e Capacità del canale in scenari con SNR variabile.

## 💻 Tecnologie Utilizzate
* **Linguaggio**: Python
* **Librerie**: 
  * `NumPy` per calcoli vettoriali e operazioni bitwise.
  * `Matplotlib` e `Seaborn` per l'analisi grafica delle distribuzioni e delle performance (BER/SNR).
  * `Itertools` e `Collections` per la generazione di pattern di errore e gestione distribuzioni.
* **Ambiente**: Google Colab / Jupyter Notebook.

## 📂 Struttura dei File
* `code_CyberDucks.ipynb`: Notebook interattivo contenente l'intera pipeline di simulazione, dalla generazione degli errori alla valutazione della sicurezza.
* `report_CyberDucks.pdf`: Documentazione tecnica completa con le derivazioni matematiche, i grafici delle distribuzioni e l'analisi dei risultati ottenuti.
