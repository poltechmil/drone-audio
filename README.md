# drone-audio

📡 Zbiór nagrań i narzędzi do analizy oraz klasyfikacji dźwięków dronów.  

To repozytorium gromadzi **próbki audio dronów (UAV)** wraz ze skryptami i metadanymi do badań, detekcji i analizy.  

---

## 📂 Struktura repozytorium


```text
drone-audio/
├── samples/          # Surowe nagrania audio (.wav, .mp3)
│   ├── consumer/     # Drony komercyjne / hobbystyczne
│   ├── military/     # Drony wojskowe
│   └── misc/         # Inne dźwięki lotnicze
├── metadata/         # JSON/CSV z metadanymi (model, lokalizacja, warunki)
├── scripts/          # Skrypty do przetwarzania i analizy
│   ├── spectrograms/ # Generowanie spektrogramów z audio
│   └── features/     # Ekstrakcja cech akustycznych (FFT, MFCC itp.)
└── README.md


## 📊 Przykład powiązania próbek z metadanymi

Każdy plik audio w katalogu `samples/` ma odpowiadający mu plik JSON w katalogu `metadata/`.  
Nazwy plików są takie same (różnią się tylko rozszerzeniem `.wav` vs `.json`).  

### Struktura

```text
samples/
├── consumer/
│   └── dji_mavic_air_01.wav
└── military/
    └── bayraktar_tb2_01.wav

metadata/
├── dji_mavic_air_01.json
└── bayraktar_tb2_01.json


### Przykład pliku `metadata/dji_mavic_air_01.json`

```json
{
  "filename": "dji_mavic_air_01.wav",
  "drone_model": "DJI Mavic Air",
  "category": "consumer",
  "recorded_at": "2025-09-20",
  "location": "teren zurbanizowany, plener",
  "description": "Lot zawisowy na wysokości ok. 10 m",
  "notes": "Nagranie w spokojnych warunkach pogodowych, brak wiatru"
}

