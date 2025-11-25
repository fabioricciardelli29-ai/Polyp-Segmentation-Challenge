# Polyp-Segmentation-Challenge
La segmentazione dei polipi nel colon rappresenta un'importante sfida nel campo dell'elaborazione di immagini 
mediche, in quanto i polipi possono costituire lesioni precancerose e richiedono un'identificazione accurata 
durante la colonscopia [1]. Questo processo è cruciale per la prevenzione e la diagnosi precoce del cancro 
colorettale, che è una delle principali cause di morte oncologica a livello globale [2]. I polipi sono escrescenze 
anomale che si sviluppano sulla mucosa del colon e del retto. Sebbene molti polipi siano benigni, alcuni 
possono evolvere in adenomi, i quali rappresentano la fase iniziale della trasformazione in tumore maligno. 
Tuttavia, la rilevazione dei polipi può risultare complessa a causa della loro variabilità in termini di dimensioni, 
forma, colore e posizione all'interno del tratto intestinale. La segmentazione automatica dei polipi attraverso 
l’uso dell’intelligenza artificiale mira a supportare i medici nella localizzazione e classificazione delle lesioni, 
riducendo il rischio di diagnosi mancate, migliorando l’efficacia degli screening e riducendo l’incidenza dei 
tumori [3]. Tuttavia, la variabilità dei dati, dovuta a differenze nei dispositivi utilizzati dai diversi centri e 
nelle condizioni dei pazienti, rappresenta un ostacolo significativo per il task di segmentazione. 
In questo contesto si colloca la Polyp Segmentation Challenge, che si pone l'obiettivo di sviluppare algoritmi 
capaci di segmentare accuratamente i polipi presenti nelle immagini di colonscopia. Una peculiarità della sfida 
è la necessità di garantire la coerenza tra frame consecutivi delle colonscopie. Per affrontare la sfida, uno degli 
approcci più utilizzati in letteratura per la segmentazione automatica è l’impiego di tecniche di Deep Learning 
basate su reti neurali convoluzionali. Tra queste, la rete U-net si distingue per la sua efficacia nella 
segmentazione semantica.





1) PER SVILUPPARE IL DATASET CON CUI ALLENARE LA RETE ESEGUIRE I CODICI CONTENUTI NELLA CARTELLA "CREAZIONE DEL DATASET CON IL PRE PROCESS".
     PER OTTENERE IL DATASET FINALE CON CUI ALLENARE LA RETE SONO STATI ESEGUITI IN CASCATA I SEGUENTI STEP:
     1) ESEGUIRE CODICE: "DIVISIONE (TRAIN, VAL, TEST) + RESIZE.ipynb"  -----> dare in input la cartella del dataset originale
     2) ESEGUIRE CODICE: "IMAGE REGIONAL MASKING + INPAINTING.ipynb"  -----> dare in input l'output dello step precedente
     3) ESEGUIRE CODICE: "DATASET NORMALIZZATO.ipynb"  ----->  dare in input l'output dello step precedente
     CON QUESTI PASSAGGI SI CONCLUDE IL PRE-PROCESSING.

2) PER ALLENARE LA RETE UTILIZZARE IL FILE "ALLENAMENTO FINALE.ipynb". ----> dare in input la cartella finale dello step precedente

3) ORGANIZZARE IL DATASET PER FARE INFERENCE ESEGUENDO IL CODICE: "INFERENCE DATASET ORGANIZE.ipynb" ----> dare in input la cartella del dataset originale

4) PER FARE INFERENCE SUL VALIDATION: ESEGUIRE CODICE "inference VALIDATION FINALE.ipynb" ---> il codice esegue inference sulle 5 migliori iterazioni e ci permette di scegliere quella migliore

5) PER FARE INFERENCE SUL TEST: ESEGUIRE CODICE "inference TEST SET FINALE.ipynb"  ----> inserire manualmente l'iterazione migliore dello step precedente, ed eseguire l'inference sul TEST

EXTRA:
- t-SNE che calcola il piano e lo visulizza sul dataset originale: VEDASI CODICE "T-SNE_CALCOLO_PIANO.ipynb"
- applicazione del piano calcolato precedentemente al dataset pre-processato: VEDASI CODICE "TSNE DATASET DEFINITIVO.ipynb"
 
