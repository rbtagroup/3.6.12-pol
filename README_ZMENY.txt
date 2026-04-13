RB TAXI – Výčetka 3.6.9 mobile compact return

Změny oproti 3.6.7:
- na mobilu je skrytý horní přehled (Účtované km / KM smluvní / Netto po přístavném / Rozdíl vs minimum / stavová hláška)
- na mobilu zůstává kompaktní verze výčetky z 3.6.7
- spodní dashboard je na mobilu skrytý
- zachováno: celé Kč bez desetinných míst
- zachováno: bez textu Ponechte prázdné
- nová cache verze service workeru

Audit opravy 3.6.10:
- export knihovny html2canvas a jsPDF jsou lokálně ve vendor/ a v offline cache
- opraveno čtení nastavení: provize musí být 1–100 %, fixy mohou být i 0 Kč
- finanční pole mají min/step/inputmode pro mobilní zadávání
- přidána kontrola, že smluvní km nesmí být vyšší než najeté km
- doplněno vysvětlení Přístavného: vyjímá se z provize, ale zůstává k odevzdání
- doplněna základní PWA metadata a lepší ovládání dialogu nastavení
- přidán spustitelný výpočetní self-test: node vypocet-selftest.js

Opravy 3.6.11:
- odstraněn CSS color-mix z placeholderů kvůli kompatibilitě s html2canvas exportem
- validační a exportní chyby se ukazují v hlášce v aplikaci místo alertů
- tlačítka exportu se během přípravy výstupu dočasně vypnou
- nová cache verze service workeru pro načtení opraveného exportu

Vzhled 3.6.12:
- kompaktnější formulář: nižší pole, tlačítka, menší paddingy a radiusy
- zmenšený header, logo a hlavní karty
- zjemněné stíny a snížená výška spodního dashboardu
- mobilní ovládání ponecháno nad cca 44 px pro pohodlné klepnutí
- v hlavičce aplikace se zobrazuje aktuální verze


Provozní nástroje 3.6.14:
- exportní knihovny se před PDF/sdílením umí samy dočíst z vendor/ a případně z CDN fallbacku
- v nastavení je tlačítko Otestovat export
- v nastavení je tlačítko Načíst nejnovější verzi, které vymaže aplikační cache a obnoví stránku
- aplikace hlásí dostupnou novou verzi service workeru a nabídne její načtení
- přidána volitelná kontrola Hotovost u sebe proti částce k odevzdání


Vzhled 3.6.15:
- přidán čistší kompaktní vizuální režim přes CSS vrstvu
- ubrané skleněné efekty, radiální dekorace, silné stíny a přebytečný glow
- méně rušivé ikony u formulářových labelů
- výraznější pracovní výsledek ve finální výčetce
- na mobilu jsou akční tlačítka lepkavě dole, aby nebylo nutné rolovat zpět


UX tok 3.6.16:
- rozepsaná směna se automaticky ukládá a po návratu obnoví
- po výpočtu lze rozepsaná data ručně vymazat z hlášky
- kontrola hotovosti ukazuje rozpad Má být / U sebe / Rozdíl
- validační chyby se zobrazují přímo pod konkrétními poli


Hotová výčetka 3.6.17:
- po výpočtu se formulář sbalí a zůstane čistá hotová výčetka s akcemi
- přidáno tlačítko Upravit údaje pro návrat k formuláři
- výčetka zůstává jako uzamčený snapshot; po změně vstupů se označí jako zastaralá
- export zastaralého snapshotu je blokovaný, dokud se výčetka znovu nepřepočítá

Logo 3.6.18:
- nahrazeny ikony aplikace novým logem RB TAXI
- změna se promítá do hlavičky, exportu výčetky, manifestu i Apple/PWA ikony
- navýšena cache service workeru, aby se po obnovení načetl nový obrázek

Vizuální polish 3.6.19:
- logo v hlavičce a výčetce je kulaté a líp sedí na nové RB TAXI ikoně
- akce po výpočtu mají jasnější prioritu: sdílení je hlavní, úpravy jsou klidnější
- mobilní rozložení má menší mezery, aby se méně scrollovalo
- stav hotové a zastaralé výčetky je výraznější přímo v reportu
