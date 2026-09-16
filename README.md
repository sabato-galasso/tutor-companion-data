# Tutor Companion — data catalog

Cataloghi JSON pubblici da usare per aggiornare offline Tutor Companion. Questo repository contiene soltanto dati e metadati: non include codice dell’app, chiavi, configurazioni o dati degli utenti.

## File pubblicati

- `manifest.json`: versione del catalogo, fonti, numero di record e hash SHA-256;
- `data/speed-cameras.json`: autovelox fissi geolocalizzati;
- `data/tutor-sections-osm.json`: tratti a velocità media geolocalizzati;
- `data/tutor-sections-aspi.json`: tratte Tutor pubblicate da Autostrade per l’Italia, con fonte, stato, date di riesame e classificazione delle 26 tratte Tutor 3.0 del lotto ASPI 2025. Le PK di ingresso e uscita sono progressive autostradali, non lunghezze; una eventuale `officialLength` viene valorizzata solo quando la fonte dichiara esplicitamente la lunghezza della singola tratta. In mancanza, l'admin mostra separatamente il calcolo derivato dalle due PK. Le eventuali `mapGeometry` sono ricostruzioni OSM dichiaratamente indicative e sono riservate al pannello admin: non sono coordinate certificate dei portali né dati per avvisi GPS;
- `data/mit-velox-devices.json`: registro dei dispositivi MIT, che non implica una posizione geografica certa.
- `research/`: dossier di verifica territoriali. Conservano fonti, stato operativo, data di verifica e prossima revisione; non sono caricati dall'app come controlli attivi.

## Uso nell’app

L’app deve prima scaricare `manifest.json`, verificarne formato e hash, quindi applicare le differenze nel database SQLite locale. L’assenza di rete non deve mai rimuovere il catalogo offline già verificato.

## Fonti e licenze

- I dati OpenStreetMap derivano da OpenStreetMap contributors e sono disponibili secondo [ODbL 1.0](https://www.openstreetmap.org/copyright).
- Le tratte Tutor ASPI mantengono le rispettive fonti per singolo record e nel manifesto: pagina ASPI, elenco Polizia di Stato, comunicato delle nuove tratte e decreto MIT per Tutor 3.0. La pubblicazione di questi estratti non sostituisce le fonti ufficiali né costituisce una segnalazione in tempo reale.

I dati sono un supporto al rispetto dei limiti. Verificare sempre segnaletica, traffico e condizioni della strada.
