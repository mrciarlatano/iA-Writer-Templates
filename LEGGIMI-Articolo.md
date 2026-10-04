# Articolo: modello iA Writer per articoli in stile arXiv

`Articolo.iatemplate` è un modello di esportazione PDF per iA Writer, pensato
per articoli scientifici in italiano. Insieme al modello, la cartella
`strumenti/` contiene `pdfbookmarks`, che aggiunge i segnalibri al PDF
esportato, e due azioni Automator che lo richiamano.

## Caratteristiche

- Formato A4, margini di 3,6 cm, interlinea 1,7.
- Font: Source Serif 4 per il testo, Source Code Pro per codice e URL.
  **I due font vanno installati** nel sistema, altrimenti iA Writer ripiega su
  Georgia e Menlo.
- Corpi: testo 10 pt, citazioni a capo 9 pt, note 8 pt. Titoli: h1 13 pt,
  h2 12 pt, h3 11 pt.
- Numero di pagina in basso. L'intestazione (`header.html`) è vuota, pronta
  per sviluppi futuri.

## Installazione del modello

1. Doppio clic su `Articolo.iatemplate`, oppure aggiungerlo da
   Impostazioni → Modelli in iA Writer.
2. Per aggiornare: eliminare il modello e reinstallarlo. La versione
   installata si vede nel Finder con «Mostra nel Finder».

## Campi facoltativi

- **Autore**: una riga `Autore:` (o `Autori:`) subito dopo il titolo, centrata
  sotto il titolo.
- **Abstract**: un titolo `## Abstract` con il testo sotto, oppure un
  paragrafo che inizia con `Abstract:`.

Esempio completo in `esempi/prova-template.md`.

## Sillabazione e impaginazione

Il motore di esportazione di iA Writer ignora `hyphens:auto`, `break-after`
e simili, quindi se ne occupa lo script in `document.html`:

- **Sillabazione italiana**: lo script inserisce trattini soft nelle parole,
  con regole di almeno 2 lettere prima e 3 dopo l'interruzione.
- **Titoli**: nessun titolo resta isolato in fondo alla pagina; dopo un titolo
  ci sono almeno 3 righe di testo.
- **Tabelle e citazioni** non vengono spezzate tra due pagine.
- **Caption**: `Fig. 1.` per le figure e `Tab. 1.` per le tabelle, numerate in
  automatico. La didascalia MultiMarkdown di una tabella deve stare sulla riga
  subito sotto la tabella.
- **Note**: compaiono a fondo documento, non a fondo pagina. È un limite del
  motore di esportazione.

## Documenti di prova

In `esempi/`: `prova-semplice.md`, `prova-abstract-campo.md`,
`prova-impaginazione.md`, `prova-riferimenti.md`, `prova-template.md`. I PDF
esportati sono ignorati da git (`*.pdf`).

## Esportare il PDF

In iA Writer: **File → Esporta → PDF**, scegliendo il modello `Articolo`.
I segnalibri non vengono creati da iA Writer: si aggiungono dopo, con
`pdfbookmarks`.

## Lo strumento `pdfbookmarks`

Aggiunge segnalibri gerarchici (outline) a un PDF che ne è privo. I titoli
vengono dal sorgente Markdown o, in mancanza, dalle dimensioni dei caratteri.
Il contenuto visibile non cambia; un indice già presente viene sostituito.

```
pdfbookmarks [-h] [-m FILE.md] [-o OUT.pdf] [-n] [-v] pdf
```

- `-m FILE.md`: sorgente Markdown (predefinito: il `.md` omonimo accanto al PDF).
- `-o OUT.pdf`: scrive su un nuovo file lasciando intatto l'originale
  (predefinito: modifica sul posto).
- `-n`: mostra l'indice senza scrivere. `-v`: dettagli e avvisi.

Installazione:

```
cp strumenti/pdfbookmarks /usr/local/bin/
chmod +x /usr/local/bin/pdfbookmarks
cp strumenti/pdfbookmarks.1 /usr/local/share/man/man1/
pip3 install pymupdf
```

Lo script usa il Python 3.13 di python.org
(`/Library/Frameworks/Python.framework/Versions/3.13/bin/python3`): PyMuPDF va
installato per quell'interprete. Si usano percorsi assoluti.

## Azioni Automator

In `strumenti/automator/`:

- `Aggiungi segnalibri PDF.workflow`: Azione rapida (Quick Action). Copiarla in
  `~/Library/Services`.
- `PDF Services/Aggiungi segnalibri.workflow`: voce per il menu PDF della
  finestra di stampa. Copiarla in `~/Library/PDF Services`.
- `Aggiungi segnalibri al PDF aperto.workflow`: Azione rapida per Anteprima,
  da copiare in `~/Library/Services`. Compare in Anteprima ▸ Servizi e agisce
  sul PDF aperto: lo chiude e lo riapre, quindi non serve salvare. Se il
  documento ha modifiche non salvate si ferma con un avviso. Alla prima
  esecuzione chiede il permesso di Automazione per controllare Anteprima.
  Si può assegnare una scorciatoia in Impostazioni ▸ Tastiera ▸ Scorciatoie ▸
  Servizi.

I tre elementi sono stati verificati dall'utente dal Finder, dal menu PDF della
finestra di stampa e da Anteprima.

Dopo aver installato un'Azione rapida può servire uscire e rientrare dalla
sessione, oppure eseguire `/System/Library/CoreServices/pbs -update`.

## Limiti noti

- Il motore di esportazione ignora `break-after`, `hyphens:auto` e altre
  proprietà di impaginazione: da qui lo script in `document.html`.
- Il motore riduce il documento a scala 0,8 nel PDF A4; il CSS lo compensa
  (variabile `--k` = 0,9375), così nel PDF le misure coincidono con il progetto.
- Le note stanno a fondo documento, non a fondo pagina.
- In rari casi un titolo può ancora finire in fondo a una pagina con il suo
  testo nella pagina successiva (il motore ignora le regole `break-after`, perciò
  lo script del modello simula l'impaginazione). Se succede, si corregge a mano:
  aggiungere una riga o modificare il testo prima del titolo ed esportare di nuovo.
