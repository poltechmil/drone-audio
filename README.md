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



