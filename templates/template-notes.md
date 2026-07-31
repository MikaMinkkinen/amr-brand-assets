# AMR PowerPoint-pohjan käyttöohjeet

> **Claudelle:** Pohja ei ole tässä repossa — se haetaan aina SharePointista.

---

## Pohjan sijainti

**SharePoint:** `AMRDike / Shared Documents / Tuote / ai-assets / templates / template.pptx`

Hae pohja Microsoft 365 SharePoint -yhteydellä näin:
```
sharepoint_search(query="template AMR pohja", folderName="AMRDike", fileType="pptx")
→ valitse tiedosto nimeltä "template.pptx"
→ lue sisältö: read_resource(uri="file:///...")
```

Pohja päivittyy säännöllisesti — käytä aina SharePointin uusinta versiota, älä tallenna paikallista kopiota pitkäksi aikaa.

---

## Pohjan tiedot (viimeksi tarkistettu 31.7.2026)

- **Teema:** AMR UUSI
- **Fonttikaava:** Raleway → major: Archivo Extrabold, minor: Archivo
- **Värikaava:** Medium Red Violet (#9F248F), Persian Green (#28B78F), Olive Green (#C2C83D)
- **Dian koko:** 33.87 × 19.05 cm (16:9 widescreen)
- **Dioja:** 45 kpl (ohjeet + valmiit layoutit)

---

## Käyttö Claudelle

Kun käyttäjä antaa pohjan (`*.pptx`), toimi näin:

1. Lue pohjan rakenne: `python /mnt/skills/public/pptx/scripts/thumbnail.py pohja.pptx thumbs`
2. Käytä dioja 11–45 sisältöpohjina — diat 1–10 ovat ohjesivuja
3. Älä poista: logo-shape, footer-shape, sivunumero-placeholder
4. Pakkaa takaisin ja validoi:
```bash
cd unpacked && rm -f ../output.pptx && zip -Xr ../output.pptx .
python /mnt/skills/public/pptx/scripts/office/validate.py output.pptx --original pohja.pptx
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
