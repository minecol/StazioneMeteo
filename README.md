# Stazione Meteo
Questo progetto consiste in uno script Python per un Raspberry Pi che trasforma il tuo dispositivo in una stazione meteorologica. È stato sviluppato come parte di un progetto scolastico per esplorare concetti di programmazione e sensori.

# Funzionalità
* Rilevamento dei dati meteorologici: Utilizza sensori per rilevare temperatura, umidità e pressione atmosferica.
* Visualizzazione dei dati: Mostra i dati raccolti sul terminale del Raspberry Pi in tempo reale.
* Archiviazione dei dati: Salva i dati su file per analisi future.

# TO-DO codice
- [ ] Per utilizzare lo script è necessario il possesso del sensore e delle librerie, gestire l'avvio di una versione di debug che lancia numeri randomici senza utilizzare ed importare le librerie del sensore così da poter provare il codice in autonomia
- [ ] La prima misura ad ogni riavvio mostra sempre dati errati, bisogna ignorarla
- [ ] La stazione in rete potrebbe inviare direttamente i dati in un google sheet (o in una coda mqtt) al posto di inserirli in un file locale
- [ ] Il dato inserito nel file utilizza troppe cifre decimali, va vista la percentuale di errore sulla misura ed utilizzare solo le cifre significative
- [ ] Il sensore Enviro+ può registrare altre misure oltre a temperatura pressione ed umidità, raccogliere anche quelle
- [ ] Lo script perde qualche millisecondo ad ogni misurazione, queste si accumulano e col passare dei giorni le misure risultano sfasate, assicurarsi quindi che ogni giorno si ricominci esattamente allo stesso orario così da compensare 

# TO-DO pratico
- [ ] Il sensore di temperatura inserito in modalità standard è troppo vicino al processore, questo falsa la misura di temperatura di diversi gradi. Allontanare il sensore attraverso cavetteria.
- [ ] Il guscio protettivo del dispositivo è al momento insufficente e temporaneo, costruire una scatola protettiva che permetta al sensore di lavorare senza essere colpito dalla pioggia e che faccia defluire l'acqua che eventualmente entra nella protezione
- [ ] La postazione in cui è posizionato il dispositivo è scialba, va abbellita e resa più gadevole

# Dati
I Dati che raccogliamo sono attualmente:
* Temperatura
* Pressione
* Umidità

# Requisiti
* Raspberry Pi 
* Sensore Elviro+ per temperatura, umidità e pressione atmosferica compatibili con Raspberry Pi
* Libreria Elviro per python (disponibile su [Github](https://github.com/pimoroni/enviroplus-python))
* Python 3.x

# Installazione
Clona il repository sul tuo Raspberry Pi:
``` 
git clone https://github.com/Torfab/StazioneMeteo.git
```

Assicurati di avere i requisiti installati sul tuo Raspberry Pi.

Esegui lo script Python:

```
cd stazione-meteo
python stazione_meteo.py
```
Assicurati di aver installato la libreria Elviro e configurato correttamente il sensore prima di eseguire lo script. Troverai ulteriori informazioni sulla configurazione dei sensori nel repository della libreria Elviro.

# Licenza
Questo progetto è rilasciato sotto la licenza MIT. Sentiti libero di utilizzare, modificare e distribuire questo software secondo i termini della licenza.

# Note Finali
È consigliato far partire lo script allo startup così che in seguito a blackout o reboot il raspberry riprenda automaticamente a registrare i dati.

Assicurati di collegare correttamente il sensore al tuo Raspberry Pi e di configurare le credenziali di rete se desideri utilizzare funzionalità di condivisione dei dati su Internet.
