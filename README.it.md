# Sintropy x Shelly – Design Challenge

## Obiettivo

Vogliamo integrare nella piattaforma **Sintropy** un modulo per gestire dispositivi **Shelly** utilizzando le nostre API.

⚠️ Questa prova è focalizzata sul **ragionamento**, non sul codice.  
Non compileremo né eseguiremo nulla.  
Ci interessa capire **come pensi**, come strutturi un problema e come spieghi le tue scelte.

---

## Contesto

Le API Sintropy sono:

- **Multi-tenant** (più clienti utilizzano il sistema in modo isolato)
- Protette da un sistema di autenticazione già esistente che permette di identificare quale tenant sta effettuando la richiesta
- La progettazione dell’autenticazione/autorizzazione **non fa parte del test**

Puoi assumere che quando una richiesta arriva al tuo modulo, il tenant sia già noto.

---

## Documentazione

- Sintropy API: https://sintropy.ai/api-docs  
- Shelly API: https://shelly-api-docs.shelly.cloud/

Per quanto riguarda la documentazione Shelly:

👉 **Ignora la parte relativa a "Cloud API / API Integrator".**  
Concentrati solo sulle API utili per:
- lettura dati del dispositivo
- lettura stato ON/OFF
- comando ON/OFF

Non è necessario conoscere tutto nel dettaglio.

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
Il comando ON/OFF può essere eseguito anche manualmente.  
Il sistema deve quindi poter leggere e mantenere uno **stato aggiornato** del dispositivo.

---

## Scenario di scala

Considera uno scenario con **100 clienti**, ognuno con **100 dispositivi** (circa **10.000 device** totali).

**Ragiona su come garantire che lo stato ON/OFF esposto dalle API Sintropy sia il più possibile aggiornato nel tempo, evitando soluzioni che potrebbero non scalare bene all’aumentare dei dispositivi.**

Inoltre:

- Considera che le API esterne (Shelly) potrebbero non essere sempre disponibili: come gestisci questa situazione?
- Spiega cosa intendi per “stato aggiornato” e quali compromessi accetteresti tra accuratezza e scalabilità.

---

## Cosa ti chiediamo di fare

Descrivi:

1. Come modelleresti i dispositivi in Sintropy (tenendo conto del multi-tenant)
2. Come esporresti voltage/current e stato ON/OFF via API
3. Come invieresti un comando ON/OFF
4. Come gestiresti cambiamenti di stato manuali
5. Come gestiresti indisponibilità temporanee delle API Shelly
6. Eventuali problemi o edge case

Non esiste una risposta “giusta”.  
Ci interessa il ragionamento più della soluzione perfetta.

---

## Deliverable

Crea una repository privata usando questo template e aggiungici come collaborator.

Crea un file:

`SOLUTION.md`

Includi:

- Le tue assunzioni
- Architettura proposta
- Esempi di endpoint con JSON
- Spiegazione delle scelte
- Alternative considerate
- (Opzionale) sezione “Bonus – AWS”

🚫 Non scrivere codice eseguibile.

---

## Criteri di valutazione

Valuteremo:

- Chiarezza del ragionamento
- Strutturazione del problema
- Coerenza tra API, tenant e stato dei dispositivi
- Capacità di ragionare su scalabilità e disponibilità
- Capacità di valutare compromessi
- Comunicazione tecnica

Non valutiamo codice o completezza implementativa.

---

## Bonus (facoltativo) – AWS

Se conosci AWS, descrivi ad alto livello come progetteresti le API Sintropy utilizzando servizi AWS.

Se non conosci AWS, ignora questa parte: non influenzerà la valutazione.

---

## Tempo

Prenditi il tempo che ritieni opportuno.  
Nel caso ci sentiremo per approfondire eventuali idee interessanti.

---

## Consegna

1. Clicca "Use this template"
2. Crea una repository privata
3. Aggiungi come collaborator:
   - `pietroparini2`
   - `CDNNDR`
4. Inviaci il link
