# onlineCV – Kontext projektu

> Tento soubor čti vždy před zahájením jakýchkoliv úprav. Obsahuje vše potřebné pro orientaci v projektu bez nutnosti procházet celý kód.

---

## Co projekt je

Osobní online CV / portfolio Ing. Jakuba Kodeše – statická jednostránková webovka hostovaná na GitHub Pages.

- **URL:** https://jakubkodes.cz
- **GitHub repo:** https://github.com/Kubislavii/WEbovka
- **Lokální cesta:** `/Users/jakubkodes/Documents/Projekty Claude/WEbovka/`
- **Doména:** CNAME soubor → `jakubkodes.cz`

---

## Struktura souborů

```
WEbovka/
├── index.html       ← JEDINÝ soubor s celým webem (HTML + CSS + JS vše v jednom)
├── favicon.svg      ← favicon webu
├── CNAME            ← custom doména (jakubkodes.cz)
├── CLAUDE.md        ← obecné instrukce pro práci na projektu
├── onlineCV.md      ← tento soubor
└── Images/
    ├── Ja_web.png           ← hlavní foto (profilová fotka, hero sekce)
    ├── Ja.png               ← alternativní foto
    ├── JaMaly.png           ← menší varianta fotky
    ├── DSC_2377.JPG         ← původní fotka
    └── DSC_2377-removebg-preview.png
```

**Důležité:** Veškerý kód (HTML struktura, CSS styly, JS logika) je v jediném souboru `index.html`. Žádné externí JS/CSS soubory. Tailwind ani žádný framework – čisté HTML/CSS/JS.

---

## Technologie & architektura

- **Čisté HTML/CSS/JS** – žádný framework, žádné závislosti (kromě Google Fonts přes system-ui a Google Analytics)
- **Google Analytics:** `G-MD5M7SP8G1`
- **CSS custom properties (CSS variables)** – celý design token systém v `:root` (světlý) a `[data-theme="dark"]` (tmavý)
- **Responsive:** breakpointy na 920px, 768px, 580px

---

## Barevné schéma (CSS variables)

### Světlý mód (výchozí)
| Proměnná | Hodnota | Použití |
|---|---|---|
| `--accent` | `#009e8e` | hlavní zeleno-tyrkysová barva |
| `--accent-dim` | `rgba(0,158,142,0.10)` | jemné pozadí prvků |
| `--accent-border` | `rgba(0,158,142,0.30)` | ohraničení s akcentem |
| `--bg-primary` | `#f5f7fa` | pozadí stránky |
| `--text` | `#1a202c` | hlavní text |
| `--text-muted` | `rgba(26,32,44,0.68)` | tlumený text |
| `--text-subtle` | `rgba(26,32,44,0.42)` | velmi jemný text |
| `--card-bg` | `rgba(0,0,0,0.03)` | pozadí karet |
| `--heading-color` | `#0d1117` | nadpisy |

### Tmavý mód
| Proměnná | Hodnota |
|---|---|
| `--accent` | `#00d4b8` |
| `--bg-primary` | `#07091a` |
| `--text` | `#e6eeff` |
| `--heading-color` | `#fff` |

Tmavý mód má navíc radial-gradient pozadí (modro-fialová mlhovina).

---

## Sekce webu (v pořadí)

1. **Top controls** – fixovaná tlačítka vpravo nahoře: „Tmavá/Světlá" (přepínač tématu) + „EN/CS" (přepínač jazyka)
2. **Hero** – jméno, titulek, statement, kontakty (tel, email, LinkedIn) + profilová fotka vpravo
3. **Jak pracuju** (How I Work) – citátový box s popisem přístupu
4. **Pracovní zkušenosti** (Experience) – timeline s accordion rozbalováním
5. **Vybrané projekty** (Projects) – grid 3 sloupce, 5 karet
6. **Dovednosti** (Skills) – 2 sloupce: Hard Skills + Soft Skills jako pills
7. **Vzdělání** (Education) – 2 karty: VUT Brno + Erasmus Lyon
8. **Kontakt** (Contact) – tlačítka email/LinkedIn + velký kontakt
9. **Footer** – copyright

---

## Dvojjazyčnost (CS/EN)

Web je plně dvojjazyčný. Přepínání funguje přes JS objekt `t` v dolní části `index.html`.

- Každý textový element má atribut `data-key="klic"`
- Objekt `t` obsahuje dvě větve: `t.cs` a `t.en` se všemi texty
- Funkce `toggleLang()` přepíná `currentLang` a iteruje všechny `data-key` elementy
- Výchozí jazyk: **čeština** (`cs`)

**Při přidávání nového textu** vždy přidej překlad do OBOU větví (`cs` i `en`) a přidej `data-key` atribut na HTML element.

---

## Pracovní zkušenosti (obsah)

| # | Role | Firma | Období |
|---|---|---|---|
| 1 | Project Manager | Digitální agentura (název nezveřejněn) | 01/2026 – současnost |
| 2 | Marketing Project Manager | ACRIOS Systems s.r.o. | 01/2024 – 01/2025 |
| 3 | Project & Brand Manager | Purple Technology s.r.o. | 2019 – 2023 |
| 4 | Sales & Marketing Specialist | Reklama Kubíček s.r.o. | 2017 – 2019 |
| 5 | Marketing Specialist | Zetor Tractors a.s. | 2012 – 2016 |

---

## Vybrané projekty (obsah)

| # | Projekt | Klient |
|---|---|---|
| 01 | Zetor.cz | Zetor Tractors |
| 02 | Brand manuál, web & strategie | Reklama Kubíček s.r.o. |
| 03 | Axiory.com | Purple Technology |
| 04 | Fintokei | Purple Technology |
| 05 | ACRIOS Systems – Branding & Web | ACRIOS Systems s.r.o. |

---

## Dovednosti (obsah)

**Hard Skills:** Projektové řízení (end-to-end), Brand management, Webové projekty (UX, vývoj), Marketingová strategie, Koordinace týmů a stakeholderů, Spolupráce s externími dodavateli, Podpora prodeje a práce s leady

**Soft Skills:** Silné komunikační schopnosti, Empatie a orientace na stakeholdery, Analytické a kreativní myšlení, Práce pod tlakem / dodržování termínů, Týmová spolupráce a odpovědnost

---

## Vzdělání

- **VUT Brno** – Řízení a ekonomika podniku / Manažerská informatika, 2005–2010
- **IDRAC Business University of Lyon** – Erasmus (Business & Management), 2009

---

## Kontaktní údaje

- **Telefon:** +420 732 819 662
- **Email:** Jakub.kodes@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/jakubkodes
- **Web:** https://jakubkodes.cz
- **Lokace:** Brno, CZ

---

## Klíčové JS funkce

| Funkce | Co dělá |
|---|---|
| `toggleTheme()` | Přepíná `data-theme` na `<html>`, ukládá do `localStorage` |
| `toggleLang()` | Přepíná CS/EN, aktualizuje všechny `data-key` elementy |
| `toggleJob(header)` | Rozbaluje/sbaluje accordion položky v timeline |
| `IntersectionObserver` | Scroll animace – přidává třídu `.vis` na `.fade` elementy |

---

## Scroll animace

- Prvky s třídou `.fade` jsou zpočátku neviditelné (`opacity: 0`, `translateY: 28px`)
- `IntersectionObserver` při scrollu přidá třídu `.vis` → prvek se zobrazí
- Zpoždění `.d1`–`.d5` pro kaskádový efekt (0.08s krok)

---

## Accordion (timeline)

- Kliknutí na `.tl-header` zavolá `toggleJob(this)`
- `.tl-header` dostane třídu `.open`, `.tl-expand` dostane `.open`
- CSS animace přes `max-height` (0 → 700px) a `opacity`
- Šipka ▾ je v headeru, šipka ▴ je v rozbaleném obsahu (zavírá)

---

## Hosting & deployment

- **GitHub Pages** – hlavní větev `main`, automatický deploy
- Custom doména přes `CNAME` soubor (`jakubkodes.cz`)
- Po každém commitu + push se web automaticky aktualizuje

---

## Metadata & SEO

- Schema.org `Person` JSON-LD (jméno, job title, kontakty, LinkedIn)
- Open Graph tagy (LinkedIn/Facebook náhled)
- Twitter Card tagy
- `hreflang` pro CS + EN
- Canonical URL: `https://jakubkodes.cz/`
- Popis: "Ing. Jakub Kodeš – Project Manager | Marketing & Digital. 10+ let mezinárodních zkušeností."

---

## Časté úpravy – kde co najít

| Chci změnit... | Kde v index.html |
|---|---|
| Text v hero sekci | `data-key="hero_statement"` v HTML + obě větve v `t.cs` / `t.en` |
| Pracovní zkušenost | HTML blok `<!-- JOB X -->` + odpovídající klíče v `t.cs` / `t.en` |
| Projekt v gridu | HTML blok `.proj-card` + klíče `proj_X_*` v překladech |
| Skill pill | HTML `<span class="pill">` + klíč `sh_X` / `ss_X` |
| Barvy | CSS variables v `:root` (světlé) nebo `[data-theme="dark"]` |
| Kontaktní údaje | Hero sekce (HTML) + kontakt sekce (HTML) + Schema.org JSON-LD |
| Foto | Soubor `Images/Ja_web.png` (src v hero-photo-col img) |
