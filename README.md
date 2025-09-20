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
```

---

## 📊 Przykład powiązania próbek z metadanymi

Każdy plik audio w katalogu `samples/` ma odpowiadający mu plik JSON w katalogu `metadata/`.  
Nazwy plików są takie same (różnią się tylko rozszerzeniem `.wav` vs `.json`).  

---

## 📂 Struktura danych

```text
samples/
├── shahed_136_data_01.wav
└── shahed_136_data_02.wav

metadata/
├── shahed_136_data_01.json
└── shahed_136_data_01.json
```

---

## 📑 Konwencja nazewnicza i metadane

Pliki audio w katalogu `samples/` i odpowiadające im pliki metadanych w `metadata/` mają identyczne nazwy
(różnią się tylko rozszerzeniem). 

### Format nazwy

```
<model>_<data>_<nr>.<ext>
```

- **`<model>`** – nazwa drona, zapisana małymi literami, spacje zastąpione `_` (np. `dji_mavic_air`, `bayraktar_tb2`)  
- **`<data>`** – data dodania nagrania w formacie `YYYYMMDD` (np. `20250920`)  
- **`<nr>`** – numer próbki z tego dnia (np. `01`, `02`)  
- **`<ext>`** – rozszerzenie pliku  
  (`wav` dla nagrań audio, `json` dla metadanych)

### Przykłady

```text
samples/shahed_136_20250920_01.wav
metadata/shahed_136_20250920_01.json

samples/shahed_136_20250920_02.wav
metadata/shahed_136_20250920_02.json
```

---

## 📝 Szablon metadanych (JSON)

Każdy plik `.wav` w katalogu `samples/` ma odpowiadający mu plik `.json` w katalogu `metadata/`.  

```json
{
  "filename": "shahed_136_20250920_01.wav",
  "drone_model": "Shahed 136",
  "location": "teren zurbanizowany",
  "description": "Przelot na wysokości ok. 100 m",
  "notes": "Nagranie w spokojnych warunkach pogodowych, brak wiatru"
}
```

### Pola

- **filename** – nazwa pliku audio w katalogu `samples/`  
- **drone_model** – pełna nazwa modelu drona  
- **location** – miejsce i warunki nagrania  
- **description** – krótki opis nagrania  
- **notes** – dodatkowe uwagi (np. zakłócenia, otoczenie)  
