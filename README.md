# AMR Brand Assets — Claude Instructions

> **Alma Media Ratkaisut (AMR)** – tyyliopas ja assettikansio Claude-avusteista dokumenttituotantoa varten.  
> Värit ja fontit on poimittu suoraan virallisesta AMR-pohjaesityksestä (teema: *AMR UUSI*).

---

## ⚡ Pikaohjeet Claudelle

Kun sinua pyydetään rakentamaan AMR-brändin mukainen **PowerPoint-esitys**:
1. Käytä `templates/template.pptx` pohjana — editoi, älä rakenna tyhjästä
2. Lue `guidelines/layout.md` — dia-tyypit, marginaalit, logo-positiot
3. Värit: `colors/brand-colors.json`
4. Fontit: `fonts/fonts.json` — **pääfontti on Archivo** (ei Calibri, ei Aptos)
5. Logo: `logos/alma/logo-primary.svg` (vaalealle taustalle) tai `logos/alma/logo-white.svg` (tummalle)

Kun sinua pyydetään rakentamaan AMR-brändin mukainen **PDF-dokumentti**:
1. Lue `guidelines/typography.md` — fonttikoot ja hierarkia
2. Lue `guidelines/layout.md` — PDF-marginaalit ja rakenne
3. Värit ja fontit samat kuin esityksissä
4. Käytä ReportLab-kirjastoa (Python) tai LibreOffice-konversiota

---

## 🎨 Brändisummary

| Elementti            | Arvo                                      |
|----------------------|-------------------------------------------|
| Pääväri 1            | Medium Red Violet `#9F248F` (PMS 254C)    |
| Pääväri 2            | Persian Green `#28B78F` (PMS 7473C)       |
| Tehosteväri          | Olive Green `#C2C83D` (PMS 611C) — ei pohjaväriksi |
| Otsikkofontti        | **Archivo Extrabold** — VERSAALI otsikoissa |
| Leipätekstifontti    | **Archivo Regular**                       |
| Ohut dekoratiivinen  | Archivo Thin                              |
| Dian koko            | 33.87 × 19.05 cm (16:9 widescreen)        |
| PDF-marginaalit      | 2.5 cm kaikilla reunoilla                 |

---

## 📁 Hakemistorakenne

```
amr-brand-assets/
├── README.md                      ← tämä tiedosto (lue aina ensin)
├── colors/
│   └── brand-colors.json          ← AMR-värit hex + Pantone + käyttöohjeet
├── fonts/
│   └── fonts.json                 ← Archivo-fontit, koot, fallback-fontit
├── logos/
│   ├── logo-primary.png           ← AMR-logo väriversio (vaalealle taustalle)
│   ├── logo-white.png             ← valkoinen logo (tummalle taustalle)
│   ├── logo-dark.png              ← tumma logovariantti
│   └── logo-alt.png               ← vaihtoehtoinen versio
├── templates/
│   ├── template.pptx              ← virallinen AMR-pohja (editoi tätä)
│   └── template-notes.md          ← ohjeet pohjan käyttöön ja slide-layoutit
└── guidelines/
    ├── typography.md              ← fonttihierarkia ja tekstisäännöt
    ├── layout.md                  ← marginaalit, grid, dia-tyypit, PDF-rakenne
    └── tone.md                    ← kirjoitustyyli ja äänensävy
```

---

## ⚠️ Tärkeät muistutukset

- **Archivo ei ole Office-safe-fontti** — LibreOffice QA-esikatselu voi näyttää tekstin eri leveänä kuin PowerPoint. Jätä tekstilaatikoihin ~10% ylimääräistä tilaa.
- **Olive Green on tehosteväri** — ei sovellu suuriin taustapintoihin, vain aksentiksi ja kuvakkeisiin.
- **Logot löytyvät myös SharePointista** — kansio: `_AMR Logot`
- **ÄLÄ käytä Aptosta** — ei yhteensopiva vanhemmissa Office-versioissa.

---

## ✅ Muistilista ennen julkaisua

- [ ] Logo näkyy oikeassa kohdassa ja oikeana versiona (väri/valkoinen)
- [ ] Värit vastaavat `brand-colors.json` -arvoja
- [ ] Otsikot VERSAALILLA (paitsi pitkät otsikot: gemena sallittu)
- [ ] Ei ylittäviä tekstilaatikoita
- [ ] Arquivo-fontit käytössä, ei Aptosta
- [ ] Diat QA-tarkastettu visuaalisesti

---

> 📌 **Claudelle:** Jos jokin assetti puuttuu hakemistosta, mainitse se käyttäjälle selkeästi. Älä korvaa puuttuvaa logoa arvauksella.
