# Instructions  

## Pagina di login
Per creare una pagina privata si può procedere nel seguente modo:

1) Andare su ws.progettimolinari.it e creare in cache remota per ogni utente necessario un account inserendo come chiave un identificativo univoco e la sua password.
Ad esempio se bisogna fare un utente "admin" per il progetto "albergo" con password "topolino" bisogna inserire in cache remota:
token: token progetto
chiave: "albergo-admin"
valore: "topolino"

In alcuni progetti è necessario inserire più utenti, procedere in modo analogo.

2) La pagina privata conterrà due div:

<div id="login">
(form di login visibile a tutti)
</div>
<div id="private">
(html visibile solo da loggati)
</div>

Nel javascript si gestirà l'accesso tramite una variabile semaforo "loggedIn" che sarà true se loggati, false altrimenti. All'avvio sarà false. 
All'utente sarà mostrato quindi solo il primo div con il form di login e il div private sarà nascosto. Alla pressione del pulsante login, il javascript eseguirà una chiamata alla cache remota dove verificherà se utente e password corrispondono (vedi punto 1). Se corrispondono il semaforo "loggedIn" passerà a true e verrà nascosto il div di login mentre il div private diventerà visibile. 

3) In alcuni progetti sarà necessario tenere traccia dell'utente che ha fatto login in una apposita variabile.

# ELENCO PROGETTI
 
1) Albergo con amministrazione (Baldonado, Basta, Del Zotto)
A partire dall'esercizio sull'albergo (gestione disponibilità camere con calendario) sviluppare le seguenti estensioni:
- creare una pagina previa login con utente admin (vedi sopra) dove l'amministratore può definire un setup delle camere, indicando:
a) le tipologie di camere presenti (singola doppia tripla ecc. è un testo libero)
b) per ogni tipologia di camera indicare il numero di camere presenti
Il setup così creato può essere salvato tramite cache remota.

- modificare la pagina già svolta per permettere di caricare il setup da remoto anzichè come nella prima versione averlo preimpostato.

2) Registro elettronico (Bolo, Ghezzi, Pedicini)
Creare un sito web di registro elettronico con tre pagine:
- creare una pagina accessibile solo tramite login con utente admin, che permette di creare:
a) un elenco di studenti (nome e cognome)
b) un elenco di materie
c) dare un nome alla classe
E' prevista una sola classe.
Una volta creata, è possibile salvare i dati della classe tramite cache remota.
- creare una pagina accessibile solo tramite login con utente prof (vedi sotto), che permette di:
- visualizzare una tabella con i nomi degli studenti come righe e le materie come classi ed in ogni cella è possibile visualizzare il voto o eventualmente modificarlo.
- creare una pagina pubblica che permette di accedere alla pagina: identica alla pagina precedente, ma senza login e con i voti in sola visualizzazione

Inserire una classe con almeno 10 studenti, e almeno 8 materie.

3) Orario treni (Felix, Manfredi, Strazzullo)
Creare un sito web per gestire un semplice orario treni, che ha due pagine:
- creare una pagina accessibile solo tramite login con utente admin (vedi sotto), che permette di creare:
a) un elenco di tratte. Ogni tratta prevede una stazione di origine, una di destinazione, una durata (in ore e minuti). Esempio: "Roma", "Milano", 3 ore e 30 minuti.
b) un elenco di orari di partenza per ogni tratta (es. 6, 8, 10, 12).
- creare una pagina che permette di interrogare il sistema con le seguenti interrogazioni:
a) treni in partenza da una certa stazione ad un certo orario: indica tutti i treni in partenza da quella stazione a partire da quell'orario
b) treni in arrivo ad una certa stazione ad un certo orario: indica tutti i treni in arrivo a quella stazione a partire da quell'orario
c) tutti gli orari di una precisa tratta (indicando stazione di partenza ed arrivo).

Inserire almeno 6 tratte ed almeno 5 orari per ciascuna tratta.
 
4) Gestione evento conferenze (Malinverno, Marocco)
Per la gestione di un evento di conferenze un istituto ha bisogno di creare un sito per l'organizzazione dell'evento. Per poterlo realizzare vengono preparati due file di setup:
lista 1) elenco docenti (con quattro attributi: email, nome, cognome, password);
lista 2) elenco studenti (con due attributi: nome e cognome).

- creare una pagina accessibile solo tramite login con utente admin, che permette di:
a) creare una nuova classe con nome e argomento. Assegnare alla classe il docente (lista 1). Sarà anche possibile aggiungere partecipanti in modo dinamico, prendendoli dalla lista 2. Ogni associazione classe-studente avrà come attributo anche la presenza (inizialmente a false).
b) Visualizzare l'elenco delle classi create e modificare i dati inseriti (modifica nome, argomento, docente e modifica elenco studenti)
Sarà possibile sempre salvare i dati in cache remota.

- creare una pagina accessibile solo tramite login con utente prof (lista 1):
a) ogni docente vedrà solo le proprie classi 
b) ogni docente potrà modificare la presenza degli studenti presenti (mettendola a true).
Sarà possibile sempre salvare i dati in cache remota.

- creare una pagina pubblica che mostra
a) mostra una form di ricerca che permette di filtrare le classi per nome e argomento
b) mostra una form di ricerca che permette di filtrare le classi per docente
c) mostra una form di ricerca che permette di filtrare le classi per studente

Inserire almeno 8 classi, con 6 docenti, e 50 studenti da distribuire nelle varie classi.

5) Elenco BnB (Barbieri, Dell'Aquila, Samet)
Un sito web ha bisogno di mostrare le proprie proposte di Bed&Breakfast.
Sono previste due pagine:

- creare una pagina accessibile solo tramite login con utente admin, che permette di:
a) visualizzare, modificare ed inserire strutture b&b
b) ogni struttura ha un nome, un luogo (indirizzo), una descrizione e delle coordinate. L'admin inserisce solo nome, descrizione ed indirizzo, il sistema in automatico tramite reverse geocoding individua le coordinate.
Una volta inserita la struttura va a far parte della lista

- creare una pagina pubblica che mostra un marcatore per ogni b&b. Al click sul marcatore viene mostrato un popup con il nome e la descrizione del b&b.

Ogni progetto va realizzato su Replit, con associato un repository git. Dopo ogni modifica (testata) ciascun componente del team esegue una commit sul repository. 
Si ricorda che:
- il repository va creato su github da un solo studente;
- deve dare i permessi di accesso agli altri studenti del gruppo;
- il repository va collegato al progetto su replit.

