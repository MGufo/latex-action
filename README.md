# Documentazione privata PentaSoft

## Struttura della documentazione

[Prendo come riferimento il documento **PROVA**]

### Cartella documento prova

- **radice**: src
- **cartella prova**: contiene il file principale del documento _prova.tex_ e i vari componenti
  - **cartella contenuto**: contiene due file:
    - _contenuti.tex_: contiene le **sezioni** del documento
    - _changelog.tex_: contiene il **registro delle modifiche**
  - **cartella immagini**: contiene le immagini **specifiche** per il documento
  - **cartella sezioni**: contiene i file delle varie sezioni che compongono il documento
  - _prova.tex_: file principale che collega la prima pagina e i vari componenti

### Directory prova

```[directory path]
src
|
└─── prova
    |   prova.tex
    |
    └─── contenuto
    |   |   changelog.tex
    |   |   contenuto.tex
    |   
    └─── immagini
    │   │   ...
    │
    └─── sezioni
        |   sezione.tex
        |   ...
 
```

### Cartella template

- **radice**: src
- **cartella template**: contiene le immagini e i file **comuni** tra i vari documenti
  - **cartella images**: contiene le varie immagini
  - **cartella source**:
    - _commands.tex_: contiene i comandi ridefiniti
    - _firstpage.tex_: definisce la prima pagina dei documenti
    - _packages.tex_: contiene i package installati
    - _styles.tex_: imposta lo stile delle pagine in particolare l'header e il footer

### Directory template

```[directory path]
src
|
└─── template
    |
    └─── images
    |   |   logo-pentasoft.png
    |   |   logo-unipd.png
    |   |   ...
    |
    └─── source
        |   commands.tex
        |   firstpage.tex
        |   packages.tex
        |   styles.tex
```

## Struttura del documento

_prova.tex_:

Import.

```[LaTeX]
\input{../template/source/packages}
\input{../template/source/commands}
\input{../template/source/styles}
```

Ridefinizione delle caratteristiche principali del documento visualizzate nella prima pagina.

```[LaTeX]
\renewcommand{\documentName}{Prova}
\renewcommand{\documentVersion}{...}

\renewcommand{\documentApprovers}{...}
\renewcommand{\documentEditors}{..}
\renewcommand{\documentVerifiers}{...}

\renewcommand{\documentUsage}{...}
\renewcommand{\documentAddressee}{...}
\renewcommand{\documentSummary}{...}
```

Contenuto della prima pagina _firstpage.tex_.

```[LaTeX]
\pagenumbering{gobble}
\pagestyle{empty}
\input{../template/source/firstpage}
\pagebreak
```

Contenuto del registro delle modifiche e delle pagine di indicizzazione _changelog.tex_.

```[LaTeX]
\input{contenuto/changelog} \pagebreak
\tableofcontents \pagebreak
```

Inserimento dei file di contenuto del documento _contenuto.tex_.

```[LaTeX]
\pagestyle{styleDocPages}
\input{contenuto/contenuto}
```

## Creazione nuovo documento

Per creare una nuova documentazione basta prendere come riferimento la cartella prova e copiarla. Per facilitare la ricerca la cartella deve avere lo stesso nome del documento principale.

Le modifiche da apportare sono le seguenti:

1. _\*file principale\*_, ridefinire le caratteristiche del documento
2. _changelog_, definire il valore della tabella delle modifiche
3. Ogni nuova sezione del documento deve avere il proprio file _sezione_ che va incluso nel file _contenuto_

Della documentazione per LaTex può essere trovata [qui](https://www.overleaf.com/learn) (Overleaf).

La documentazione di riferimento la trovate [qui](
https://github.com/Yakuzaishi-SWE/docs/tree/master/src) (Github).
