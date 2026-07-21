# 🅿️ Parking Report

Systém pro sledování rezervací firemního parkování pro dva uživatele s mobilním přístupem.

---

## 📱 Postup update z mobilu (iPhone)

### 1. Nahraj screenshot do GitHub
1. Otevři **GitHub app** (App Store) → repozitář `Parking`
2. Přejdi do složky `[IN]`
3. Klikni **+** → *Upload file* → vyber screenshot z parkovacího systému
4. Screenshot musí mít dole text s instrukcí, např. `Úterý audi, zbytek mini`
5. **Commit** přímo v aplikaci

### 2. Stáhni změny na NTB
1. Otevři **GitHub Desktop** na notebooku
2. Klikni **Fetch origin** → pak **Pull origin**
3. Nový screenshot se objeví v `[IN]` složce lokálně

### 3. Nech Claudovi zpracovat
1. Otevři **Cowork** na notebooku
2. Napiš: **"zpracuj nové screenshoty v [IN]"**
3. Claude vytěží data a aktualizuje `Parking.html`

### 4. Publikuj
1. V **GitHub Desktop**: **Commit → Push**
2. Za 1–2 minuty je report živý na `https://JoshMEnow.github.io/Parking/Parking.html`
3. Na mobilu klikni **↻** pro aktualizaci

---

## Co to dělá

- Čte screenshoty z parkovacího systému uložené ve složce `[IN]`
- Vytěží z nich datumy a typ auta (instrukce je text dole pod obrázkem, např. *"Minik"* nebo *"Úterý audi, zbytek minicooper"*)
- Aktualizuje `Parking.html` — živý report dostupný na webu
- Označí duplicity (stejné datum z více screenshotů)

## Struktura

```
Parking/
  [IN]/          ← sem nahrávají screenshoty oba uživatelé
  [OUT]/         ← zpracované screenshoty (archiv)
  Parking.html   ← živý report (GitHub Pages)
  README.md
```

## Report (Parking.html)

- Banner **DNES** — okamžitě vidíš kde dnes parkuješ a jakým autem
- Záložky aut: Vše / 🚙 Mini / 🚗 Audi / 🚐 Kodiaq — každé s RZ a barvou auta při výběru
- Záložky času: Nadcházející / Historie / Vše
- Duplicity označeny oranžově ⚠️
- Tlačítko **↻** vpravo nahoře pro aktualizaci (obchází cache iOS)
- Zobrazuje čas posledního refreshe uživatelem
- Funguje jako webová zkratka na iPhone (Safari i Chrome)

**URL:** `https://JoshMEnow.github.io/Parking/Parking.html`

## Workflow

### Přidání nových rezervací
1. Nahraj screenshot(y) do složky `[IN]`
2. Každý screenshot musí mít dole text s instrukcí o autě, např.:
   - `Minik` → všechny datumy = Mini Cooper
   - `Úterý audi, zbytek minicooper` → dle dne v týdnu
3. V Cowork řekni Claudovi: *„zpracuj nové screenshoty v [IN]"*
4. Claude aktualizuje `Parking.html` a označí zpracované soubory
5. V GitHub Desktop: **Commit → Push**
6. Report je živý do 1–2 minut

### Druhý uživatel (iPhone2)
- Nahrává screenshoty přes **GitHub app** (App Store) do složky `[IN]`
- Report čte na stejné URL v Safari/Chrome

## Auta, RZ a barvy

| Auto | RZ | Barva tlačítka | Barva pruhu |
|---|---|---|---|
| 🚙 Mini Cooper | 7AY8867 | britská zelená | zelená |
| 🚗 Audi Q7 | 6AK5140 | bílá | modrá |
| 🚐 Kodiaq | 8AN9096 | vesmírná šedá | hnědá |

## Lokace

| Kód | Barva pruhu |
|---|---|
| SHQ0 | modrá |
| NHQ0 | oranžová |
| HHQ0 / Bazén | fialová |

## Logika zpracování screenshotů

- **Uživatel** se čte z horní části screenshotu (`You` = Josh, `Andreika` = Andreika)
- **Instrukce** (typ auta) se čte z dolního textu, např. `minik`, `Úterý audi, zbytek mini`
- **Duplicita**: stejné datum od různých uživatelů → označeno ⚠️
- **Update**: stejné datum od stejného uživatele → přepíše předchozí záznam
- **Zrušení**: datum chybí v novějším screenshotu stejného uživatele → odstraněno z dat
- **Zpracované soubory**: označeny `.done` markerem v `[IN]` (binární soubory nelze přesunout)

## Technologický stack

| Vrstva | Technologie |
|---|---|
| Hosting | GitHub Pages (zdarma, statický HTML) |
| Správa kódu | GitHub + GitHub Desktop (Windows) |
| Vstup dat | GitHub app (iOS) → složka `[IN]` |
| Zpracování | Claude / Cowork — čtení obrázků, extrakce dat, aktualizace HTML |
| Frontend | Vanilla HTML/CSS/JS, žádné závislosti |
| Mobilní přístup | Safari / Chrome na iPhone (shortcut na domovskou obrazovku) |

**Čas přípravy:** ~5,5 hodiny aktivní práce rozložených do 22 dní (29. 6. – 21. 7. 2026), 13 pracovních bloků, 923 zpráv v konverzaci.
