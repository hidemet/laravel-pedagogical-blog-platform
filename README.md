# PIMEL - Piattaforma Blog per Pedagogista (Laravel 11)

**PIMEL (Pedagogia In Movimento)** è un'applicazione web full-stack costruita con **Laravel** che funge da piattaforma digitale completa per un consulente pedagogico. Il progetto include un blog ricco di funzionalità, una sezione per la presentazione dei servizi, e un pannello di amministrazione (CMS) personalizzato per la gestione totale dei contenuti.

---

## 🖼️ Panoramica del Progetto

| Homepage Pubblica | Articolo del Blog | Dashboard Admin | Gestione Contenuti (CMS) |
| :---: | :---: | :---: | :---: |
| ![Screenshot della Homepage](./media/screenshot-homepage.png) | ![Screenshot di un articolo](./media/screenshot-article.png) | ![Screenshot della Dashboard Admin](./media/screenshot-admin-dashboard.png) | ![Screenshot della gestione articoli](./media/screenshot-admin-articles.png) |

---

## ✨ Feature Principali

### Area Pubblica (Client-Facing)
*   **Blog Dinamico:** Articoli organizzati in rubriche, con funzionalità di ordinamento (per data, popolarità) e filtraggio.
*   **Interazione Utente:** Sistema di **commenti** (con risposte nidificate) e **"Mi Piace"** (gestiti via AJAX per un'esperienza fluida).
*   **Gestione Servizi:** Sezione dedicata alla presentazione dei servizi offerti dal professionista.
*   **Autenticazione e Profilo Utente:** Registrazione, login, e un'area profilo dedicata per gli utenti.
*   **Newsletter:** Form di iscrizione con selezione delle rubriche di interesse.
*   **Form di Contatto:** Modulo per l'invio di messaggi diretti, con notifica via email all'amministratore.

### Area Amministrativa (Pannello CMS)
*   **Dashboard Riepilogativa:** Una homepage per l'admin con accesso rapido a tutte le sezioni di gestione.
*   **CRUD completo per gli Articoli:** Creazione, modifica e cancellazione di articoli con gestione di immagini (upload/rimozione), stato (Bozza, Pubblicato, Pianificato, Archiviato) e scheduling delle pubblicazioni.
*   **Gestione Rubriche e Servizi:** Interfacce CRUD per organizzare le categorie del blog e le pagine dei servizi.
*   **Moderazione Commenti:** Pannello per approvare o eliminare i commenti lasciati dagli utenti.
*   **Gestione Iscritti Newsletter:** Visualizzazione degli iscritti e modifica delle loro preferenze.

## 🏛️ Architettura e Best Practice Laravel

Questo progetto è stato costruito ponendo forte enfasi sulla scrittura di codice pulito, manutenibile e scalabile, sfruttando le migliori practice del framework Laravel.

*   **Framework:** **Laravel 11** (PHP 8.2+)
*   **Architettura:**
    *   **Pattern MVC:** Rigorosa separazione delle responsabilità.
    *   **Form Requests** (`StoreArticleRequest`, `StoreRubricRequest`): Per disaccoppiare la logica di validazione dai controller.
    *   **Actions** (`SaveArticleAction`): Per incapsulare logiche di business complesse e riutilizzabili.
    *   **Observers** (`ArticleObserver`): Per automatizzare task come la generazione dello slug e degli excerpt.
    *   **Policies** (`ArticlePolicy`): Per una gestione granulare e centralizzata dei permessi di autorizzazione.
*   **Database:**
    *   Schema progettato e gestito tramite **Migrations**.
    *   Popolamento dei dati di test tramite **Seeders** e **Factories**.
    *   Relazioni Eloquent complesse (es. Many-to-Many tra rubriche e iscritti, polimorfiche se necessarie).
*   **Frontend:**
    *   **Vite:** Per la compilazione e l'ottimizzazione degli asset (CSS e JS).
