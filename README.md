# Tutor Companion — data catalog

Cataloghi JSON pubblici da usare per aggiornare offline Tutor Companion. Questo repository contiene soltanto dati e metadati: non include codice dell’app, chiavi, configurazioni o dati degli utenti.

## File pubblicati

- `manifest.json`: versione del catalogo, fonti, numero di record e hash SHA-256;
- `data/speed-cameras.json`: autovelox fissi geolocalizzati;
- `data/tutor-sections-osm.json`: tratti a velocità media geolocalizzati;
- `data/tutor-sections-aspi.json`: tratte Tutor pubblicate da Autostrade per l’Italia;
- `data/mit-velox-devices.json`: registro dei dispositivi MIT, che non implica una posizione geografica certa.

## Uso nell’app

L’app deve prima scaricare `manifest.json`, verificarne formato e hash, quindi applicare le differenze nel database SQLite locale. L’assenza di rete non deve mai rimuovere il catalogo offline già verificato.

## Fonti e licenze

- I dati OpenStreetMap derivano da OpenStreetMap contributors e sono disponibili secondo [ODbL 1.0](https://www.openstreetmap.org/copyright).
- Le tratte Tutor ASPI e il registro MIT mantengono le rispettive fonti indicate nel manifesto. La pubblicazione di questi estratti non sostituisce le fonti ufficiali né costituisce una segnalazione in tempo reale.

I dati sono un supporto al rispetto dei limiti. Verificare sempre segnaletica, traffico e condizioni della strada.
