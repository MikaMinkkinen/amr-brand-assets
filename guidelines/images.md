# AMR Kuvituskuvat, brändigrafiikka ja mock-upit

> **Claudelle:** Tämä tiedosto kuvaa SÄÄNNÖT (kansiorakenne, koot, nimeämis-
> käytäntö) kuvien käyttöön AMR-esityksissä. Se EI sisällä listaa itse
> kuvista — ne elävät SharePointissa ja niiden luettelo/kuvaus pidetään
> SharePoint-kansion omassa `README.md`:ssä, koska se muuttuu aina kun joku
> lisää tai poistaa kuvia. Tämä tiedosto muuttuu vain kun itse SÄÄNTÖÄ
> muutetaan, joten se sopii versionhallintaan; kuvat ja niiden kuvaukset
> eivät.

---

## Miksi kuvat eivät ole tässä repossa

Kuvituskuvia ja mock-upeja **ei synkata eikä kopioida** `amr-brand-assets`-
repoon eikä Git LFS:ään, toisin kuin pohja, fontit, värit ja logot. Ne
haetaan **suoraan SharePointista joka kerta** esitystä tehdessä:

- **Sivusto:** AMRDike
- **Polku:** `Shared Documents/Tuote/ai-assets/images`

Tämä on tietoinen valinta: kuvakirjastoa ylläpitää liiketoiminta suoraan
SharePointissa ilman git-osaamista, eikä kukaan joudu muistamaan synkata
kuvia repoon aina kun kirjasto päivittyy.

---

## Kolme kansiota, kolme eri käyttötarkoitusta

```
images/                          (SharePointissa, ei täällä)
├── README.md                    ← per-kuva-kuvaukset/avainsanat, elää SharePointissa
├── illustrations/                ← valokuvat pohjan valmiisiin kuvapaikkoihin
│   ├── cover-hero/
│   ├── section-hero/
│   └── content-side/
├── brand/                        ← brändin oma graafinen kuvitus (kuvioita/tekstuureja
│   │                                valokuvan sijaan samoihin kuvapaikkoihin)
│   ├── cover-hero/
│   ├── section-hero/
│   └── content-side/
└── mockups/                      ← vapaasti sijoitettavat esikatselukuvat,
    ├── kauppalehti/                 mediabrändin ja laitetyypin mukaan jaoteltuna
    │   ├── desktop/
    │   ├── mobile/
    │   └── print/
    ├── iltalehti/
    │   ├── desktop/
    │   ├── mobile/
    │   └── print/
    └── <muut mediabrändit samalla kaavalla>
```

**Eron logiikka:**

| Kansio | Mitä | Miten liitetään |
|---|---|---|
| `illustrations/` | Valokuvat: toimisto, ihmiset, työelämä, abstraktit tunnelmakuvat | Pohjan valmis kuvapaikka (`custGeom`-rajaus periytyy automaattisesti) |
| `brand/` | AMR:n oma graafinen kuvitus: kuvioita, tekstuureja, brändivärien yhdistelmiä — käytetään kun halutaan valokuvan sijaan abstraktimpi, puhtaasti brändin mukainen tausta | Sama pohjan valmis kuvapaikka kuin `illustrations/` — samat koot/suhteet |
| `mockups/` | Esikatselu siitä miltä mainos näyttää oikeassa kontekstissa (selain/puhelin/printti) | Vapaasti sijoitettu, ei pohjan paikkamerkkiin sidottu |

`illustrations/` ja `brand/` jakavat saman alikansiorakenteen ja samat
kokovaatimukset, koska ne täyttävät täsmälleen samat kuvapaikat — kyse on
vain siitä, halutaanko valokuva vai graafinen/abstrakti tausta.

---

## Kuvakoot ja -suhteet

Koot on johdettu suoraan pohjan omista kuvapaikoista (`template.pptx`, ks.
`template-notes.md`). **Kuvasuhde on tärkeämpi kuin tarkka pikselimäärä** —
väärä suhde tarkoittaa venymistä tai ei-toivottua rajautumista:

| Kansio | Kuvasuhde (L:K) | Suunta | Minimikoko | Suositus |
|---|---|---|---|---|
| `illustrations/cover-hero/`, `brand/cover-hero/` | ~0,91:1 | pysty | 1600×1760 px | 2400×2640 px |
| `illustrations/section-hero/`, `brand/section-hero/` | ~0,91:1 | pysty | 1600×1760 px | 2400×2640 px |
| `illustrations/content-side/`, `brand/content-side/` | ~0,89:1 | pysty | 1200×1350 px | 1800×2025 px |
| `mockups/*/desktop/` | ~16:10 (1,6:1) | vaaka | 1920×1200 px | 2400×1500 px |
| `mockups/*/mobile/` | ~9:19,5 (0,46:1) | pysty | 1080×2340 px | 1290×2796 px |
| `mockups/*/print/` | ~0,7:1 (A-sarja) | pysty | 1240×1754 px | 1754×2481 px |

Muita huomioita:
- **Tiedostomuoto:** valokuvat ja brändigrafiikka JPEG (laatu ~85-90) ellei
  tarvita läpinäkyvyyttä (silloin PNG). Mock-upit (ruutukaappaustyyppiset)
  mieluummin PNG — terävä teksti/UI, ei JPEG-artefaktia.
- **Väriavaruus:** sRGB.
- Jos kuva ei ole täsmälleen oikeassa suhteessa, se venyy paikalleen
  (`fillRect`) — tarkista aina visuaalisessa QA:ssa ettei kuva näytä
  venytetyltä, ja rajaa kuvasuhde ennen liittämistä jos ero on suuri (>~5 %).

---

## Nimeämislogiikka

`<kuvaus>-<konteksti>.<pääte>`, pienillä kirjaimilla, väliviivoin, **ei
ääkkösiä tiedostonimessä** (å/ä/ö → a/o, jotta polut/URL:t eivät riko mitään).
SharePointin haku (`sharepoint_search`) osuu tiedostonimeen ja sisältöön
mutta ei tue erillisiä tagi-sarakkeita tämän liittimen kautta, joten
kuvaava nimi on ainoa hakukahva sen lisäksi mitä SharePoint-kansion oma
`README.md` kertoo.

- Kuvituskuva: `toimisto-tiimipalaveri.jpg`, `data-analytiikka-naytolla.jpg`
- Brändigrafiikka: `brand-kuvio-violetti-vihrea.jpg`, `brand-tekstuuri-pisteet.jpg`
- Mock-up: `kauppalehti-mobile-etusivu-bannerimainos.png`,
  `iltalehti-desktop-artikkelisivu-native.png`

Kuvaava sisältö ensin (hakuosuvuus), konteksti (sivu/sijoittelu/laite)
perässä. Mediabrändi näkyy sekä kansiopolussa että tiedostonimessä
mock-upeille, jotta haku osuu myös ilman kansiorajausta.

---

## Hakuprosessi (tekninen, ks. myös SKILL.md Vaihe 7)

1. Hae `images/`-kansio SharePointista (`sharepoint_folder_search` /
   `read_resource`) — älä oleta tämän tiedoston kansiorakennetta ilman että
   vahvistat sen ensin oikeasta SharePoint-sisällöstä, koska kirjasto elää
   siellä eikä täällä.
2. Lue kansion oma `README.md` ensin — se kertoo mitä kuvia on tarjolla ja
   millä avainsanoilla.
3. Hae ja liitä kuva `amr-pptx`-skillin `scripts/insert_picture_placeholder.py`
   -skriptillä (placeholder-tila `illustrations/`- ja `brand/`-kuville,
   `--new`-tila `mockups/`-kuville).
4. Tekijänoikeudet: tämä kansio (kaikki kolme alikansiota) on ainoa
   hyväksytty lähde — älä koskaan korvaa puuttuvaa kuvaa yleisellä
   web-haulla.
