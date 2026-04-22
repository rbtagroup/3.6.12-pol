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
- přidána volitelná kontrola Hotovost u sebe proti očekávané hotovosti


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

Světlý režim 3.6.20:
- zvýšen kontrast hlavních textů, hodnot a popisků
- pole formuláře mají čitelnější okraje, bílé pozadí a výraznější focus
- karty a stavové boxy ve světlém režimu mají pevnější hranice
- výsledek výčetky je ve světlém režimu čitelnější jako čistý doklad

Dýško 3.6.21:
- přebytek v poli Hotovost u sebe se zobrazuje jako dýško
- dýško je jen informační rozdíl hotovosti, nemění výplatu ani částku k odevzdání
- chybějící hotovost zůstává červeně jako kontrolní varování

Hotovost u sebe 3.6.22:
- kontrola Hotovost u sebe se počítá proti hotovosti včetně výplaty řidiče
- očekávaná hotovost u sebe = K odevzdání celkem + výplata řidiče
- náklady a nehotovost zůstávají odečtené; dýško je jen přebytek nad očekávanou hotovost

Celá hotovost 3.6.23:
- pole přejmenováno na Celá hotovost u sebe, aby bylo jasné, že jde o hotovost před oddělením výplaty
- nápověda vysvětluje zadání celé hotovosti u sebe
- ve finální výčetce se dýško / chybějící hotovost ukáže jen při nenulovém rozdílu

Audit balík 3.6.24:
- doplněny testy pro celou hotovost u sebe, dýško a chybějící hotovost
- přidána iOS nápověda pro instalaci přes Safari a stav Online/Offline
- sdílení obrázku jasně rozlišuje skutečné sdílení a fallback stažení souboru
- modal nastavení má lepší focus trap a validační chyby mají aria vazby
- manifest doplněn o jazyk, kategorie, orientaci, shortcut a screenshoty pro širší PWA kompatibilitu


Premium polish 3.6.25:
- upraven finální výstup výčetky jako výraznější hotový doklad
- doplněn akční panel pod výčetkou pro sdílení a PDF
- zmenšena a sjednocena pole, tlačítka a karty pro kompaktnější profesionální vzhled
- zklidněn header, statusy a světlý režim pro lepší čitelnost
- zkráceny vybrané hlášky a texty ve výstupu


Cache refresh 3.6.26:
- přidána verze do URL hlavních CSS/JS/vendor souborů, aby mobil nenačítal starou kopii
- service worker pro HTML, CSS, JS, manifest a exportní knihovny používá network-first strategii
- doplněny no-cache meta tagy v HTML jako pojistka pro mobilní prohlížeče


iOS stability 3.6.27:
- přidáno větší odsazení obsahu od krajů na mobilu a respektování safe-area
- inputy/selecty mají na mobilu 16px kvůli omezení iOS zoomování při fokusu
- doplněna ochrana proti vodorovnému „plavání“ layoutu na iOS


No edge slider 3.6.28:
- odstraněny záporné mobilní okraje u spodních akčních lišt, aby nic neutíkalo doprava
- skryty systémové scrollbary aplikace, pokud je prohlížeč vykreslí na hraně obsahu


Stable mobile 3.6.28:
- verze označena jako stabilní mobilní build po ověření na iPhonu
- doporučený instalační postup:
  iPhone: otevřít v Safari, klepnout na Sdílet a zvolit Přidat na plochu
  Android: otevřít v Chrome a zvolit Instalovat aplikaci nebo Přidat na plochu
  při staré verzi: v aplikaci otevřít Nastavení a dát Načíst nejnovější verzi
- další ladění dělat až po nové záloze této stabilní verze


Production hardening:
- cache a service worker reset jsou omezeny jen na tuto aplikaci, aby nezasahovaly jiné GitHub Pages aplikace na stejné doméně


Keyboard safe 3.6.29:
- Pridana ochrana proti prekryvani formulare mobilni klavesnici pres VisualViewport.
- Pri psani se aktivni pole automaticky posune do viditelne casti obrazovky.
- Spodni akcni panel se pri otevrene klavesnici docasne vrati do toku stranky, aby neprekryval pole na iOS/Androidu.


Keyboard lite 3.6.30:
- Zjemnena obsluha mobilni klavesnice, aby se pri psani nespoustel zbytecny plynuly scroll.
- Stav klavesnice se prepocitava pres requestAnimationFrame a zapisuje se jen pri skutecne zmene.
- Aktivni pole se posune jen kdyz je mimo bezpecnou viditelnou oblast.


Android keyboard 3.6.31:
- Detekce klavesnice uz nepocita jen rozdil window.innerHeight a visualViewport.height, protoze Android Chrome casto zmensi obe hodnoty zaroven.
- Pridana baseline vyska viewportu pred fokusem pole, diky ktere se keyboard-open spolehlive zapne i na Androidu.
- Po zmene orientace se baseline prepocita, aby nevznikal falesny keyboard stav.


Android steady 3.6.32:
- Pro Android se pri otevrene klavesnici nepouziva promenlivy keyboard inset, protoze Chrome uz viewport casto zmensuje sam.
- Pridana trida android-keyboard a pevna spodni rezerva, aby obsah pri psani neposkakoval podle kazde zmeny vysky klavesnice nebo adresniho radku.
- iOS vetev zustava dynamicka, protoze tam se chovani v realnem testu potvrdilo jako spravne.


Android native scroll 3.6.33:
- Na Androidu je vypnuty dodatecny JS scroll aktivniho pole, aby se nebil s nativnim posunem Chrome klavesnice.
- iOS vetev zustava beze zmeny, protoze tam keyboard guard funguje spravne.
- Android si posun pole resi nativne, aplikace jen drzi stabilni keyboard-open layout.


Android minimal scroll 3.6.34:
- Android uz neni bez JS posunu uplne; po otevreni klavesnice se provede jen male jednorazove dorovnani, pokud je aktivni pole porad mimo viditelnou cast.
- Nepouziva se centrovani pole pres scrollIntoView, aby se nevratilo dvojite poskakovani.
- iOS vetev zustava beze zmeny.


Clean report 3.6.35:
- Ve vysledne vycetce je schovany radek Minimum podle km v sekci Kilometry.
- Ve vysledne vycetce a sdilenem exportu je schovana samostatna polozka Nehotovost.
- Vypocty zustavaji beze zmeny, meni se pouze zobrazeni hotove vycetky.


Visual contrast 3.6.36:
- Pridan citelnejsi font Manrope pro bezny text, cisla zustavaji stabilni diky tabular-nums.
- Jemne zesileny ramecky bublin, vstupu a vysledkove vycetky v tmavem i svetlem rezimu.
- Zvyrazneny focus stav inputu bez zmeny layoutu nebo vypoctu.


Luxury surface 3.6.37:
- Pridana premium vizualni vrstva black lacquer + champagne gold s vyraznejsimi ramecky a hlubsimi materialy.
- Zvyraznena hotova vycetka, primarni tlacitko, aktivni pole a karty bez zmeny vypoctu.
- Zachovana pracovni struktura aplikace, pouze posilena citelnost a wow efekt.


Wow report 3.6.38:
- Hotova vycetka dostala premium certifikatovy moment: silnejsi hlavicku, vetsi logo a vyraznejsi kartu K odevzdani.
- Po vypoctu se vysledek zobrazi kratkou reveal animaci a jemnym svetelnym prejezdem pres hlavni castku.
- Vypocty a vstupni formular zustavaji beze zmeny.


Refined luxury 3.6.39:
- Zmensena a zklidnena hotova vycetka po wow experimentu.
- Odebrany modry dashboardovy dojem, hlavni report je vic graphite/champagne a mene barevny.
- Animace je jemnejsi a bez svetelneho prejezdu pres castku.


Navy compact 3.6.40:
- Vycetka je vracena bliz k RB navy/gold smeru misto graphite luxury experimentu.
- Zmensena hlavicka, logo, hlavni castka, karty i radky ve vysledku.
- Zjednoduseny kontrast a barvy, aby hotova vycetka nepusobila prekombinovane.


Navy readable 3.6.41:
- Radky ve vysledne vycetce jsou na mobilu zpet v jedne bublina / jeden radek.
- Zesileny kontrast textu a hodnot, mene graphite dojmu, vice NAVY pozadi.
- Hodnoty a popisky jsou tucnejsi pro lepsi citelnost.


Unified RB style 3.6.42:
- Sjednocen vzhled cele aplikace do jednoho RB ink/gold stylu.
- Potlaceny vyrazny modry/graphite experiment, karty, vstupy i hotova vycetka maji jednotne materialy.
- Radky ve vycetce zustavaji jedna bublina / jeden radek, text je kontrastnejsi.


Full audit 3.6.43:
- Sjednocen export obrazku i PDF s aktualnim RB ink/gold stylem aplikace.
- PWA theme/background barvy jsou sladene s tmavym RB stylem, bez stare modre.
- Formularova pole maji name/autocomplete a validace po chybe presune pozornost na prvni problem.
- Hotove vycetky se ukladaji do historie poslednich 10 smen v tomto zarizeni.
- Rozepsana smena je oddelena od hotove vycetky; po vypoctu se uklada hotovy zaznam do historie.
- Pridan kontrolni checklist pred odeslanim a PDF pouziva samostatny sirsi exportni layout.


Simplified flow 3.6.44:
- Odstranena sekce Kontrola pred odeslanim, protoze zdvojovala hotovou vycetku.
- Odstranena historie poslednich vycetek vcetne ukladani hotovych zaznamu.
- Pridan hapticky fallback pres navigator.vibrate pro podporovane prohlizece; na iOS web/PWA zustava bezpecny no-op, protoze Safari nativni haptiku webum neposkytuje.
