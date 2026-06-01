# Funkční požadavky systému

Níže jsou rozšířené funkční požadavky se zpřesněnými akceptačními kritérii a poznámkami implementace. Cílem je pokrýt hlavní scénáře použití a podmínky ověřitelnosti.

## Obecné zásady
- **Autentizace:** systém podporuje registraci a přihlášení pro role `Student`, `Firma` a `Administrátor`.
- **Validace:** vstupy z formulářů musí být validovány (povinná pole, velikost nahrávek, formát e-mailu).
- **Bezpečnost:** citlivá data (CV, e-mail) jsou uložena šifrovaně podle standardů.

---

## Studenti (F-ST)

- **F-ST-01 – Vytvoření a úprava profilu (Must have)**
	- Popis: Student může vytvořit a upravit profil obsahující jméno, škola, obor, klíčové dovednosti, jazyky, dostupnost (hodiny/týdně) a krátké bio.
	- Akceptace: Po uložení jsou změny okamžitě viditelné pro studentův účet; pole s chybějícími povinnými hodnotami blokují uložení.

- **F-ST-02 – Nahrání životopisu (Must have)**
	- Popis: Student může nahrát CV (PDF) max. 10 MB; systém ukládá originál a generuje náhled PDF (miniatura).
	- Akceptace: Nahrání proběhne úspěšně, soubor je dostupný ke stažení firmám po studentově souhlasu.

- **F-ST-03 – Vyhledávání nabídek (Must have)**
	- Popis: Fulltextové vyhledávání podle nadpisu, popisu a klíčových slov; nabídky jsou řazeny podle relevance a data vložení.
	- Akceptace: Dotaz vrací relevantní výsledky během 2 sekund při 1000 záznamech v testovací sadě.

- **F-ST-04 – Filtrace nabídek (Must have)**
	- Popis: Filtrování podle lokality (kraj/město), typu (brigáda/praxe/stáž), odměny, oboru, home office, vzdálenost (km) a zkušeností.
	- Akceptace: Kombinace filtrů vrátí správné subsety; UI ukazuje aktivní filtry.

- **F-ST-05 – Rychlá reakce (Must have)**
	- Popis: Tlačítko „Odpovědět“ odešle firmě profil a připojené CV; student může přidat krátkou zprávu.
	- Akceptace: Kliknutí vytvoří záznam reakce spojený s inzerátem; firma obdrží notifikaci a může stáhnout CV.

- **F-ST-06 – Přehled reakcí (Should have)**
	- Popis: Student vidí historii reakcí se stavem (Odesláno, V řízení, Pozváno, Přijat, Zamítnut) a možnost zrušit reakci.
	- Akceptace: Historie zobrazuje čas, firmu a stav; změna stavu od firmy se promítne do přehledu.

- **F-ST-07 – Uložené vyhledávání a upozornění (Should have)**
	- Popis: Student může uložit vyhledávací dotaz a dostávat periodické e-mailové upozornění na nové relevantní nabídky.

---

## Firmy (F-FI)

- **F-FI-01 – Registrace a firemní profil (Must have)**
	- Popis: Firma vytvoří účet, vyplní název, IČ (volitelně), logo, web, popis a adresu; změny schvalovány administrátorem podle pravidel.

- **F-FI-02 – Tvorba a správa inzerátů (Must have)**
	- Popis: Formulář tvorby inzerátu obsahuje název, obor, typ úvazku, plat/odměnu, lokalitu, popis, kontaktní osobu a volitelně požadované dokumenty.
	- Akceptace: Inzerát lze uložit jako koncept, publikovat (pokud je účet schválen) nebo archivovat.

- **F-FI-03 – Správa uchazečů (Must have)**
	- Popis: Firma má seznam reakcí na inzerát s možností filtrovat a označovat uchazeče dle stavu. Lze stáhnout CV a posílat předběžné zprávy.

- **F-FI-04 – Rychlé akce a změna stavu (Must have)**
	- Popis: Změna statusu uchazeče (např. „Pozváno na pohovor“, „Přijat“, „Zamítnut“) a komentáře viditelné pro administrátora.

---

## Komunikace (F-CH)

- **F-CH-01 – Chat mezi studentem a firmou (Must have)**
	- Popis: Textový chat (1:1) připojený k reakci na inzerát; historie dostupná oběma stranám.
	- Akceptace: Zprávy dorazí v reálném čase; uložené chaty lze exportovat administrátorem pro audit.

- **F-CH-02 – Notifikace (Should have)**
	- Popis: Vizuální notifikace v UI a volitelně e-mail / push notifikace při důležitých událostech (nová zpráva, změna stavu uchazeče).

---

## Administrace (F-AD)

- **F-AD-01 – Schvalování firem (Must have)**
	- Popis: Administrátor vidí frontu nových firem, ověří údaje a schválí/ zamítne; neschválené firmy nemohou publikovat inzeráty.

- **F-AD-02 – Moderace a správa účtů (Must have)**
	- Popis: Blokace, smazání účtu, odstraňování inzerátů a přístup k metrikám a auditním záznamům.

- **F-AD-03 – Statistiky a export dat (Should have)**
	- Popis: Dashboard zobrazuje počet aktivních účtů, inzerátů, reakcí a úspěšnost spojení; export CSV pro reporting.

---

## Systém / Společné (F-SYS)

- **F-SYS-01 – Typ registrace (Must have)**
	- Popis: Jasné rozlišení Student vs Firma na registraci; role definují přístupová práva.

- **F-SYS-02 – GDPR a mazání dat (Must have)**
	- Popis: Uživatelské rozhraní umožní požádat o smazání dat; systém provede anonymizaci/odstranění dle zákonných lhůt.

- **F-SYS-03 – Limity a zálohy (Should have)**
	- Popis: Omezení velikosti nahrávek, zálohování dat, a logování pro audit.

---

## Poznámky k implementaci
- Doporučená priorita: postupně dodávat jádro (registrace, inzeráty, reakce, stahování CV, chat) a následně rozšíření (notifikace, statistiky, uložená vyhledávání).
- Testy: pro každou funkci připravit minimálně 2 integrační scénáře a 5 jednotkových testů pro kritické komponenty.

---

Soubor aktualizován automaticky pro potřeby diagramu a exportu SVG.
