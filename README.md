# Sintropy x Shelly – Design Challenge

## Obiettivo

Vogliamo integrare nella piattaforma **Sintropy** un modulo per gestire dispositivi **Shelly** utilizzando le nostre API.

⚠️ Questa prova è focalizzata sul **ragionamento**, non sul codice.  
Non compileremo né eseguiremo nulla.  
Ci interessa capire come pensi, come strutturi un problema e come spieghi le tue scelte.

---

## Contesto

Le API Sintropy sono:

- **Multi-tenant**
- Protette da un sistema di autenticazione già esistente che identifica il tenant
- L’autenticazione/autorizzazione **non fa parte del test**

Puoi assumere che quando una richiesta arriva al tuo modulo, il tenant sia già noto.

---

## Documentazione

- Sintropy API: https://sintropy.ai/api-docs  
- Shelly API: https://shelly-api-docs.shelly.cloud/

👉 Ignora la sezione relativa a **API Integrator**.

Concentrati solo sulle API utili per:

- Lettura dati del dispositivo  
- Lettura stato  
- Eventuale ricezione aggiornamenti di stato  
- Comando ON/OFF  

Sei libero di scegliere l’approccio che ritieni più adatto.

---

## Scope della prova

Consideriamo dispositivi che:

- Producono misurazioni elettriche (voltage/current)
- Espongono uno stato ON/OFF modificabile

Il modello specifico non è rilevante: ragiona per astrazione.

⚠️ Lo stato può cambiare anche manualmente.  
Il sistema deve mantenere uno **stato aggiornato** del dispositivo.

---

## Scenario di scala

Considera **100 clienti**, ognuno con **100 dispositivi** (circa **10.000 device**).

**Ragiona su come garantire che lo stato ON/OFF esposto dalle API Sintropy sia il più possibile aggiornato nel tempo, evitando soluzioni che potrebbero non scalare bene all’aumentare dei dispositivi.**

Inoltre:

- Le API Shelly potrebbero non essere sempre disponibili: come gestisci questa situazione?
- Spiega cosa intendi per “stato aggiornato” e quali compromessi accetteresti tra accuratezza e scalabilità.

---

## Cosa ti chiediamo di fare

Descrivi:

1. Modello dei dispositivi (multi-tenant)
2. API per telemetria e stato
3. Invio comandi ON/OFF
4. Gestione cambi manuali
5. Gestione indisponibilità Shelly
6. Eventuali edge case

Non esiste una risposta giusta.  
Ci interessa il ragionamento.

---

## Deliverable

Crea una repository privata usando questo template.

Crea un file:

`SOLUTION.md`

Includi:

- Assunzioni
- Architettura proposta
- Esempi di endpoint (JSON sufficiente)
- Spiegazione delle scelte
- Compromessi valutati

### Formato

Puoi usare **qualsiasi formato** utile a spiegare il tuo ragionamento:

- Testo libero
- Bullet point
- JSON
- Pseudocodice
- Diagrammi semplici
- Struttura mista

🚫 Non scrivere codice eseguibile o production-ready.  
Valutiamo solo chiarezza e qualità del ragionamento.

---

## Bonus (facoltativo) – AWS

Questa parte è opzionale.

Se conosci AWS (anche a livello base), rispondi brevemente alla seguente domanda.  
Se non conosci AWS, ignorala: non influenzerà la valutazione.

**Domanda:**  
Ignorando l’integrazione Shelly, come progetteresti le API Sintropy utilizzando servizi AWS?

È sufficiente una descrizione ad alto livello, ad esempio:

- Quali servizi useresti? (API Gateway, Lambda, ECS, DynamoDB, SQS, EventBridge, ecc.)
- Come separeresti i componenti principali?
- Come gestiresti autenticazione, logging e persistenza?
- Valuteresti un approccio event-driven? Perché?

Puoi inserire la risposta in una sezione “Bonus – AWS” dentro `SOLUTION.md`.

Anche una risposta parziale va benissimo: ci interessa capire il tuo ragionamento.

---

## Tempo

Prenditi il tempo che ritieni opportuno.  
Nel caso ci sentiremo per approfondire alcune idee insieme.

---

## Consegna

1. Clicca "Use this template"
2. Crea una repository privata
3. Aggiungi come collaborator:
   - `pietroparini2`
   - `CDNNDR`
4. Inviaci il link
