# 🎨 ArtGallery - Galleria d'Arte Virtuale Enterprise

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white)
![WebSockets](https://img.shields.io/badge/WebSockets-Real--Time-blueviolet?style=for-the-badge)

ArtGallery è un'applicazione web enterprise che digitalizza il concetto tradizionale di galleria d'arte. Offre una piattaforma completa per la gestione, l'esposizione e la commercializzazione di opere d'arte, eliminando gli intermediari e permettendo agli artisti di raggiungere un pubblico globale.

---

## 🎯 Target Utenti
Il sistema è progettato per rispondere alle esigenze di due categorie principali:
- **Artisti:** Possono creare la propria galleria virtuale, gestire il portfolio ad alta risoluzione e vendere autonomamente le proprie opere.
- **Collezionisti:** Possono scoprire nuovi talenti, esplorare collezioni certificate e partecipare ad aste competitive.

---

## 🚀 Funzionalità Chiave

### 🏛️ Gestione Gallerie & Esposizione
- **Upload High-Res:** Caricamento di opere (dipinti, sculture, fotografie) con gestione avanzata dei metadati.
- **Metadata Rich:** Ogni opera include dettagli su tecnica, data di creazione, dimensioni e background storico.

### 💰 Modelli di Vendita Flessibili
- **Prezzo Fisso:** Per l'acquisto immediato tramite check-out rapido.
- **Aste Online:** Sessioni di vendita competitive con gestione automatizzata del miglior offerente.

### ⚡ Sistema Real-Time (WebSockets)
Le pagine delle aste si aggiornano dinamicamente senza ricaricamento della pagina. Grazie alla tecnologia **WebSocket**, ogni nuova offerta viene trasmessa istantaneamente a tutti gli utenti connessi.

### 🔔 Notifiche Multi-Canale
- **In-App:** Badge e pop-up immediati quando la propria offerta viene superata.
- **Email Transazionali:** Notifiche automatiche via email per scadenze di aste e conferme d'acquisto.

### 💳 Integrazione Pagamenti Sicuri
- Gestione completa del ciclo di vita della transazione.
- **Webhooks:** Utilizzo di webhook per gestire stati di pagamento asincroni (riuscito, fallito, rimborsato) garantendo l'integrità dei dati sul database interno.

---

## 🛠️ Stack Tecnologico & Architettura

L'applicazione è costruita seguendo il pattern **MVC (Model-View-Controller)** per garantire manutenibilità e scalabilità.

| Componente | Tecnologia | Descrizione |
| :--- | :--- | :--- |
| **Frontend** | **Angular** | Gestione dell'interfaccia reattiva, form di pagamento e client WebSocket. |
| **Backend** | **Java / Spring** | Logica di business, gestione delle transazioni e sicurezza. |
| **Data Layer**| **JPA / Hibernate** | Mappatura O/R e gestione della persistenza atomica dei dati. |
| **Real-Time** | **STOMP / WebSockets** | Protocollo per la comunicazione push server-to-client. |
| **Async** | **Webhook API** | Gestione delle notifiche asincrone dal gateway di pagamento. |

---

## 🧠 Logica Tecnica & Sfide Risolte

### Transazionalità e Integrità
In un sistema di aste, l'atomicità è critica. Ho implementato logiche **JPA Transactional** per assicurare che l'inserimento di un'offerta e l'aggiornamento del prezzo corrente avvengano come un'unica operazione indivisibile, prevenendo inconsistenze tra utenti concorrenti.

### Comunicazione Asincrona
L'integrazione del Gateway di pagamento non si limita a una chiamata sincrona. Il sistema è configurato per "ascoltare" i **Webhook** esterni, permettendo al backend di aggiornare lo stato dell'ordine anche se l'utente chiude il browser durante l'elaborazione del pagamento.

---

## 📸 Preview
//da aggiungere
---

## 🔧 Setup & Installazione
1. Clonare la repository.
2. Configurare il database nel file `application.properties` del backend.
3. Eseguire il backend Java.
4. Entrare nella cartella `frontend`, eseguire `npm install` e poi `ng serve`.
---

## 👥 Contributors
Questo progetto è stato realizzato in collaborazione da:
* **[Antoniopio Giurranna](https://github.com/Tonino03)** - Sviluppo logica e integrazione API.
* **[Francesco D'Angelo](https://github.com/Vuot00)** - Sviluppo UI e gestione database.
