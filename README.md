# Teostatavusuuring: TI abil eestikeelse tehnilise informaatika lõputöö genereerimine

See repositoorium sisaldab Uku Renek Kronbergsi 2026. aasta bakalaureusetöö LaTeX-lähtekoodi, valminud PDF-i ning töö eksperimendis kasutatud TI-ga genereeritud näidislõputöid.

Töö uurib, kas ja millistel tingimustel suudavad kaasaegsed suured keelemudelid koos agentsete tööriistadega genereerida eestikeelse tehnilise informaatika lõputöö. Fookus ei ole ainult mudelitel eraldi, vaid mudeli ja tööriista kombinatsioonidel.

## Töö lühikokkuvõte

Bakalaureusetöös võrreldakse nelja mudel-tööriista kombinatsiooni:

- Google Gemini 3.1 Pro + Antigravity
- OpenAI GPT-5.4 + ChatGPT Codex Visual Studio Code'is
- Anthropic Claude Sonnet 4.6 + Cowork
- Anthropic Claude Opus 4.6 + Cowork

Kõigile kombinatsioonidele anti sama lühike eestikeelne viip, mis palus luua UniTartuCS mallil põhineva täieliku LaTeX-vormingus bakalaureusetöö ning valida ise informaatikaga seotud teema. Kuna iga kombinatsiooni kohta tehti üks jooks, käsitletakse tulemusi eksploratiivse hinnanguna, mitte lõpliku mudelite paremusjärjestusena.

Täiendava juhtumiuuringuna käsitletakse ka ühe tööpäeva pikkust iteratiivset seanssi Claude Opus 4.7 + Claude Code kombinatsiooniga.

## Repositooriumi struktuur

| Tee | Sisu |
| --- | --- |
| `thesis.tex` | Põhifail, millest lõputöö kompileeritakse. |
| `thesis.pdf` | Käesoleva bakalaureusetöö kompileeritud PDF. |
| `estonian/põhi.tex` | Töö metaandmed ja peatükkide kaasamine. |
| `estonian/sektsioonid/` | Lõputöö peatükid, lisad ja litsentsitekst. |
| `estonian/viited.bib` | Töö bibliograafiakirjed. |
| `estonian/seadistus.tex` | Viitamisstiil, värvid, graafikute seadistus ja lisapaketid. |
| `unitartucs/` | Tartu Ülikooli arvutiteaduse instituudi LaTeX-malli failid. |
| `Genereeritud lõputööd/` | Eksperimendis mudelite loodud PDF-väljundid. |
| `.latexmkrc` | Kohaliku kompileerimise seadistus `latexmk` jaoks. |

## Genereeritud väljundid

Kaustas `Genereeritud lõputööd/` on eksperimendi tulemusena salvestatud PDF-id:

| Fail | Kombinatsioon | Teema | Maht |
| --- | --- | --- | --- |
| `Gemini_3.1_Pro_Antigravity.pdf` | Gemini 3.1 Pro + Antigravity | GenAI ja algajad programmeerijad | 39 lk |
| `GPT_5.4_Visual_Studio_Codex.pdf` | GPT-5.4 + Codex VS Code'is | RAG-põhine küsimus-vastuse süsteem | 47 lk |
| `Sonnet_4.6_Cowork.pdf` | Claude Sonnet 4.6 + Cowork | LLM-id koodiülevaatuses | 40 lk |
| `Opus_4.6_Cowork.pdf` | Claude Opus 4.6 + Cowork | Turvaline paroolihaldur | 61 lk |
| `Opus_4.7_genereeitud_too_1_toopaev.pdf` | Claude Opus 4.7 + Claude Code ja OpenAI GPT-5.5 + Codex| Iteratiivne ühe tööpäeva juhtumiuuring | 57 lk |

## Kompileerimine

Projekt kasutab UniTartuCS LaTeX-malli ning on seadistatud eesti keeles kompileerimiseks.

Vajalikud tööriistad:

- TeX Live või muu täielik LaTeX-i distributsioon
- `latexmk`
- `lualatex`
- `biber`
- Python ja Pygments, sest mall kasutab `minted` paketti

Kompileerimiseks käivita repositooriumi juurkaustas:

```bash
latexmk thesis.tex
```

Fail `.latexmkrc` kasutab `lualatex`-i ning lisab `--shell-escape` lipu, mida on vaja `minted` paketi jaoks.

Abifailide eemaldamiseks:

```bash
latexmk -c
```

## Peatükkide ülevaade

- `1-sissejuhatus.tex` kirjeldab probleemi, eesmärki ja uurimisküsimusi.
- `2-taust.tex` annab ülevaate suurtest keelemudelitest, eesti keele toest ja TI kasutamisest akadeemilises kirjutamises.
- `3-metoodika.tex` kirjeldab mudelite valikut, ühe kasutajaviibaga eksperimenti ja hindamiskriteeriume.
- `4-mudelid.tex` võrdleb valitud mudel-tööriista kombinatsioone.
- `5-eksperimendid.tex` esitab põhitulemused ja mudelite genereeritud tööde analüüsi.
- `6-toovoog.tex` kirjeldab käesoleva bakalaureusetöö enda kirjutamise töövoogu.
- `7-arutelu.tex` tõlgendab tulemusi, piiranguid ja praktilisi soovitusi.
- `8-kokkuvote.tex` võtab töö järeldused kokku.
- `10-lisad.tex` sisaldab eksperimendi viipa, väljundfailide nimekirja ja näitekatkendeid.
- `11-litsents.tex` sisaldab lõputöö lihtlitsentsi.


Autor: Uku Renek Kronbergs
Juhendaja: Alo Peets (MSc)
Õppekava: Informaatika
Ülikool: Tartu Ülikool, arvutiteaduse instituut
