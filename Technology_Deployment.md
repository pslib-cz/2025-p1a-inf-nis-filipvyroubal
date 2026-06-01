# Technologie a nasazení

## Technologie

- Frontend: HTML, CSS, JavaScript (statická webová stránka, případně framework typu React/Vue pro budoucí rozšíření)
- Backend: Node.js / Python / Java (záleží na výběru, API by mělo být REST nebo GraphQL)
- Databáze: relační databáze (PostgreSQL / MySQL) pro ukládání studentů, firem, inzerátů, reakcí a chatů
- Ukládání souborů: objektové úložiště nebo diskový filesystem pro CV soubory (S3 kompatibilní úložiště nebo cloud storage)
- Autentizace: JWT / OAuth2 pro bezpečné přihlášení a role-based access control
- Notifikace: e-mailová služba (SMTP, SendGrid, Mailgun) a případně push notifikace

## Uživatelské rozhraní

- Responzivní design pro desktop i mobil
- Přístupnost a WCAG 2.1 AA jako součást nefunkčních požadavků

## Nasazení

- Reverzní proxy / load balancer: Nginx, HAProxy nebo cloudová služba
- Aplikační servery: kontejnery (Docker) pro backend i frontend
- Databáze: nasazení v clusteru nebo spravované DB službě
- Zálohování: denní zálohy databáze a záloha uložených souborů
- Monitoring a logování: Prometheus/Grafana, ELK nebo cloudové monitorování
- CI/CD: GitHub Actions / GitLab CI / Jenkins pro automatické testování a nasazení

## Nasazovací scénář

1. Vývoj na lokálním počítači.
2. Push do repozitáře, spuštění CI pipeline.
3. Build a testy aplikace.
4. Deploy do staging prostředí.
5. Po ověření přepnutí do produkce.

## Poznámka

Tento dokument slouží jako doplněk k diagramům a vysvětluje technologické volby a architekturu nasazení.