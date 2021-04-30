# Descrizione Dashboard CASI - COVID-19 Regione Umbria
_v.1.20 del 24/04/2020_

Descrizione dei dataset visualizzati nella dashboard realizzata dalla Regione Umbria allo scopo di informare i cittadini e mettere a disposizione in modo trasparente i dati raccolti, utili ai soli fini comunicativi e informativi, sotto licenza CC-BY-4.0. I dati vengono pubblicati nella dashboard anche più volte al giorno, in base al loro aggiornamento progressivo e con un processo validato da parte della Funzione Sanità del Centro Operativo Regionale di cui alla DGR 126/2020. Occorre quindi fare riferimento a data del fenomeno ed alla data di ultimo aggiornamento.

## Dataset: _casi e dati generali emergenza_

Il dataset contiene le informazioni generali riguardanti l'emergenza da coronavirus in Umbria, pubblicati a partire da aprile 2020. 

Interrogabile via API: [SI](https://apistore.regione.umbria.it/store/apis/info?name=COVID-19&version=1.0.0&provider=admin&tag=Agenda%20digitale-group)

Pubblicato in Open Data: [SI](http://dati.umbria.it/dataset?tags=coronavirus)

![Schema principali concetti](/img/schema_tracciato_covid_umbria.png)

nb. La disponibilità attuale di ogni campo per le varie aree geografiche o strutture è indicata nelle colonne "Disp".

| Nome campo         | Descrizione           | Disp.Naz. (equivalente campo DPC) |Disp. Reg.|Disp. Com.|Disp. Osp.| Formato | Esempio |
|--------------------|-----------------------|-----------------------------------|----------|----------|----------|---------|---------|
| **data**                        | Data dell’informazione            | data     |X|X|X       | YYYY-MM-DD HH:MM:SS Ora italiana | 2020-03-05 12:15:45 |
| **stato**                       | Stato di riferimento              | stato     |X|X|X      | XYZ (ISO 3166-1 alpha-3)      | ITA                 |
| **codice_regione**              | Codice della Regione (ISTAT) | codice_regione |X|X|X      | Numero    | 10                  |
| **denominazione_regione**              | Denominazione della Regione |denominazione_regione |X|X|X | Testo                        | Umbria                  |
| **codice_geo**              | Codice area geografica (ISTAT per i comuni) a cui si riferiscono i dati |      |X|X|    | Numero                        | 55004                  |
| **denominazione_geo**       | Denominazione dell'area geografica (ad es. regione o comune) o struttura (ad es. ospedale) a cui si riferiscono i dati       |      |X|X|X    | Testo                         | Amelia             |
| **tipo_geo**              | Tipo di area geografica o struttura a cui si riferiscono i dati. Valorizzato nel modo seguente: _regione; comune; ospedale; extra (per i dati sui non residenti);_ |    |X|X|X    | Testo                        | Comune                  |
| **lat_geo**                         | Latitudine (centroide)            | lat     |X|X|        | WGS84                         | 42.6589177          |
| **long_geo**                        | Longitudine (centroide)           | long    |X|X|        | WGS84                         | 13.70439971         |
| **residenti**                 | Totale residenti da ISTAT 2019              |          |X|X|n/a           | Numero                        | 11819                   |
| **fascia_eta**	| Ove applicabile al dato, indica l'intervallo di età, compreso tra un valore minimo e uno massimo, nel modo seguente: _A. Minore di 6 anni; B. da 6 anni a 13 anni; C. da 14 a 17 anni; D. da 18 a 39 anni; E. da 40 a 64 anni; F. da 65 a 79 anni; G. maggiore di 80 anni_ |    |X| |     | Testo	| A. Minore di 6 anni |
| **sesso**  | Ove applicabile al dato, indica il sesso delle persone a cui si riferisce il dato.	            	|     |X| |        | Testo |	M |
| **casi_positivi**                 | Totale complessivo delle persone ad oggi risultate positive ad almeno un tampone oro-faringeo; _anche uguale a: attualmente_positivi + guariti + deceduti_              | totale_casi    |X|X|n/a    | Numero                 | 3    |
| **tasso_casi_positivi_x1000** | Prevalenza del totale dei casi positivi ogni 1000 abitanti residenti, dall'inizio dell'emergenza; _calcolo: casi_positivi / residenti * 1000_  |    | | |n/a     | Numero                        | 2,25                   |
| **nuovi_positivi**  | Nuovi casi positivi dal giorno precedente; _calcolo: casi_positivi - casi_positivi del giorno prima_       | nuovi_positivi     |X|X|n/a       | Numero                        | 3                   |
| **tasso_nuovi_settimana_x1000** | Incidenza dei nuovi casi positivi ogni 1000 abitanti residenti, negli ultimi 7 giorni; _calcolo: nuovi_positivi degli ultimi 7 giorni / residenti * 1000_  |    | | |n/a     | Numero                        | 2,25                   |
| **isolamento**      | Totale complessivo delle persone sottoposte alle due modalità di isolamento possibile, fiduciario o contumaciale. Quindi non per forza testate positive; _calcolo: attualmente_positivi + isolamento_volontario_ |        |X|X|n/a        | Numero                        | 3                   |
| **isolamento_fiduciario (era isolamento_volontario)**      | Attuale numero di persone sottoposte ad isolamento fiduciario in quanto hanno avuto contatti stretti con casi positivi, loro familiari o casi sospetti definiti dall'ISP. Non sono testate positive e sono in isolamento in casa o altra struttura non ospedaliera |         | | |n/a         | Numero                        | 3                   |
| **isolamento_contumaciale (era in_isolamento_domiciliare)**      | Attuale numero di casi positivi che sono tenuti a restare in isolamento contumaciale, senza ricovero |      |X|X|n/a       | Numero                        | 3                   |
| **isolamento_positivi**      | Attuale numero di casi positivi che sono tenuti a restare in isolamento contumaciale, tolti i guariti clinici; _calcolo: isolamento_positivi_sintomatici + isolamento_positivi_asintomatici; oppure anche: isolamento_contumaciale - guariti_clinici_ | isolamento_domicialiare    |X| |n/a    | Numero                        | 3                   |
| **isolamento_positivi_sintomatici**      | Attuale numero di casi positivi in isolamento contumaciale, con sintomi |     |X| |n/a     | Numero                        | 3                   |
| **isolamento_positivi_asintomatici**      | Attuale numero di casi positivi in isolamento contumaciale, senza sintomi |     |X| |n/a     | Numero                        | 3                   |
| **usciti_da_isolamento**      | Totale numero di casi positivi usciti dall'isolamento contumaciale (non più positivi al tampone) |        |X| |n/a        | Numero                        | 3                   |
| **ricoverati_totale**        | Attuale numero dei casi positivi che sono ricoverati in ospedale        | totale_ospedalizzati    |X|n/a|X     | Numero                        | 3                   |
| **di_cui_ricoverati_con_sintomi**      | Attuale numero di casi positivi che sono ricoverati in reparti diversi dalla terapia intensiva; _calcolo: ricoverati_totale - di_cui_ricoverati_in_terapia_intensiva_ | ricoverati_con_sintomi    |X|X|X    | Numero                        | 3                   |
| **di_cui_ricoverati_in_terapia_intensiva**           | Attuale numero di casi positivi ricoverati in terapia intensiva   | terapia_intensiva       |X|X|X         | Numero                        | 3                   |
| **terapia_intensiva_attuali_posti**           | Attuale numero di posti in terapia intensiva   |      | |n/a|               | Numero                        | 3                   |
| **in_terapia_intensiva_attuali_degenti**           | Attuale numero di ricoverati (anche non positivi) in terapia intensiva   |          | |n/a|           | Numero                        | 3                   |
| **totale_positivi** | Attuale numero di casi positivi tolti i guariti clinici ; _calcolo: attualmente_positivi - guariti_clinici; oppure anche: isolamento_positivi + ricoverati_totale_    | totale_positivi     |X|X|n/a     | Numero                  | 3  |
| **attualmente_positivi** | Attuale numero di casi positivi; _calcolo: ricoverati_totale + in_isolamento_contumaciale_      |    |X|X|n/a      | Numero                     | 3              |
| **tasso_positivi_x1000** | Tasso degli attuali casi positivi ogni 1000 abitanti residenti; _calcolo: attualmente_positivi / residenti * 1000_  |    |X|X|n/a    | Numero                        | 1,85                   |
| **sign_positivi_x1000**  | Significatività degli attuali casi positivi ogni 1000 abitanti residenti rispetto al tasso medio regionale; _calcolo: 1 se tasso_positivi_x1000 superiore del 5% alla media, oppure -1 se tasso_positivi_x1000 inferiore del 5% alla media, altrimenti 0 se intorno alla media_  |   |X|X|n/a    | Numero                        | 1                   |
| **dimessi_guariti**              | Totale dei guariti e dei guariti clinici; _= calcolo: guariti + guariti_clinici_           | dimessi_guariti     | | |n/a    | Numero                        | 3                   |
| **guariti**              | Totale dei casi positivi che risolvono i sintomi dell’infezione da Covid-19 e che risultano negativi in due test consecutivi effettuati a distanza di 24 ore uno dall’altro           |     |X|X|n/a     | Numero                        | 3                   |
| **guariti_clinici**      | Totale dei casi positivi che risultano clinicamente guariti, anche se ancora positivi al test. Pur non essendo più necessario il ricovero, la persona non può ritornare alla vita di comunità perché ancora con una carica virale elevata. Dato aggiornato fino al 26.11.2020     |    | | |n/a     | Numero                        | 3                   |
| **deceduti**             | Totale dei casi positivi che sono deceduti, anche con diagnosi post-mortem; La conferma che la causa del decesso è attribuibile esclusivamente al SARS-CoV-2 verrà dichiarata dall’Istituto Superiore di Sanità | deceduti     |X|X|n/a     | Numero                        | 3                   |
| **indice_letalita**      | Percentuale di deceduti sul totale dei casi positivi; _calcolo: deceduti * 100 / casi_positivi_ |              |X|X|n/a     | Numero                        | 3                   |
| **tamponi_eseguiti**     | Totale dei tamponi molecolari (test) effettuati, un soggetto può essere sottoposto a più tamponi quindi non è indicativo delle persone controllate       | tamponi        |X| |n/a        | Numero                        | 3                   |
| **nuovi_tamponi_eseguiti** | Nuovi tamponi molecolari eseguiti nel singolo giorno; _calcolo: tamponi_eseguiti - tamponi_eseguiti del giorno prima_       |       |X| |n/a       | Numero                        | 3                   |
| **tamponi_positivi**     | Totale dei tamponi molecolari (test) effettuati con esito positivo, un soggetto può essere sottoposto a più tamponi       |      |X| |n/a       | Numero                        | 3                   |
| **casi_testati**     | Totale dei soggetti sottoposti a test        |      |X| |n/a      | Numero                        | 3                   |
| **nuovi_casi_testati** | Nuovi soggetti su cui si è eseguito il test nel singolo giorno; _calcolo: casi_testati - casi_testati del giorno prima_       |     |X| |n/a      | Numero                        | 3                   |
| **testo_acc**      | Testo sostitutivo del dato a fini di accessibilità.    |    | | |    | Testo         | XYZ           |
| **note**                 | Eventuali note sul dato raccolto. In questo campo viene indicata anche l'eventuale revisione di aggiornamento del dato.       |        |X|X|X        | Testo                        | XYZ                   |
| **status**               | Se dato ufficiale confermato = "pub"       |       |X|X|X      | Testo                        | pub       |
