# Marco Callea

### Cloud Engineering & Security · Sicilia, IT

> Laureato in Informatica @ UniCT, AWS Certified Solutions Architect Associate.
> Progetto infrastrutture su AWS con Terraform. Vengo dalla sicurezza delle applicazioni web e dei sistemi AI, e porto quel modo di ragionare dentro l'infrastruttura: per ogni attacco, la difesa misurata.

---

## Su di me

- Laurea Triennale in Informatica (L-31), Università di Catania
- **AWS Certified Solutions Architect Associate** (SAA-C03), agosto 2026 · [verifica su Credly](https://www.credly.com/badges/6db73762-70a0-4368-8dda-475fb43fef5d/public_url)
- Focus: Cloud engineering, Infrastructure as Code, cloud security
- Approccio *offensive to defensive*: capire come si attacca per progettare difese che reggono
- [marcocallea.it](https://www.marcocallea.it) · [callea9marco@outlook.it](mailto:callea9marco@outlook.it) · [LinkedIn](https://it.linkedin.com/in/marco-callea) · [TryHackMe](https://tryhackme.com/p/Rusheeerrr)

---

## Progetti

### [Sito vetrina serverless su AWS](https://github.com/marcocallea/terraform-s3-static-site)

`Terraform` `AWS S3` `IAM` `Serverless`

Infrastruttura per il sito di una piccola attività locale, definita interamente in Terraform: hosting statico su S3, nessun server, nessun database, nessun backend.

- Contenuti aggiornabili senza deploy: menu, orari e stato aperto/chiuso letti in tempo reale da un foglio di calcolo condiviso, così chi gestisce l'attività aggiorna il foglio e il sito si allinea da solo
- Superficie di attacco minima by design: nessun server o database da proteggere, due soli account protetti con MFA e permessi least-privilege
- Costo di esercizio trascurabile, vincolo reale per una piccola attività

### [On-Prem GenAI Security Assessment](https://github.com/marcocallea/onprem-genai-security-assessment)

`Python` `LLM fine-tuning` `RAG` `FastAPI` `OWASP LLM Top 10` `MITRE ATLAS`

Assessment riproducibile di un assistente GenAI on-premise (LLM fine-tunato, layer RAG, web app), testato sui suoi tre input non fidati: documenti, dati di training e identità utente. Per ciascuno un attacco realistico e la difesa misurata prima e dopo con un eval harness.

- **Prompt injection**: nessun filtro è risolutivo; la difesa efficace è architetturale (dual-LLM a privilegio minimo), che riduce l'esfiltrazione da 3/4 a 0/4 dei vettori testati
- **Backdoor nel fine-tuning**: invisibile ai test funzionali, neutralizzata validando il dataset prima dell'addestramento
- **Broken access control nel RAG**: leak cross-tenant chiuso spostando l'autorizzazione al layer del retrieval

### [Dataset Poisoning mediante Applicazioni Web](https://github.com/marcocallea/loanscore_hardened)

`Python` `FastAPI` `Pydantic` `Defense-in-Depth`

Tesi di laurea. Framework di hardening applicativo a 5 livelli contro il data poisoning indiretto nelle web app, validato su un proof-of-concept bancario di loan risk scoring contro injection sintetiche, label flipping e data flooding.

### [ReminderBot](https://github.com/marcocallea/ReminderBot)

`Python` `Telegram Bot API`

Bot Telegram per la gestione di promemoria con scheduling e notifiche automatiche. Architettura event-driven, gestione asincrona, integrazione con API esterne. Progetto collaborativo.

---

## Stack

**Cloud & Infrastructure as Code**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

**Security**

![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-2596CD?style=flat-square&logo=metasploit&logoColor=white)
![OWASP](https://img.shields.io/badge/OWASP-000000?style=flat-square&logo=owasp&logoColor=white)

**Linguaggi & Framework**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

## Stats

![Stats](https://github-readme-stats.vercel.app/api?username=marcocallea&show_icons=true&theme=github_dark&hide_border=true&hide_title=true&count_private=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=marcocallea&layout=compact&theme=github_dark&hide_border=true&hide_title=true)

---

*security by design, not by accident.*
