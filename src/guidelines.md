# Linee guida

Quando dobbiamo definire l'architettura di rete di un servizio, dobbiamo avere prima ben chiari una serie di elementi che ci aiuteranno nella progettazione. In pratica dobbiamo _visualizzare_ chiaramente come il nostro servizio verrà usato, immaginando il come, perché, dove, etc. di ogni azione che l'utente compie.

> Dobbiamo sempre ricordarci di porre l'*utente* che dovrà fruire del nostro servizio al centro delle nostre riflessioni, ed a questo fine possiamo usare diverse strategie. Questo tipo di progettazione si chiama "User Centered Design" (UDC).

I passi che dovremo svolgere sono i seguenti:

1. dimensionamento: quali utenti, quanti utenti
1. tipo di dispositivi end-user: quali dispositivi, quanti dispositivi
1. tipo di collegamenti degli end-device, bluetooth, WiFi, rete dati, RFIF, etc.
1. dislocazione dei server: on-premises, cloud
1. dislocazione dei db: on-premises, cloud

In ognuno di questi passaggi ci si può aiutare con dei diagrammi o disegni per chiarire meglio che cosa intendete. Non abbiate timore di scrivere o disegnare: la cosa più importante in questa fase è che siate chiari.

Nei passaggi in cui operate delle scelte, è fondamentale che specifichiate il perché avete optato per una determinata tecnologia piuttosto che per un'altra.

- <span class="ok">OK</span>: scelgo una connessione WiFi perché ha una maggiore banda che mi permette di servire adeguatamente lo streaming video
- <span class="no">NO</span>: scelgo la connessione WiFi
- <span class="ok">OK</span>: scelgo un server in cloud perché ha minori costi iniziali e mi permette di pagare solo quello che effettivamente uso
- <span class="no">NO</span>: scelgo un server in cloud

I fattori da tenere in considerazione nella discussione di vantaggi e svantaggi:

- costi (sia iniziali che di esercizio)
- requisiti non funzionali (prestazioni, affidabilità)
- sicurezza dei dati, vulnerabilità ad eventuali attacchi
- normativa vigente, es. GDPR

Quando possibile è sempre utile aggiungere anche un'analisi quantitativa, oltre che semplicemente qualitativa. Ad esempio possiamo migliorare gli esempi precedenti come segue:

- Considerando 100 utenti che guardano in contemporanea un flusso video di 4kbps, ho bisogno di 800 kbps che può essere adeguatamente sostenuto da una connessione WiFi
- Si può stimare il costo iniziale del mio servizio pari a circa €10k (server+rack) e circa €500 mensile per la gestione, mentre in cloud non ho costi iniziali ed ho un costo mensile di circa €400 euro; scelgo quindi il server in cloud perché ha sia minori costi iniziali che di esercizio e mi permette di pagare solo quello che effettivamente uso



Infine, nella costruzione delle frasi, consiglio di seguire alcuni _pattern_ che aiutano a creare un discorso che sia chiaro e continuo:

- mettere l'utente come soggetto e specificare il fine dell'azione
  - <span class="ok">OK</span>: il fattorino scannerizza il codice a barre del pacco per prenderlo in carico
  - NO: codice a barre è scannerizzato dal fattorino

- scrivere possibilmente un caso d'uso completo del servizio, dal momento in cui l'utente inizia ad usarlo fino alla fine
  - <span class="ok">OK</span>: il fattorino, prende in carico il pacco scannerizzando il codice a barre, quando lo consegna al destinatario lo scannerizza di nuovo per confermare l'avvenuta consegna
  - <span class="no">NO</span>: il codice a barre serve per la presa in carico e la consegna

Come ultimo suggerimento, può essere utile considerare nel nostro discorso anche alcuni casi in cui avviene qualcosa di imprevisto. Esempio: se il destinatario non è in casa? se il pacco si perde o danneggia durante il trasporto? se il codice a barre diventa illeggibile per qualche motivo? etc.






