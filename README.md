# Marco Callea

### Junior Cloud &amp; DevSecOps Engineer · Sicilia, IT

> **AWS Certified Solutions Architect – Associate.** Progetto infrastrutture su AWS con Terraform: container, serverless e security automation, tutto definito come codice.
> Vengo dalla sicurezza delle applicazioni web e dei sistemi AI, e porto quel modo di ragionare dentro l'infrastruttura: privilegio minimo di default, e per ogni affermazione di sicurezza un test che la dimostra.

[![Certificazione](https://img.shields.io/badge/AWS_Certified-Solutions_Architect_Associate-FF9900?style=flat-square&logo=amazonwebservices&logoColor=white)](https://www.credly.com/badges/6db73762-70a0-4368-8dda-475fb43fef5d/public_url)
[![Sito](https://img.shields.io/badge/marcocallea.it-0b1220?style=flat-square)](https://www.marcocallea.it)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://it.linkedin.com/in/marco-callea)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=maildotru&logoColor=white)](mailto:callea9marco@outlook.it)

---

## Infrastrutture

Due architetture production-ready su AWS, interamente in Terraform, ognuna con il proprio caso studio: decisioni, trade-off, modello di sicurezza e costi reali.

### [aws-n8n-infra](https://github.com/marcocallea/aws-n8n-infra) · container

`Terraform` `ECS Fargate` `RDS PostgreSQL` `ALB` `CloudFront` `IAM` `SSM` `checkov`

```
utente → CloudFront → ALB → n8n su ECS Fargate → RDS
                            └── subnet private, nessun accesso da internet
```

Deployment completo di una piattaforma open source di workflow automation, nello scenario in cui le aziende la self-hostano: credenziali e dati restano nel proprio account invece che presso un SaaS.

- Rete multi-AZ con subnet private, database mai esposto a internet, HTTPS via CloudFront
- Catena di security group a privilegio minimo in cui ogni livello autorizza solo il precedente, verificata con test negativi documentati nel repo
- Segreti generati da Terraform e iniettati da SSM Parameter Store, mai presenti nel codice
- Circa 40 risorse in moduli riusabili, ricreabili da zero in dieci minuti con un comando
- CI bloccante con `fmt`, `validate`, `tflint` e `checkov`: zero finding aperti, deviazioni documentate una per una

### [aws-security-watchdog](https://github.com/marcocallea/aws-security-watchdog) · serverless

`Terraform` `Lambda` `EventBridge` `CloudTrail` `DynamoDB` `API Gateway` `SNS` `Python`

```
CloudTrail → EventBridge → Lambda → DynamoDB + SNS → email
                                        ↑
                              API Gateway (auth IAM)
```

Detection in tempo reale degli eventi di sicurezza di un account AWS. CloudTrail registra tutto, ma i log restano in un bucket che nessuno legge finché il danno non è fatto: questo progetto chiude quel divario.

- Quattro regole EventBridge su login root, security group aperti a internet, modifiche IAM e manomissioni di CloudTrail
- Classificazione per severità in una Lambda Python, archiviazione su DynamoDB con TTL, notifica via SNS solo per gli eventi che la meritano
- API HTTP autenticata IAM (SigV4) per interrogare lo storico: senza firma valida risponde 403
- Architettura pay-per-use a costo quasi nullo, pensata per restare sempre attiva
- CI bloccante con security scanning IaC: zero finding aperti

---

## Altri progetti

### [terraform-s3-static-site](https://github.com/marcocallea/terraform-s3-static-site)

`Terraform` `S3` `IAM` `Serverless`

Il sito di un'attività locale, in produzione. Hosting statico su S3 definito interamente in Terraform: nessun server, nessun database, nessun backend da mantenere. Menu, orari e stato aperto/chiuso vengono letti in tempo reale da un foglio di calcolo condiviso, così chi gestisce l'attività aggiorna il foglio e il sito si allinea da solo. Due soli account da proteggere, MFA e permessi least-privilege, costo di esercizio trascurabile.

### [loanscore_hardened](https://github.com/marcocallea/loanscore_hardened) · tesi di laurea

`Python` `FastAPI` `Pydantic` `JWT` `Defense-in-Depth`

Framework di hardening applicativo a cinque livelli contro il data poisoning indiretto nelle web app, costruito a partire da un'analisi sistematica delle vulnerabilità che lo abilitano (tassonomia CWE-1000). Validato su un proof-of-concept bancario di loan risk scoring contro injection sintetiche, label flipping e data flooding.

### [onprem-genai-security-assessment](https://github.com/marcocallea/onprem-genai-security-assessment)

`Python` `RAG` `fine-tuning` `FastAPI` `OWASP LLM Top 10` `MITRE ATLAS`

Assessment riproducibile di un assistente GenAI on-premise, testato sui suoi tre input non fidati: documenti, dati di training e identità utente. Per ciascuno un attacco realistico e la difesa misurata prima e dopo con un eval harness.

- **Prompt injection**: nessun filtro è risolutivo; la difesa efficace è architetturale (dual-LLM a privilegio minimo), che riduce l'esfiltrazione da 3/4 a 0/4 dei vettori testati
- **Backdoor nel fine-tuning**: invisibile ai test funzionali, neutralizzata validando il dataset prima dell'addestramento
- **Broken access control nel RAG**: leak cross-tenant chiuso spostando l'autorizzazione al layer del retrieval

---

## Stack

**Cloud &amp; Infrastructure as Code**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

Servizi usati nei progetti: VPC · ECS Fargate · Lambda · API Gateway · EventBridge · RDS · DynamoDB · S3 · CloudFront · ALB · CloudTrail · CloudWatch · SNS · IAM · KMS · SSM

**Security &amp; Quality**

![checkov](https://img.shields.io/badge/checkov-6C47FF?style=flat-square&logo=prisma&logoColor=white)
![tflint](https://img.shields.io/badge/tflint-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)
![OWASP](https://img.shields.io/badge/OWASP-000000?style=flat-square&logo=owasp&logoColor=white)

**Linguaggi &amp; Framework**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

## In breve

| | |
|---|---|
| **Formazione** | Laurea Triennale in Informatica (L-31), Università degli Studi di Catania |
| **Certificazione** | AWS Solutions Architect – Associate (SAA-C03), agosto 2026 · [verifica su Credly](https://www.credly.com/badges/6db73762-70a0-4368-8dda-475fb43fef5d/public_url) |
| **Cerco** | Prima esperienza come Cloud / DevSecOps Engineer |
| **Dove** | Ragusa e Catania in sede, oppure da remoto |
| **Lingue** | Italiano madrelingua · Inglese B2 |

---

<div align="center">

![Stats](https://github-readme-stats.vercel.app/api?username=marcocallea&show_icons=true&theme=github_dark&hide_border=true&hide_title=true&count_private=true)

*security by design, not by accident.*

</div>
