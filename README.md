# SIW Federazione Sportiva

![Logo SIW](siw-federazione/src/main/resources/static/images/logo-siw.png)

## 📋 Descrizione del Progetto

**SIW Federazione** è un'applicazione web sviluppata per la gestione di una federazione sportiva. Il sistema permette la gestione centralizzata di squadre, presidenti e giocatori, offrendo funzionalità differenziate in base al ruolo dell'utente (Amministratore, Presidente, Utente registrato o Visitatore).

Il progetto è stato realizzato come parte del corso di **Sistemi Informativi su Web (SIW)** presso l'Università Roma Tre.

---

## 🚀 Obiettivi

L'obiettivo principale è fornire una piattaforma digitale per:
*   **Gestire il tesseramento** dei giocatori nelle varie squadre.
*   **Amministrare le società sportive**, assegnando presidenti e gestendo i dettagli delle squadre.
*   **Consultazione pubblica** dei dati relativi alle squadre e ai giocatori tesserati.

---

## 🛠️ Tecnologie Utilizzate

Il progetto è basato su un'architettura **MVC (Model-View-Controller)** e utilizza le seguenti tecnologie:

### Backend
*   **Java 17**: Linguaggio di programmazione principale.
*   **Spring Boot 3.0.6**: Framework per lo sviluppo rapido di applicazioni.
*   **Spring Data JPA**: Per la persistenza dei dati e l'astrazione del database.
*   **Spring Security**: Per la gestione dell'autenticazione e delle autorizzazioni basate sui ruoli.

### Frontend
*   **Thymeleaf**: Template engine server-side per la generazione dinamica delle pagine HTML.
*   **HTML5 & CSS3**: Per la struttura e lo stile delle pagine (fogli di stile personalizzati in `static/css`).

### Database
*   **PostgreSQL**: Database relazionale per la memorizzazione persistente dei dati.

### Build & Dependency Management
*   **Maven**: Per la gestione delle dipendenze e il ciclo di vita del progetto.

---

## 👤 Ruoli e Funzionalità

Il sistema prevede diversi livelli di accesso:

### 1. Utente Non Registrato (Guest)
*   Visualizzazione dell'elenco delle squadre.
*   Visualizzazione dei dettagli di una squadra e dei suoi giocatori.
*   Accesso alle pagine di Login e Registrazione.

### 2. Utente Registrato
*   Accesso all'area riservata.
*   Visualizzazione di contenuti dedicati.

### 3. Presidente di Squadra
*   **Gestione Squadra**: Modifica dei dati della propria squadra.
*   **Campagna Acquisti**: Tesseramento di nuovi giocatori.
*   **Svincolo**: Rimozione di giocatori dalla rosa.

### 4. Amministratore (Admin)
*   **Gestione Totale**: Creazione e modifica di squadre.
*   **Gestione Presidenti**: Creazione di nuovi account presidente e assegnazione di un presidente a una squadra specifica.
*   **Gestione Giocatori**: Inserimento di nuovi giocatori nel sistema.

---

## ⚙️ Configurazione e Avvio

### Prerequisiti
*   Java 17 o superiore installato.
*   PostgreSQL installato e in esecuzione.

### Configurazione Database
Il progetto è configurato per connettersi a un database PostgreSQL locale. Assicurati di avere un database chiamato `siw-federazione` o modifica il file `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/siw-federazione
spring.datasource.username=postgres
spring.datasource.password=postgres
```

### Avvio dell'Applicazione
1.  Clona il repository.
2.  Apri il terminale nella cartella del progetto.
3.  Esegui il comando Maven:
    ```bash
    ./mvnw spring-boot:run
    ```
4.  L'applicazione sarà disponibile all'indirizzo: `http://localhost:8081`

---

## 📂 Struttura del Progetto

```
siw-federazione/
├── src/main/java/it/uniroma3/siw/
│   ├── authentication/  # Configurazione sicurezza
│   ├── controller/      # Gestione delle richieste HTTP
│   ├── model/           # Entità del dominio (Squadra, Giocatore, ecc.)
│   ├── repository/      # Interfacce per l'accesso ai dati
│   └── service/         # Logica di business
├── src/main/resources/
│   ├── static/          # Risorse statiche (CSS, Immagini)
│   └── templates/       # Pagine HTML (Thymeleaf)
└── pom.xml              # Dipendenze Maven
```
