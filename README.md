# ⛰️ Meteo Alpi

**Confronto multi-modello delle previsioni meteo per l'arco alpino** — Italia · Francia · Svizzera · Austria

Un'app web a file singolo, pensata per chi va in montagna e vuole capire **quanto fidarsi** di una previsione: invece di affidarsi a una sola fonte, mette a confronto fianco a fianco fino a 9 modelli meteorologici nazionali. Se concordano, la previsione è solida; se divergono, c'è incertezza — un'informazione preziosa proprio nelle giornate dubbie.

---

## Caratteristiche

- **9 modelli meteorologici a confronto**, incluso ICON-2I (ItaliaMeteo/ARPAE), il modello ufficiale italiano ad alta risoluzione
- **Indicatore di concordanza** tra modelli, per capire a colpo d'occhio il margine di incertezza
- **Uso offline**: scarica i dati prima di partire e consultali senza segnale
- **Storico dei salvataggi**: confronta come è cambiata la previsione nel tempo (fino a 3 scatti per località)
- **Dettaglio orario e per fasce** (notte/mattina/pomeriggio/sera), con più grandezze mostrate insieme
- **Link diretti ai bollettini ufficiali** della zona (ARPA regionali, Aeronautica Militare, AINEVA, MeteoSwiss, Météo-France, GeoSphere Austria)
- **Parere AI opzionale**: un riassunto in linguaggio semplice dei dati già scaricati
- **4 temi colore** e **5 layout** (da smartphone a desktop, più una modalità minimal)
- **Backup su file** esportabile/importabile

## Installazione

Non serve installare nulla: è un **singolo file HTML**.

1. Scarica `index.html`
2. Aprilo nel browser

Per metterlo sulla schermata Home del telefono (si apre a schermo intero, come un'app):
- **Android**: apri il sito con Chrome → menu ⋮ → "Installa app"
- **iPhone/iPad**: Safari → icona condivisione → "Aggiungi alla schermata Home"

L'app è una PWA: dopo il primo caricamento può avviarsi anche senza connessione. Per aggiornare dati e previsioni serve comunque una connessione Internet.

> **Nota per Android**: alcuni browser bloccano le richieste di rete dai file aperti con `file://`. Se la ricerca non funziona, servi il file con un piccolo server locale:
> ```bash
> python -m http.server 8080
> ```
> poi apri `http://localhost:8080/index.html`

## Fonti dati

Tutti i dati meteo provengono da [Open-Meteo](https://open-meteo.com/), gratuito per uso non commerciale e **senza chiave API**. I modelli disponibili:

| Modello | Ente | Note |
|---|---|---|
| ICON-2I | ItaliaMeteo / ARPAE 🇮🇹 | Alta risoluzione (2 km), solo 3 giorni |
| ICON | DWD 🇩🇪 | Affidabile su Alpi e Italia |
| ECMWF | Centro europeo 🇪🇺 | Tra i più affidabili in assoluto |
| Météo-France | Météo-France 🇫🇷 | Preciso sul versante francese |
| GFS | NOAA 🇺🇸 | Confronto indipendente |
| GEM | Canada 🇨🇦 | Ulteriore punto di vista |
| JMA | Giappone 🇯🇵 | Controllo extra |
| ICON-D2 | DWD 🇩🇪 | Altissima risoluzione, Europa centrale |
| AROME | Météo-France 🇫🇷 | Altissima risoluzione, Francia |

## Parere AI (opzionale)

La funzione AI **non inventa previsioni**: riceve i dati già scaricati dai modelli e li riassume in linguaggio semplice. Tre modalità: commento sul giorno selezionato, andamento nelle prossime 24 ore, tendenza nei prossimi giorni.

Richiede la configurazione di un provider in *Impostazioni → AI*:
- **Groq** — gratuito, richiede una chiave (registrazione ~2 minuti, nessuna carta di credito). Consigliato.
- **LLM7.io** — senza chiave, ma servizio community senza garanzie
- Anche Google Gemini, OpenRouter, Cerebras, o endpoint personalizzato

La chiave API resta salvata **solo sul dispositivo** (localStorage del browser) e non viene mai scritta nel file HTML.

## Privacy

- Nessun dato viene inviato a server dell'autore: non esistono server dell'autore
- Preferiti, impostazioni e cache restano nel browser del dispositivo
- Le uniche chiamate di rete sono verso Open-Meteo (dati meteo) e, se configurato, verso il provider AI scelto
- Nessun tracciamento, nessun cookie di profilazione, nessuna pubblicità

## Avvertenza importante

I dati grezzi di modello **non sostituiscono i bollettini ufficiali** (ARPA, Protezione Civile, MeteoSwiss, Météo-France) né i bollettini valanghe (AINEVA, Meteomont). In montagna la divergenza tra modelli è frequente: usa questo strumento per capire il margine di incertezza, **non come previsione definitiva**. Le decisioni in ambiente alpino restano responsabilità di chi le prende.

## Documentazione

Il manuale completo, corredato di schermate e istruzioni operative, è disponibile qui: [Meteo_Alpi_Manuale.docx](Meteo_Alpi_Manuale.docx).

## Contatti

**Lorenzo Baudino**
- Email: baudinolorenzo@gmail.com
- WhatsApp: [+39 320 723 6032](https://wa.me/393207236032)

## Licenza

MIT — vedi [LICENSE](LICENSE)
