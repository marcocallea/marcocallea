<h1 align="center">Marco Callea</h1>
<h3 align="center">AI Security · Cybersecurity · Secure Development — Sicilia, IT</h3>

<br/>

> Laureato in Informatica @ UniCT. Lavoro sulla sicurezza dei sistemi **AI** e delle applicazioni web: studio dove si rompono e costruisco le difese che li tengono insieme.
> Per ogni attacco, la difesa misurata.

---

## Su di me

- Laurea Triennale in Informatica (L-31) — Università di Catania
- Focus: **AI Security · Web Application Security · Penetration Testing**
- Tesi: progettazione di un **framework di hardening** contro il data poisoning, validato su un proof-of-concept reale
- Approccio *offensive to defensive*: capire come si attacca per costruire difese solide
- [callea9marco@outlook.it](mailto:callea9marco@outlook.it) · [LinkedIn](https://it.linkedin.com/in/marco-callea-76596b161) · [TryHackMe](https://tryhackme.com/p/Rusheeerrr)

---

## Progetto principale

### [On-Prem GenAI Security Assessment](https://github.com/marcocallea/onprem-genai-security-assessment)
`Python` `LLM fine-tuning` `RAG` `FastAPI` `OWASP LLM Top 10` `MITRE ATLAS`

Assessment riproducibile di un assistente GenAI on-premise (LLM fine-tunato + RAG + web app), testato sui suoi **tre input non fidati**: documenti, dati di training e identità utente. Per ciascuno, un attacco realistico e la difesa misurata prima e dopo da un eval harness.

- **Prompt injection**: nessun filtro è risolutivo; la difesa efficace è architetturale (dual-LLM a privilegio minimo)
- **Backdoor nel fine-tuning**: invisibile ai test funzionali, neutralizzata validando il dataset prima dell'addestramento
- **Broken access control nel RAG**: leak di dati tra tenant azzerati con autorizzazione al retrieval

---

## Stack

**AI / Security**

![LLM Security](https://img.shields.io/badge/LLM_Security-2dd4bf?style=flat-square&logoColor=white)
![Prompt Injection](https://img.shields.io/badge/Prompt_Injection-2dd4bf?style=flat-square&logoColor=white)
![Data Poisoning](https://img.shields.io/badge/Data_Poisoning-2dd4bf?style=flat-square&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-2596CD?style=flat-square&logo=metasploit&logoColor=white)

**Linguaggi & Framework**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

---

## Altri progetti

### [Dataset Poisoning mediante Applicazioni Web — Tesi di Laurea](https://github.com/marcocallea/loanscore_hardened)
`Python` `FastAPI` `Pydantic` `Defense-in-Depth`

Framework di hardening applicativo a 5 livelli contro il data poisoning indiretto nelle web app, validato su un proof-of-concept bancario (loan risk scoring) contro injection sintetiche, label flipping e data flooding.

### [ReminderBot](https://github.com/marcocallea/ReminderBot)
`Python` `Telegram Bot API`

Bot Telegram per la gestione di promemoria con scheduling e notifiche automatiche. Architettura event-driven, gestione asincrona, integrazione con API esterne. Progetto collaborativo.

---

## Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=marcocallea&show_icons=true&theme=github_dark&hide_border=true&hide_title=true&count_private=true" height="150"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=marcocallea&layout=compact&theme=github_dark&hide_border=true&hide_title=true" height="150"/>
</p>

---

<p align="center">
  <sub>security by design, not by accident.</sub>
</p>
