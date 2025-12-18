# Bioinformatics Project
Analizzatore di k-mer per Sequenze FASTQ
Panoramica
Questo strumento analizza file FASTQ contenenti reads di sequenziamento di uguale lunghezza, studiando la distribuzione posizionale di k-mer (sottostringhe di lunghezza k) all'interno dei reads. Il programma identifica pattern ricorrenti e produce diverse forme di output per l'analisi dei dati.

Funzionalità Principali
1. Analisi Posizionale dei k-mer
Il programma esamina ciascuna possibile posizione nei reads e conta quante volte ogni k-mer appare in quella specifica posizione. Questo permette di identificare se certi pattern tendono a comparire in posizioni specifiche.

2. Filtraggio per Frequenza
Viene applicata una soglia di frequenza F (compresa tra 0 e 1). Solo i k-mer che appaiono con frequenza almeno F nell'intero dataset vengono considerati nel report finale.

3. Report Testuale
Genera un file di testo strutturato che mostra, per ogni k-mer significativo:

- Il k-mer stesso (es: "ATGCTA")

- La frequenza totale

- La distribuzione dettagliata per ogni posizione

- Il numero di occorrenze in ciascuna posizione possibile

4. Identificazione del k-mer Dominante
Tra tutti i k-mer che superano la soglia, il programma identifica quello che appare più frequentemente in una singola posizione, evidenziando così il pattern più "fortemente posizionato".

5. Visualizzazione Grafica
Crea un diagramma a barre che mostra l'andamento del k-mer dominante attraverso tutte le posizioni. Il grafico evidenzia chiaramente:

- La posizione di picco (massima frequenza)

- L'andamento generale attraverso le diverse posizioni

- La distribuzione spaziale del pattern

6. Estrazione Mirata di Reads
Seleziona tutti i reads che contengono il k-mer dominante esattamente nella posizione dove esso occorre più frequentemente. Questi reads vengono salvati in un file FASTA con informazioni aggiuntive.

7. Calcolo della Qualità Media
Per ogni read estratto, calcola la qualità media delle sue basi convertendo i valori Phred (presenti nel file FASTQ) in punteggi numerici, fornendo così un'indicazione dell'affidabilità del sequenziamento per quel read specifico.

Formato degli Output
Report Testuale
Il file di report organizza i dati in modo tabellare, facilitando l'analisi comparativa tra diversi k-mer e le loro distribuzioni posizionali.

Diagramma
Il grafico prodotto è un istogramma che visualizza intuitivamente come la presenza del k-mer dominante vari attraverso le diverse posizioni del read, permettendo di identificare pattern di localizzazione.

File FASTA
I reads selezionati vengono salvati in formato FASTA standard, ma con header arricchiti che includono:

- L'identificatore originale del read

- La qualità media calcolata
Questa formattazione permette un'ulteriore analisi con altri strumenti bioinformatici.

Applicazioni Tipiche
Questo strumento è utile per:

- Identificare adapter o contaminazioni in posizioni specifiche

- Studiare bias di sequenziamento

- Analizzare pattern ricorrenti in esperimenti di ChIP-seq o CLIP-seq

- Controllare la qualità di librerie di sequenziamento

- Identificare motivi sequenza-specifici

## ** Punti di Forza **

- Analisi posizionale precisa: Non solo conta i k-mer, ma ne studia la distribuzione spaziale

- Soglia regolabile: Permette di filtrare il rumore di fondo

- Output multipli: Fornisce sia dati grezzi che visualizzazioni

- Integrità dei dati: Mantiene le informazioni di qualità originali

- Formati standard: Usa formati largamente supportati (FASTQ, FASTA, PNG)
