# Titolo del documento di prova

Autore: Marco Rossi

## 1 Introduzione

Questo documento serve a verificare se i riferimenti incrociati di iA Writer producono, nel PDF esportato, destinazioni interne e magari un indice dei segnalibri. Il testo è volutamente neutro e ripetitivo: conta la struttura, non il contenuto. Il metodo è descritto nella sezione [2 Metodo][], mentre i risultati si trovano più avanti.

Un secondo paragrafo completa la premessa. Chi legge il documento a schermo dovrebbe poter fare clic sui riferimenti e raggiungere la sezione indicata, senza scorrere manualmente le pagine. Per questo ogni titolo del documento è bersaglio di almeno un collegamento.

### 1.1 Scopo

Lo scopo è controllare tre cose: che i riferimenti automatici, costruiti con il testo del titolo, siano riconosciuti; che i titoli con etichetta esplicita siano raggiungibili; che l'elenco finale contenga un collegamento per ogni titolo. Si veda anche [1.2 Struttura][] per l'organizzazione del documento.

Il paragrafo seguente aggiunge del testo di riempimento. L'archivio raccoglie documenti di vario genere, ordinati per data e per argomento, e consultabili sia in sede sia a distanza. Chi lo gestisce decide con regolarità quali materiali conservare e quali scartare.

### 1.2 Struttura

Il documento si compone di cinque sezioni numerate a mano e di un indice finale dei riferimenti. Le sezioni hanno titoli di livello due e tre, così da verificare l'eventuale gerarchia dei segnalibri nel PDF.

Come primo passo si legga [1.1 Scopo][], poi si passi a [2 Metodo][]. Il testo di questo paragrafo è abbastanza lungo da occupare qualche riga, in modo che la giustificazione e la sillabazione abbiano modo di manifestarsi in modo regolare.

## 2 Metodo

Il metodo consiste nel scrivere il documento con la sintassi dei riferimenti di MultiMarkdown, esportarlo in PDF e ispezionare il file risultante con uno strumento che elenca le destinazioni nominate e i segnalibri. Il confronto con un'esportazione priva di riferimenti mostra la differenza.

Un secondo paragrafo descrive le condizioni di prova: stesso modello, stessa lingua, stessi caratteri. L'unica variabile è la presenza dei collegamenti. I dettagli sulla raccolta si trovano in [2.1 Raccolta dei dati][].

### 2.1 Raccolta dei dati

I dati sono raccolti aprendo il PDF e leggendo l'elenco delle destinazioni interne. Per ciascun titolo si annota se esiste una destinazione con un nome corrispondente e se il collegamento nel testo vi punta correttamente.

Il paragrafo seguente serve solo a occupare spazio e a spostare i titoli successivi verso il fondo della pagina, dove l'impaginazione deve evitare di lasciare un titolo isolato. Si torni alla [1 Introduzione][] per il quadro generale.

## 3 Risultati [Risultati]

I risultati, come promesso, sono qui. Questo titolo ha un'etichetta esplicita, perciò può essere raggiunto anche con la forma abbreviata: vedi [Risultati][] oppure [vai ai risultati][Risultati]. Il testo di ciascun collegamento è diverso, la destinazione è la stessa.

Un secondo paragrafo ricorda che la parte più interessante riguarda i titoli annidati, trattati in [3.1 Risultati principali][]. Se il PDF contiene destinazioni nominate, esse dovrebbero comparire in un elenco con nomi derivati dai titoli o dalle etichette.

### 3.1 Risultati principali

In questa sezione si riporterebbero i risultati principali. Poiché si tratta di un documento di prova, ci si limita a osservare che il comportamento atteso è il seguente: ogni collegamento interno diventa un salto verso la pagina in cui si trova il titolo corrispondente.

Il paragrafo successivo continua il discorso. Una buona prova richiede più pagine, perché i riferimenti all'indietro e in avanti attraversano i salti di pagina. Per questo il testo è disteso su circa tre pagine, con paragrafi di lunghezza varia.

## 4 Discussione

La discussione confronta quanto atteso con quanto osservato. Se i collegamenti sono presenti ma i segnalibri no, il lettore potrà comunque fare clic nel testo; se mancano entrambi, i riferimenti sono soltanto decorazione. Il punto di partenza è sempre [3 Risultati][Risultati].

Un altro paragrafo prosegue con osservazioni di carattere generale. L'esperienza insegna che i motori di esportazione trattano in modo diverso i collegamenti interni e quelli esterni, e che le destinazioni possono avere nomi inattesi. Per le cautele del caso si veda [4.1 Limiti][].

### 4.1 Limiti

La prova ha limiti evidenti: un solo documento, un solo modello, una sola versione del programma. I risultati non vanno generalizzati. Resta il fatto che, se funziona qui, vale la pena sperimentare su documenti più grandi.

Un ultimo paragrafo di questa sezione serve a portare il testo verso la fine della seconda pagina. Si consideri anche la [5 Conclusioni][] per le indicazioni operative, e il [2.1 Raccolta dei dati][] per le procedure di controllo.

## 5 Conclusioni

Le conclusioni sono brevi. Se i riferimenti incrociati producono destinazioni interne nel PDF, il modello può sfruttarle; in caso contrario conviene rinunciare a qualsiasi aspettativa di navigazione e considerare il PDF come un documento puramente stampabile.

Un secondo paragrafo chiude il discorso e rimanda alla [1 Introduzione][] per chi volesse ricominciare la lettura. Segue l'elenco completo dei riferimenti a ogni titolo del documento.

## Indice dei riferimenti

- [1 Introduzione][]
- [1.1 Scopo][]
- [1.2 Struttura][]
- [2 Metodo][]
- [2.1 Raccolta dei dati][]
- [3 Risultati][Risultati]
- [3.1 Risultati principali][]
- [4 Discussione][]
- [4.1 Limiti][]
- [5 Conclusioni][]
- [Indice dei riferimenti][]
