# drone-audio

📡 Zbiór nagrań i narzędzi do analizy oraz klasyfikacji dźwięków dronów.  

To repozytorium gromadzi **próbki audio dronów (UAV)** wraz ze skryptami i metadanymi do badań, detekcji i analizy.  

---

## 📂 Struktura repozytorium

```text
drone-audio/
├── samples/          # Surowe nagrania audio (.wav, .mp3)
├── metadata/         # Pliki JSON z metadanymi (model, lokalizacja, warunki)
├── scripts/          # Skrypty do przetwarzania i analizy
│   ├── spectrograms/ # Generowanie spektrogramów z audio
│   └── features/     # Ekstrakcja cech akustycznych (FFT, MFCC itp.)
└── README.md


## 📊 Przykład powiązania próbek z metadanymi

Każdy plik audio w katalogu `samples/` ma odpowiadający mu plik JSON w katalogu `metadata/`.  
Nazwy plików są takie same (różnią się tylko rozszerzeniem `.wav` vs `.json`).  


## 📂 Struktura danych

```text
samples/
├── dji_mavic_air_01.wav
└── bayraktar_tb2_01.wav

metadata/
├── dji_mavic_air_01.json
└── bayraktar_tb2_01.json


## 📑 Konwencja nazewnicza i metadane

Pliki audio w katalogu `samples/` i odpowiadające im pliki metadanych w `metadata/` mają identyczne nazwy
(różnią się tylko rozszerzeniem). 

### Format nazwy

<model>_<data>_<nr>.<ext>

- `<model>` – nazwa drona, zapisana małymi literami, spacje zastąpione `_` (np. `dji_mavic_air`, `bayraktar_tb2`)  
- `<data>` – data dodania nagrania w formacie `YYYYMMDD` (np. `20250920`)  
- `<nr>` – numer próbki z tego dnia (np. `01`, `02`)  
- `<ext>` – rozszerzenie pliku (`wav` dla nagrań audio, `json` dla metadanych)  

### Przykłady

samples/dji_mavic_air_20250920_01.wav  
metadata/dji_mavic_air_20250920_01.json  

samples/bayraktar_tb2_20250920_02.wav  
metadata/bayraktar_tb2_20250920_02.json  

---

### Szablon metadanych (JSON)

Każdy plik `.wav` w katalogu `samples/` ma odpowiadający mu plik `.json` w katalogu `metadata/`.  

{
  "filename": "dji_mavic_air_20250920_01.wav",
  "drone_model": "DJI Mavic Air",
  "recorded_at": "2025-09-20",
  "location": "teren zurbanizowany, plener",
  "description": "Lot zawisowy na wysokości ok. 10 m",
  "notes": "Nagranie w spokojnych warunkach pogodowych, brak wiatru"
}

### Pola

- **filename** – nazwa pliku audio w katalogu `samples/`  
- **drone_model** – pełna nazwa modelu drona  
- **recorded_at** – data nagrania (`YYYY-MM-DD`)  
- **location** – miejsce i warunki nagrania  
- **description** – krótki opis nagrania  
- **notes** – dodatkowe uwagi (np. zakłócenia, otoczenie)  
