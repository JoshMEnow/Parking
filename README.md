# 🅿️ Parking Report

Systém pro sledování rezervací firemního parkování pro dva uživatele s mobilním přístupem.

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
- Záložky aut: Vše / Mini Cooper / Audi Q7 / Kodiaq
- Záložky času: Nadcházející / Historie / Vše
- Duplicity označeny oranžově ⚠️
- Funguje jako webová zkratka na iPhone

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

## Auta a barvy

| Auto | Barva |
|---|---|
| 🚙 Mini Cooper | zelená |
| 🚗 Audi Q7 | modrá |
| 🚐 Kodiaq | hnědá |

## Lokace

| Kód | Barva pruhu |
|---|---|
| SHQ0 | modrá |
| NHQ0 | oranžová |
| HHQ0 / Bazén | fialová |
