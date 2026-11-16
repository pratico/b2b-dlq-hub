# B2B DLQ Hub — Fault-Tolerant Webhook & API Dead-Letter Queue Middleware

🇬🇧 / 🇺🇸 **ENGLISH** | [🇮🇹 Vai alla versione in Italiano](#-italiano)

[![Status](https://img.shields.io/badge/Status-Live%20in%20Production%20(Linux%20VPS)-198754?style=flat-square)](https://antoniangeloflore.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-antoniangeloflore.com-0d6efd?style=flat-square)](https://antoniangeloflore.com)
[![Stack](https://img.shields.io/badge/Stack-Node.js%20%7C%20Express%20%7C%20MySQL%20%7C%20PM2-333333?style=flat-square)](https://github.com/pratico)
[![Privacy](https://img.shields.io/badge/Architecture-Idempotent%20%26%20GDPR--Safe-dc3545?style=flat-square)](https://antoniangeloflore.com)

## Product Overview

**B2B DLQ Hub** is a production-grade middleware platform engineered for web agencies, professional firms, and SMEs that rely on multiple disconnected software systems. Acting as a centralized reliability hub for operational data transfers—orders, customer inquiries, leads, and notifications—it guarantees that **no payload is ever lost**, even when downstream APIs or third-party endpoints experience downtime.

Deployed and actively running in a **Linux VPS production environment**, it is designed for businesses that cannot afford operational interruptions: every event entering the hub is tracked, validated, and delivered to its destination—guaranteed.

## The Problem Solved

In day-to-day operations across e-commerce platforms, ERPs, CRMs, booking engines, and invoicing software, fragile point-to-point integrations create severe bottlenecks:

- **Wasted engineering & staff time:** Repetitive manual exports, double data entry, and daily cross-checks between disconnected tools.
- **Human transcription errors:** Miskeyed orders, incomplete lead records, and duplicate entries.
- **Operational bottlenecks during outages:** Whenever an external API goes offline, times out, or undergoes maintenance, webhooks fail silently and staff must manually reconstruct and replay lost transactions.
- **Direct revenue loss:** A dropped e-commerce order or missed B2B lead translates immediately into lost revenue and damaged client trust.

**B2B DLQ Hub** eliminates these failures permanently: transactions that fail on the first attempt are never discarded. Instead, they are safely persisted in a **Dead-Letter Queue (DLQ)** and automatically replayed once the target system recovers—zero data loss, zero manual intervention.

## Operator Workflow

The operational lifecycle is engineered for complete transparency and unattended reliability:

1. **Event Origin** — A business event occurs in the source system (e.g., a new e-commerce order, booking, contact request, or CRM update).
2. **Centralized Ingestion & Validation** — The payload enters the hub, where it is validated, assigned an idempotency key, and persisted as a tracked delivery job.
3. **Automated Real-Time Routing** — The hub resolves the target endpoint and dispatches the payload immediately.
4. **Intelligent Fault Recovery (DLQ & Backoff)** — If the destination endpoint is offline, rate-limited, or returning HTTP 5xx errors, the job is moved to the persistent Dead-Letter Queue and retried automatically using progressive backoff intervals to avoid overwhelming recovering services.
5. **Sequential Completion & Full Audit Trail** — As soon as the target service comes back online, queued jobs are replayed in order. Operators have full visibility into what was delivered, what is pending, and exact error diagnostics.
6. **End Result** — All connected systems remain synchronized automatically without manual recovery work.

## Main Features & Operational Benefits (ROI)

| Functionality | Operational Advantage |
|---|---|
| **Centralized Data Routing Hub** | Single control plane for all data flows across disparate business applications. |
| **Persistent Dead-Letter Queue (DLQ)** | Zero lost orders or leads—even during prolonged third-party API outages. |
| **Automated Idempotent Replay** | Self-healing delivery pipeline that recovers automatically without duplicate records. |
| **End-to-End Audit & Diagnostics** | Full visibility into delivery status, timestamps, and HTTP error logs for every payload. |
| **Elimination of Manual Re-Entry** | Saves hours of manual reconciliation and emergency firefighting every week. |
| **Continuous Business Continuity** | Your operations keep running smoothly even when external vendors experience downtime. |

**Immediate ROI:** Eliminating lost orders and hours spent manually reconciling failed webhooks delivers measurable financial payback within the first weeks of deployment, backed by a lightweight, low-maintenance Linux VPS footprint.

## High-Level Architecture & Production Stack

The platform runs on a battle-tested, high-availability backend stack:

- **Node.js / Express:** Event-driven, low-latency backend runtime built for non-blocking asynchronous I/O and high-throughput webhook ingestion.
- **MySQL:** ACID-compliant relational persistence ensuring zero queue loss across restarts and full transactional auditability.
- **Bootstrap 5:** Clean, responsive operational dashboard accessible from any device with zero frontend bloat.
- **Linux VPS Production Runtime (Nginx + PM2):** Deployed in production on Linux with process supervision, automatic restarts, and reverse-proxy security.

## Confidentiality Notice & B2B Licensing

🔒 **Proprietary Software Asset (All Rights Reserved):** This repository serves as a functional and architectural showcase within the Professional Portfolio ([https://antoniangeloflore.com](https://antoniangeloflore.com)). For operational security and NDA compliance, the source code and internal production configurations are not publicly exposed.

🤝 **Webhook Stabilization & White-Label Licensing:** Available for custom API/webhook resilience integrations, white-label agency licensing, and asynchronous B2B technical consultations (zero calls required). Watch live technical demos on [antoniangeloflore.com](https://antoniangeloflore.com) or connect via [LinkedIn](https://www.linkedin.com/in/antoniangeloflore/).

---

<a name="-italiano"></a>
## 🇮🇹 ITALIANO

# B2B DLQ Hub — Middleware Asincrono & Dead-Letter Queue per Flussi API/Webhook

[![Stato](https://img.shields.io/badge/Stato-Attivo%20in%20Produzione%20(Linux%20VPS)-198754?style=flat-square)](https://antoniangeloflore.com)

## Panoramica del Prodotto

**B2B DLQ Hub** è una piattaforma middleware progettata per agenzie web, studi professionali e PMI che utilizzano più software gestionali non comunicanti tra loro. Il sistema funge da hub centralizzato per il trasferimento affidabile dei dati operativi — ordini, richieste clienti, contatti, notifiche — tra applicazioni diverse, garantendo che **nessuna informazione venga mai persa**, anche quando uno dei sistemi coinvolti è temporaneamente non raggiungibile.

Attivo in **produzione su infrastruttura Linux VPS**, il prodotto è pensato per realtà che non dispongono di un reparto IT interno ma che, allo stesso tempo, non possono permettersi interruzioni operative: ogni dato che entra nel sistema arriva a destinazione, sempre.

## Il Problema Risolto

Nella gestione quotidiana di un'azienda che si affida a più strumenti digitali (gestionali, CRM, piattaforme di prenotazione, e-commerce, sistemi di fatturazione), i dati vengono spesso spostati manualmente da un sistema all'altro. Questo comporta:

- **Perdite di tempo:** copia-incolla ripetitivi, doppie registrazioni, controlli manuali di coerenza tra sistemi.
- **Errori umani:** ordini trascritti male, contatti incompleti, dati duplicati o mancanti.
- **Colli di bottiglia operativi:** quando un servizio esterno è offline o in manutenzione, le operazioni si bloccano e qualcuno deve ricordarsi di "rifare a mano" ciò che non è andato a buon fine.
- **Perdita di dati critici:** un ordine o una richiesta cliente che non arriva a destinazione significa fatturato perso e insoddisfazione.

**B2B DLQ Hub** elimina definitivamente questi problemi: le operazioni che non riescono al primo tentativo non vengono scartate, ma messe in attesa in modo sicuro e completate automaticamente appena il sistema di destinazione torna disponibile. Zero perdite, zero interventi manuali.

## Come Funziona (Flusso Operativo Utente)

Il flusso operativo è pensato per essere semplice e trasparente per l'utente finale:

1. **Origine del dato:** un evento aziendale si verifica nel software di partenza — ad esempio un nuovo ordine, una prenotazione, una richiesta di contatto o un aggiornamento anagrafico.
2. **Acquisizione centralizzata:** l'informazione viene inviata all'hub, che la riceve, la valida e la registra come operazione da inoltrare verso il sistema di destinazione corretto.
3. **Instradamento automatico:** l'hub determina autonomamente quale software deve ricevere il dato e lo inoltra in tempo reale.
4. **Gestione intelligente dei guasti:** se il sistema di destinazione è offline, sovraccarico o in manutenzione, l'operazione non viene persa: viene messa in coda di sicurezza (Dead-Letter Queue) e ritentata automaticamente con idempotenza e ripresa progressiva, evitando di sovraccaricare ulteriormente il servizio in difficoltà.
5. **Completamento e tracciabilità:** appena il servizio di destinazione torna operativo, tutte le operazioni in attesa vengono completate automaticamente nell'ordine corretto. Ogni operazione risulta tracciabile: l'utente può sempre sapere cosa è stato consegnato, cosa è in attesa e quando è stato completato.
6. **Risultato finale:** i dati sono sincronizzati tra tutti i sistemi coinvolti, senza che nessuno dell'azienda debba intervenire manualmente.

## Funzionalità Principali & Vantaggi Operativi (ROI)

| Funzionalità | Vantaggio Operativo |
|---|---|
| **Hub centralizzato di instradamento dati** | Un unico punto di controllo per tutti i flussi tra i software aziendali. |
| **Coda di sicurezza per operazioni non riuscite (DLQ)** | Nessun ordine o contatto perso, mai — nemmeno durante i guasti dei servizi esterni. |
| **Recupero e completamento automatici** | Zero interventi manuali: il sistema si riprende da solo dopo un'interruzione. |
| **Tracciabilità delle operazioni** | Controllo totale: sempre possibile verificare lo stato di ogni trasferimento. |
| **Riduzione del lavoro manuale** | Ore di copia-incolla e verifiche eliminate ogni settimana. |
| **Affidabilità operativa continua** | L'attività aziendale non si ferma quando un fornitore di servizi ha un problema tecnico. |

**ROI immediato:** la riduzione degli errori manuali e delle ore perse in trasferimenti ripetitivi si traduce in un ritorno economico misurabile fin dalle prime settimane di utilizzo, con un costo di gestione minimo grazie all'automazione completa del ciclo operativo.

## Tecnologie Utilizzate (Ad Alto Livello)

La piattaforma è costruita su uno stack tecnologico maturo e collaudato:

- **Node.js / Express:** runtime e framework backend di riferimento per applicazioni ad alta affidabilità e bassa latenza, ideali per gestire flussi di dati continui e operazioni asincrone.
- **MySQL:** database relazionale di standard industriale, garanzia di integrità e durabilità dei dati nel tempo.
- **Bootstrap 5:** interfaccia utente moderna, responsive e accessibile da qualsiasi dispositivo, senza dipendenze superflue.
- **Infrastruttura Linux VPS in Produzione (Nginx + PM2):** esecuzione continua 24/7 con supervisione dei processi e riavvio automatico.

Questa combinazione garantisce stabilità operativa, prestazioni elevate e manutenibilità nel lungo periodo — le caratteristiche essenziali per un sistema su cui un'azienda fa affidamento ogni giorno.

## Nota di Riservatezza & Collaborazioni B2B

🔒 **Asset Software Proprietario (Tutti i diritti riservati):** Questo repository ha finalità di presentazione funzionale e architetturale per il Portfolio Professionale ([https://antoniangeloflore.com](https://antoniangeloflore.com)). Per ragioni di sicurezza operativa e accordi di riservatezza (NDA), il codice sorgente e le specifiche infrastrutturali non sono esposti pubblicamente.

🤝 **Messa in Sicurezza Webhook & Licensing White-Label:** Disponibile per integrazioni B2B su misura, licenze White-Label per agenzie e consulenze tecniche asincrone (zero call). Demo video su [antoniangeloflore.com](https://antoniangeloflore.com) o contatti su [LinkedIn](https://www.linkedin.com/in/antoniangeloflore/).
