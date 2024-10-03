# Learning-Domain-Driven-Design
Summary of book 

### CHAPTER 1
## Analyzing Business Domains

Cos'e' il business domain:
E' il servizion che una compagnia offre ai propri e potenziali clienti. Ogni azienda ne puo' avere piu' di uno

Subdomains:
I domini vengono suddivisi in sotto domini, ognunco con un obbiettivo specifico e diverso.

Tipi di subdomains: 
- core subdomain
- generic subdomain
- supporting subdomain

#### Core subdomain
E' il valore aggiunto che ha l'azienda nei confronti dei competitors (ad esempio inventare prodotti o servizi). Dovrebbe avere un alta complessita' per evitare di essere replicato facilmente. La fonte del vantaggio competitivo non e'
per forza di natura tecnologica. (Ad esempio un'azienda che produce gioielli il vantaggio e' dato dall'artigiano)

#### Generic subdomain
Sono le attivita' piu' generiche che tutte le aziende possono fare nella stessa maniera (ad esempio un meccanismo di autenticazione). Non e' vincolante il fatto che sia un attivita' semplice, il vero vincolo e' che non da alcun vantaggio competitivo se fatto in maniera diversa/migliore dei competitors.

#### Supporting subdomain
Supporta il core business della compagnia, ha un vantaggio farlo in maniera custom ma non deve avere alta complessita'. Non e' il principale business dell'azienda, ad asempio una campagna pubblicitaria di un prodotto. Supporta il core business ma non puo' esserlo)

I subdomain si distinguono per altri due aspetti: La volatility e la solution strategy.

#### Volatility
Il core subdomain puo' variare spesso, scelte di business, nuovi tentativi per migliorare il prodotto, cambio di target etc.
Il supporting subdomain non dovrebbe cambiare molto spesso in quanto non porta reale vantaggio competitivo coi competitors, a fronte di un grande sforzo non si hanno grandi vantaggi.
Il generic subdomain puo' cambiare in ottica di miglioramento ad esempio applicando delle patch di sicurezza aggiornando la versione di una libreria.

#### Solution strategy
Per il core subdomain e' sicuramente ideale sviluppare la soluzione internamente. In modo tale da poter fare evolvere il prodotto nella maniera piu' veloce possibile. L'azienda deve avere come obbiettivo di mantenere questa parte con la qualita' piu' alta possibile.
Il generic subdomain si puo' tranquillamente esternalizzare in quanto solitamente sono soluzioni generiche e configurazioni custom (codice open source)
Il supporting subdomain e' ideale svilupparlo internamente anche attraverso l'utilizzo di qualche framework. Data la complessita' bassa di questo dominio e' adatto ad essere assegnato a sviluppatori meno esperti i quali possono fare pratica.

Domain experts

E' importante indetificare queste persone le quali saranno le persone che daranno un impatto piu' importante sul prodotto.
Sono le persone che conoscono in maniera approfondita il settore. Non sono gli sviluppatori, nemmeno gli analisti. Sono coloro che hanno una conoscenza approfondita del problema ed esperienza diretta, coloro che potrebbero anche utilizzare il software.


### CHAPTER 2
## Discovering Domain Knowledge

Questo capitolo e' concentrato nella spiegazione dell'importanza dell' "ubiquitous language".

### Business Problems
L'obbiettivo aziendare e' fornire una soluzione per i problemi dei clienti.
La parola problema non deve essere interpretata come un problema matematico o qualcosa che puo' essere risolto con la matematica.

Durante il capitolo spiega l'importanza di evitare tanti livelli di comunicazione perche' ad ogni livello si perdono informazioni (telefono senza fili)
Definire un liguaggio univoco e' utile per evitare fraintendimenti.

### What Is a Model?

Spiega che un modello non e' la coppia reale di una determinata cosa ma un costrutto umano che ci aiuta a dare un senso ai sistemi del mondo reale.
Per essere piu' chiaro fa un esempio di una mappa. La stessa mappa puo' rappresentare dettagli specifici, per esempio la mappa di una citta' che mostra la metropolitana piuttosto che le strade della citta'. Oppure la divisione in fusi orari piuttosto che le zone di calore.

### CHAPTER 3
## Managing Domain Complexity


In questo capitolo viene introdotto il concetto di "bounded context". Lo fa facendo un esempio, la stessa parola "lead" ha significato diverso per il team di marketing e il team di vendita. Vengono proposte varie soluzioni non funzionali o non ottimali. Viene proposto a questo punto di utilizzare i Bounded context. Li accomuna alle mappe del paragrafo precedente. E proprio come in quelle mappe servono per far vedere alcuni dettagli specifici anche nei vari contesti servono informazioni diverse.
Quindi nel contesto del reparto di vendite il "lead" avra' determinate caratteristiche mentre nel contesto di marketing il lead ne avra' altre. Inoltre ogni bunded context ha un ubiquitous language specifico. Quindi il lead nei vari contesti assume significati leggermente diversi.

### CHAPTER 4
## Integrating Bounded Contexts

I confini tra i vari bounded context devono essere chiari. Pero' tra vari contesti ci puo'/deve essere comunicazione, ma se ognuno ha una linguaggio diverso la comunicazione puo' risultare difficile. Per questo vengono utilizzate delle forme di comunicazione chiamate "contratto".
Ce ne sono di tre tipi: 
- cooperation
- customer–supplier
- separate ways

#### Cooperation
In quest ocaso i team dovranno avere un ottima comunicazione, il successo di un team dipende dal successo dell'altro. 
Ci sono principalmente 2 pattern di integrazione: Partnership, Shared Kernel

##### Partnership
E' basato su una comunicazione molto frequente, infatti non e' indicato per i team distribuiti.
Ogni team comunica con l'altro riguardo i cambiamenti delle API o dei modelli (per esempio) e l'altro team si occupa di integrare le modifiche.

##### Shared Kernel
Ci puo' essere il caso in cui alcuni modelli possano essere utili in multipli contesti, ad esempio il modello per l'autorizzazione. 
Questo modello e' importante che abbia solo gli elementi necessari per i vari contesti. Questo perche', per definizione, viola il principio di isolamento dei contesti.
Per capire quando usare il shared kernel bisogna analizzare il costo di dupplicazione rispetto al costo di coordinazione. Se il costo di dupplicazione e' basso e' giusto che ogni contesto abbia i suoi modelli. Se invece e' altro potrebbe essere utile utilizzare questo approccio. Quando il costo di dupplicazione e' alto? Sopratutto quando il modello cambia spesso. Comunicare con tutti i vari moduli le modifiche potrebbe essere impegnativo e generare errori. 
Violando il principio descritto sopra il suo utilizzo deve essere giustificato.

#### Customer–supplier
Diversamente dal pattern di cooperation il customer supplier ha due team dove il successo e' indipendente l'uno dall'altro.
Il contratto di integrazione puo' essere definito da entrambe le parti (upstream team e downstream team)
Viene applicato attravero l'utilizzo di 3 patterns:
- conformist
- anticorruption layer
- open-host service

##### Conformist
Il fornitore non ha reale interesse per supportare le necessita' del cliente. Utilizza un approccio "Take it or leave it". Il cliente puo' decidere se aderire o meno a questo tipo di contratto. Solitamente sono contratti Standard industriali (ad esempio API. REST). Quindi il fornitore ha totale controllo sul codice rilasciato.

##### Anticorruption layer (ACL)
Come nel pattern conformist l'autorita' e' sblianciata sul upstream service. In questo caso il servizio downstream non si vuole adattare completamente e crea un layer intermedio che fa da interprete.
Quando viene applicato:
- Quando il servizio destinatario contiente il core subdomain. In quanto dovrebbe essere totalmente indipendente dal fornitore.
- Quando il servizio upstream e' ineficiente
- Quando il servizio upstream cambia spesso, in questo modo si cambia solo il meccanismo di traduzione.

##### Open-Host Service
E' l'inverso del ACL, il fornitore ci tiene ai clienti quindi si adatta alle loro esigenze. Crea un servizio che slega il codice interno da quello esposto (chiamato pub‐
lished language). Quando deve cambiare qualcosa implementa diverse versioni del servizio e il cliente decidera' di cambiare versione una volta pronto.


#### Separate Ways
Questa e' l'ultima opzione di collaborazione. Non collaborare affatto.

##### Communication Issues
Quando ci sono dei problemi di comunicazione gravi conviene dupplicare le funzionalita' nei vari bounded contexts.

##### Generic Subdomains
Il sottodominio duplicato da la possibilita' di prendere strade separate.  Nei generic subdomain che sono facili da integrare puo' essere conveniente duplicare le integrazioni invece che avere un servizio condiviso. Un esempio puo' essere il servizio di Logging.

##### Model Differences
Quando c'e' troppa differenza tra i modelli dei vari contesti conviene andare in vie separate.
