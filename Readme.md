flowchart TD

classDef aktivnost fill:#e6eef7,stroke:#000;
classDef odluka fill:#a7f5a5,stroke:#000,shape:diamond;

A[Kupac ulazi u web-shop]:::aktivnost --> B[Pregled proizvoda]:::aktivnost
B --> C[Dodavanje u košaricu]:::aktivnost
C --> D[Unos podataka i izbor plaćanja]:::aktivnost

D --> E{Plaćanje uspješno?}:::odluka

E -->|NE| F[Obavijest o pogrešci]:::aktivnost
F --> K[KRAJ]:::aktivnost

E -->|DA| G[Kreiran nalog u sustavu]:::aktivnost

G --> H[Skladište zaprimilo narudžbu]:::aktivnost
H --> I[Priprema paketa]:::aktivnost
I --> J[Dostava kupcu + potvrda]:::aktivnost
J --> K
