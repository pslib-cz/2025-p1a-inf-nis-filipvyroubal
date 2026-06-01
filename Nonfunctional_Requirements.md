# Nefunkční požadavky systému

Níže jsou shrnuty nefunkční požadavky (kvalitativní atributy), jejich cíle a akceptační kritéria.

## Výkon a škálovatelnost
- **NF-PERF-01 – Odezva aplikace (Must have):** 90 % dotazů na vyhledávání musí mít dobu odezvy < 2 s při zátěži 1000 současných uživatelů.
- **NF-PERF-02 – Škálovatelnost (Should have):** Systém musí být horizontálně škálovatelný pro zpracování nárůstu uživatelů bez významné degradace výkonu.

## Dostupnost a spolehlivost
- **NF-AV-01 – Dostupnost (Must have):** Cílová dostupnost služeb 99.5 % za měsíc.
- **NF-REC-01 – Obnova po chybě (Should have):** Systém musí mít obnovu z poslední plné zálohy do 2 hodin.

## Bezpečnost a ochrana osobních údajů
- **NF-SEC-01 – Šifrování (Must have):** Všechna citlivá data v klidu a při přenosu musí být šifrována (TLS pro přenos, AES-256 pro uložení).
- **NF-SEC-02 – Autentizace a autorizace (Must have):** Role-based access control pro studenty, firmy a administrátory; podpora silných hesel a resetu hesla.
- **NF-PRIV-01 – GDPR (Must have):** Dodržení požadavků na ochranu osobních údajů a auditovatelné mazání dat na požádání.

## Údržba a provoz
- **NF-MNT-01 – Monitoring a logování (Should have):** Služby musí zaznamenávat metriku výkonu, chyby a bezpečnostní události; logy uchovávat 90 dní.
- **NF-MNT-02 – Automatizace nasazení (Should have):** CI/CD pipeline pro automatické buildy a nasazení s rollback možností.

## Uživatelská použitelnost a přístupnost
- **NF-UX-01 – Dostupnost (Should have):** Aplikace by měla splňovat základní zásady přístupnosti WCAG 2.1 AA pro klíčové stránky (registrace, inzerát, reakce).
- **NF-LOC-01 – Lokalizace (Should have):** Podpora českého a anglického jazyka v UI.

## Data a zálohování
- **NF-BKP-01 – Zálohování (Must have):** Denní zálohy databáze s retenční politikou 30 dní.
- **NF-Retention-01 – Retenční politika (Should have):** Definovat dobu uchovávání osobních údajů a anonymizaci po uplynutí lhůty.

## Testovatelnost a metriky
- **NF-TST-01 – Metody testování (Should have):** Automatizované integrační a zátěžové testy pokrývající kritické scénáře.
- **NF-METR-01 – Telemetrie (Should have):** Implementovat telemetrii pro sledování použití funkcí a chyb.

---

Poznámka: Tyto nefunkční požadavky jsou navrženy tak, aby sloužily jako doplněk k funkčním požadavkům a poskytly jasná akceptační kritéria pro vývoj a testování.
