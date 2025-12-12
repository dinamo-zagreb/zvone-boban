```mermaid
flowchart TD

classDef aktivnost fill:#e6eef7,stroke:#000;
classDef odluka fill:#a7f5a5,stroke:#000,shape:diamond;
classDef spremnik fill:#f7d43b,stroke:#000;

A[Kupac ulazi u web-shop]:::aktivnost --> B[Pregled proizvoda]:::aktivnost
B --> C[Dodavanje u košaricu]:::aktivnost
C --> D[Unos podataka i izbor plaćanja]:::aktivnost

D --> E{Plaćanje uspješno?}:::odluka

E -->|NE| F[Obavijest o pogrešci]:::aktivnost
F --> K[KRAJ]:::aktivnost

E -->|DA| G[Kreiran nalog u sustavu]:::aktivnost

G --> S
S[Skladište zaprimilo narudžbu?]:::spremnik

style S clip-path: polygon(50% 100%, 0 0, 100% 0);

S --> H[Priprema paketa]:::aktivnost
H --> I[Dostava kupcu + potvrda]:::aktivnost
I --> K
