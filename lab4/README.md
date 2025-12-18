# Information Security - Lab 4: Secret Key Agreement over Wiretap Channels

Questo repository contiene il lavoro svolto per il quarto e ultimo laboratorio del corso di **Information Security** presso l'**Università degli Studi di Padova** (A.A. 2024/2025). Il progetto esplora la generazione di chiavi segrete tra due parti (Alice e Bob) sfruttando la rumorosità intrinseca dei canali di comunicazione e l'ausilio di discussioni pubbliche.

## 👥 Gruppo: CyberDucks
* **Andrea Andreozzi** 
* **Riccardo Scalco** 
* **Sergio Cibecchini** 
* **Luca Ferrari** 

## 🎯 Obiettivi del Laboratorio
L'obiettivo principale è l'implementazione di un protocollo di **Secret Key Agreement**. Alice, Bob ed Eve ricevono segnali correlati da una sorgente o tramite un canale wiretap; il sistema deve permettere ad Alice e Bob di concordare una chiave identica che risulti, allo stesso tempo, segreta rispetto all'intercettatore Eve.

## 🛠️ Task e Implementazione

### 1. Implementazione del Canale Wiretap (Task 1)
Simulazione di un canale wiretap dove gli alfabeti di input e output sono composti da parole a 7 bit $\{0,1\}^7$.
* **Modello di Errore**: Ogni canale introduce al massimo un bit-flip per ogni parola trasmessa.
* **Operazione**: L'errore viene applicato tramite la funzione `apply_error` utilizzando l'operazione bitwise XOR ($x \oplus e$).
* **Validazione**: Verifica della distribuzione uniforme e dell'indipendenza dei canali tramite $10^4$ trasmissioni.

### 2. Protocollo di Accordo della Chiave
Alice trasmette una sequenza $x$, Bob riceve $y$ ed Eve riceve $z$.
* Viene utilizzato un canale di discussione pubblica $C$ per scambiare informazioni che aiutino Alice e Bob a sincronizzare le proprie chiavi ($k_A$ e $k_B$).
* Il protocollo è testato per diverse lunghezze di chiave e livelli di rumore nel canale.

### 3. Valutazione delle Metriche di Sicurezza
Il sistema viene analizzato secondo quattro parametri fondamentali:
* **Correctness**: Valuta la probabilità che le chiavi $k_A$ e $k_B$ non coincidano.
* **Uniformity**: Calcolo dell'entropia $H(k_A)$ per verificare che la chiave sia distribuita uniformemente e non sia prevedibile.
* **Secrecy**: Misurata tramite la Mutua Informazione $I(k; Z, C)$, che quantifica quanta informazione sulla chiave trapela ad Eve attraverso il canale wiretap e la discussione pubblica.
* **Total Variation Distance**: Analisi della distanza tra la distribuzione empirica ottenuta e quella ideale.

## 📈 Risultati e Conclusioni
* **Affidabilità**: La correttezza diminuisce all'aumentare del rumore ($\epsilon$), ma il disallineamento tra le chiavi rimane entro limiti accettabili (sotto il 27% nei casi peggiori).
* **Segretezza**: È stato dimostrato che la segretezza migliora con l'aumentare del rumore nel canale di Eve e che chiavi più corte presentano generalmente una perdita di informazione inferiore.
* **Uniformità**: I risultati sperimentali mostrano un'uniformità quasi perfetta, con valori di entropia estremamente vicini al massimo teorico.

## 💻 Tecnologie Utilizzate
* **Linguaggio**: Python
* **Librerie**: `NumPy` per calcoli matriciali, `Matplotlib` per i grafici delle metriche e `collections.Counter` per l'analisi delle frequenze
* **Ambiente**: Google Colab / Jupyter Notebook

## 📂 Struttura dei File
* `code_cyberducks.ipynb`: Notebook con l'implementazione del protocollo e i test statistici.
* `report_cyberducks.pdf`: Relazione finale con grafici dettagliati, analisi delle performance e conclusioni teoriche.
