# Sintropy x Shelly – Design Challenge

## Obiettivo

Vogliamo integrare nella piattaforma **Sintropy** un modulo per gestire dispositivi **Shelly** utilizzando le nostre API.

⚠️ Questa prova è focalizzata sul **ragionamento**, non sul codice.  
Non compileremo né eseguiremo nulla.  
Ci interessa capire **come pensi**, come strutturi un problema e come spieghi le tue scelte.

---

## Documentazione

- Sintropy API: https://sintropy.ai/api-docs  
- Shelly API: https://shelly-api-docs.shelly.cloud/

Per quanto riguarda la documentazione Shelly:

👉 **Ignora la parte relativa a "Cloud API / API Integrator".**  
Ai fini della prova, concentrati solo sulle API utili per:
- lettura dati del dispositivo
- lettura stato ON/OFF
- comando ON/OFF

Non è necessario conoscere tutto nel dettaglio: usa solo le parti rilevanti.

---

## Scope della prova

Per semplicità, immaginiamo di dover gestire una categoria generica di dispositivi Shelly che:

- producono misurazioni elettriche (es. tensione e corrente)
- espongono uno stato ON/OFF e possono essere attivati o disattivati

Non è importante il modello specifico del dispositivo.  
L’obiettivo è ragionare su come astrarre questo tipo di device all’interno delle API Sintropy.

Trattiamo quindi i dispositivi in modo concettuale, come:

- **sensori** che generano dati (voltage/current)
- **attuatori** che hanno uno stato (ON/OFF) modificabile

⚠️ Nota importante:  
Il comando ON/OFF può essere eseguito anche manualmente (es. pulsante fisico o operatore).  
Il sistema deve quindi poter leggere e mantenere uno **stato aggiornato** del dispositivo.

Non serve affrontare:

- UI
- provisioning account
- deploy o infrastruttura
- database reale
- copertura di tutti i modelli Shelly

Se qualcosa non è specificato, puoi fare assunzioni ragionevoli: dichiararle fa parte del lavoro reale.

---

## Cosa ti chiediamo di fare

Immagina di dover progettare questa integrazione.

Descrivi:

1. Come modelleresti i dispositivi in Sintropy
2. Come esporresti le informazioni (voltage/current e stato ON/OFF) via API
3. Come invieresti un comando ON/OFF tramite le API Sintropy
4. Come gestiresti il fatto che lo stato possa cambiare anche manualmente
5. Eventuali problemi o edge case che immagini possano emergere

Non esiste una risposta “giusta”.  
Ci interessa il percorso logico più della soluzione perfetta.

---

## Deliverable

Crea una repository privata usando questo template e aggiungici come collaborator.

Nella repository crea un file:

`SOLUTION.md`

Dentro includi:

- Le tue assunzioni
- Una proposta di architettura (anche semplice)
- Esempi di endpoint con JSON di esempio
- Spiegazione delle scelte fatte
- Eventuali alternative considerate

Puoi usare:

- Testo descrittivo
- Bullet point
- Esempi JSON
- Pseudocodice
- Diagrammi semplici (anche ASCII o Mermaid)

🚫 Non scrivere codice eseguibile.  
Preferiamo una spiegazione chiara in `SOLUTION.md` piuttosto che codice funzionante.

---

## Criteri di valutazione

Valuteremo:

- Chiarezza del ragionamento
- Capacità di strutturare il problema
- Coerenza tra API, stato e comportamento dei dispositivi
- Capacità di individuare possibili edge case
- Comunicazione tecnica

Non valutiamo:

- Codice eseguibile o funzionante
- Completezza dell’implementazione
- Scelta del linguaggio o framework
- Qualità formale di diagrammi o documentazione
- Precisione sintattica degli endpoint
- Formattazione o stile del repository

Puoi usare qualsiasi formato che ritieni utile per spiegare il tuo ragionamento.

---

## Bonus (facoltativo) – AWS

Questo punto è opzionale.

Se conosci AWS (anche a livello base), rispondi brevemente alla seguente domanda.  
Se non conosci AWS, ignoralo: non influenzerà la valutazione.

**Domanda:**  
Ignorando la parte Shelly, come progetteresti le API di Sintropy basandoti su servizi AWS?

È sufficiente una descrizione ad alto livello, ad esempio:

- Quali servizi useresti (API Gateway, Lambda, ECS, DynamoDB, SQS, EventBridge, ecc.)
- Come separeresti i componenti principali
- Come gestiresti autenticazione, logging e persistenza

Puoi rispondere in una sezione “Bonus – AWS” dentro `SOLUTION.md`.

---

## Tempo

Prenditi il tempo che ritieni opportuno.  
Nel caso ci sentiremo per approfondire insieme eventuali idee abbozzate o punti interessanti.

---

## Consegna

1. Clicca "Use this template"
2. Crea una repository privata nel tuo account
3. Aggiungi come collaborator i seguenti utenti GitHub:
   - `pietroparini2`
   - `CDNNDR`
4. Inviaci il link della repository
