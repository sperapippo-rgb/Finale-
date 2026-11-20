# Football Analyst 3.1 — ZIP completo

## Contenuto
- `index.html`: interfaccia PWA.
- `styles.css`: grafica responsive Android/desktop.
- `app.js`: ricerca automatica OpenFootball, elenco partite, filtro squadra, statistiche HT, split casa/trasferta.
- `manifest.webmanifest`: installazione PWA.
- `sw.js`: service worker con cache versionata e aggiornamento controllato.
- `icon.svg`: icona app.
- `README.md`: istruzioni.
- `LICENSE.txt`: note licenza.

## Pubblicazione da telefono
1. Crea un repository GitHub nuovo, pubblico, ad esempio `football-analyst-final`.
2. Estrai questo ZIP sul telefono.
3. Nel repository seleziona **Add file → Upload files**.
4. Carica tutti gli 8 file nella root (non caricare la cartella contenitore come singolo file).
5. Premi **Commit changes**.
6. Apri **Settings → Pages**.
7. In **Build and deployment** seleziona **Deploy from a branch**, branch `main`, cartella `/ (root)`, poi **Save**.
8. Attendi il link pubblicato da GitHub Pages.

## Fonte dati e compatibilità
Fonte automatica: https://github.com/openfootball/football.json (archivi JSON pubblici, licenza CC0). Gli indirizzi sono nel formato `https://raw.githubusercontent.com/openfootball/football.json/master/SEASON/CODE.json`. Alcuni percorsi stagione/campionato sono stati controllati; gli archivi possono cambiare o mancare. L'app mostra gli errori senza generare dati fittizi.

Il formato dei risultati è gestito sia quando `score` è un array (risultato finale) sia quando è un oggetto con `ft` e `ht`. Le statistiche HT vengono calcolate soltanto quando il dato HT e il risultato FT sono presenti. Un risultato finale senza HT non entra nel campione del primo tempo.

## Protocollo 3.1: stato reale
Implementato in questa build: mercati A e B separati; campioni ultime 5/10 partite disponibili; split casa/trasferta; frequenze storiche gol HT e vantaggio HT; gol HT fatti/subiti; campioni espliciti; nessuna influenza quote; nessuna selezione automatica; N.D. dove mancano dati; distinzione tra frequenze storiche e probabilità predette.

Non implementato e quindi N.D.: probabilità predittive validate, quattro indicatori 0–15, indice pressione 0–15', minuti dei gol, xG/tiri/attacchi, assenze, probabili formazioni, motivazioni/classifica dettagliata, integrazione FootyStats. Non si dichiara che questa build soddisfi integralmente ogni punto del protocollo.

Copertura femminile: non è inclusa in modo verificato nella fonte configurata. Non vengono mescolati dati maschili e femminili. La ricerca multi-campionato cerca soltanto i codici elencati nell'app.

## Limiti
Non è un servizio live, non garantisce tutte le leghe mondiali, non è un consiglio finanziario o di scommessa. Dati gratuiti dipendono dalla disponibilità e qualità della fonte pubblica. Nessuna API key, abbonamento o servizio a pagamento richiesto.
