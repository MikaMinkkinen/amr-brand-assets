# AMR PowerPoint-pohjan käyttöohjeet

> **Claudelle:** Pohja on osa repoa. Käytä aina repon tiedostoa.

---

## Pohjan sijainti

**Repo:** `templates/template.pptx` (tallennettu Git LFS:llä)

Käytä pohjaa suoraan repon tiedostosta:
```bash
python /mnt/skills/public/pptx/scripts/thumbnail.py templates/template.pptx thumbs
```

Älä hae pohjaa muualta äläkä lataa sitä internetistä. Jos pohja on
päivitettävä, korvaa repon `templates/template.pptx` uudella versiolla ja
commitoi muutos.

---

## Pohjan tiedot (viimeksi tarkistettu 31.7.2026)

- **Teema:** AMR UUSI
- **Fonttikaava:** major: Archivo Extrabold, minor: Archivo
- **Värikaava:** Medium Red Violet (#9F248F), Persian Green (#28B78F), Olive Green (#C2C83D)
- **Dian koko:** 33.87 × 19.05 cm (16:9 widescreen)

---

## Dia-jaottelu (mallidiat sisältötyypeittäin)

> **Tämä on ainoa paikka, jossa dianumerot ylläpidetään.** Muut ohjeet (esim.
> `CLAUDE.md`) viittaavat tähän — älä kopioi numeroita muualle.

| Sisältötyyppi     | Käytä diaa           |
|-------------------|----------------------|
| Esityksen aloitus | diat 1–3 (cover)     |
| Osion vaihtuminen | diat 4–6 (section)   |
| Sisältö           | diat 7–9 (content)   |
| Roadmap           | dia 10   (roadmap)   |
| Päätös / kiitos   | diat 11–13 (closing) |

---

## Käyttö Claudelle

Kun rakennat esitystä, toimi näin:

1. Lue pohjan rakenne: `python /mnt/skills/public/pptx/scripts/thumbnail.py templates/template.pptx thumbs`
2. Valitse mallidiat yllä olevan **Dia-jaottelu**-taulukon mukaan
3. Älä poista: logo-shape, footer-shape, sivunumero-placeholder
4. Pakkaa takaisin ja validoi:
```bash
cd unpacked && rm -f ../output.pptx && zip -Xr ../output.pptx .
python /mnt/skills/public/pptx/scripts/office/validate.py output.pptx --original ../templates/template.pptx
```

---

## Muokkausohje

```python
# Muuta otsikko säilyttäen muotoilut — älä käytä text_frame.text = "..."
for shape in slide.shapes:
    if shape.has_text_frame and shape.name == "Title":
        for para in shape.text_frame.paragraphs:
            for run in para.runs:
                run.text = "UUSI OTSIKKO"
                break
```
