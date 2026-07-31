# AMR Logot

Logokansio on jaettu AMR-brändin omaan logoon ja julkaisijabrändeihin.

## Rakenne

```
logos/
├── alma/
│   ├── logo-primary.svg     ← väriversio vaalealle taustalle
│   ├── logo-primary.png
│   ├── logo-white.svg       ← valkoinen tummalle taustalle
│   └── logo-white.png
│
├── brands/
│   ├── iltalehti/
│   │   ├── logo-primary.svg
│   │   ├── logo-primary.png
│   │   ├── logo-white.svg
│   │   └── logo-white.png
│   ├── kauppalehti/
│   ├── talouselama/
│   ├── tekniikkatalous/
│   ├── tivi/
│   ├── arvopaperi/
│   ├── etuovi/
│   ├── vuokraovi/
│   ├── nettiauto/
│   ├── nettivene/
│   ├── nettimoto/
│   └── nettikone/
│
└── README.md
```

## Nimeämiskäytäntö

| Tiedostonimi        | Käyttö                                    |
|---------------------|-------------------------------------------|
| `logo-primary.svg`  | Brändin päävärilogo — vaalealle taustalle |
| `logo-primary.png`  | PNG-versio samasta                        |
| `logo-white.svg`    | Valkoinen versio — tummalle taustalle     |
| `logo-white.png`    | PNG-versio samasta                        |

## Ohjeet Claudelle

- Käytä SVG:tä ensisijaisesti — se skaalautuu vektorina
- PowerPoint-dioihin käytä PNG:tä (SVG ei tue suoraan python-pptx / pptxgenjs -kirjastoissa)
- Vaalealla pohjalla → `logo-primary.png`
- Värillisellä tai kuvataustalla → `logo-white.png`
- ÄLÄ lataa logoja internetistä — käytä vain tästä kansiosta löytyviä
- Jos logo puuttuu, mainitse se käyttäjälle selkeästi

## Status

| Brändi           | SVG | PNG |
|------------------|-----|-----|
| AMR              | ✅  | ✅  |
| Iltalehti        | ✅  | ✅  |
| Kauppalehti      | ✅  | ✅  |
| Talouselämä      | ✅  | ✅  |
| Tekniikka&Talous | ✅  | ✅  |
| Tivi             | ✅  | ✅  |
| Arvopaperi       | ✅  | ✅  |
| Etuovi.com       | ✅  | ✅  |
| Vuokraovi.com    | ✅  | ✅  |
| Nettiauto        | ✅  | ✅  |
| Nettivene        | ✅  | ✅  |
| Nettimoto        | ✅  | ✅  |
| Nettikone        | ✅  | ✅  |
