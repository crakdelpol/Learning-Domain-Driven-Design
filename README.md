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


