# object oriented programing (oop)
l'aplicazione nella ripository  e una rest API che permette di ottenere dati a partire di un data set (API) permettendo quindi la realisazione dei operazione diverse (filtri e statstiche ) su alcune campi
# formato de resultati
in seguito  ad una richiesta al servizio viene restituito  un JSON  rappresentante oggetti che modellano dati contenuti nel struttura dati  appartenente al data set  il formato dell l'oggetto rappresentante ogni singolo elemento ,nello specifico si rappresenta come segue 

```
{
   "domain": "warman.weir",
            "create_date": "2020-12-04T18:39:57.791735",
            "update_date": "2020-12-04T18:39:57.791737",
            "country": "US",
            "isDead": "False",
            "A": [
                "165.160.15.20",
                "165.160.13.20"
            ],
            "NS": [
                "dns2.cscdns.net",
                "dns1.cscdns.net"
            ],
}
```

               in particolare  
               
                 **domain** rappresenta il dominio trovato nella ricera
                 **create date** rappresenta la data di creazione 
                **update date** rappresenta la data  in cui  e stata aggiornata 
                **country** rapprensenta il coutry dove provenga il dominio 
                **isDead** rappresenta il lo stato della richiesta
                **NS** rappresenta il domain name server del dominio
                
                    
 le satistiche possono essere fatti e sono in prticolare  specificato  la data  e la zona degli esemepi di  formati JSON possono essere fatti  nel seguente modo 
                
 ```{
  "statistics": [
    {
      "zone": "bundle_all_zones",
      "date": "2020-10-12T00:00:00",
      "dec": 0,
      "inc": 40861375,
      "total": 306773769
    },
    {
      "zone": "bundle_all_zones",
      "date": "2020-09-22T00:00:00",
      "dec": 0,
      "inc": 41103956,
      "total": 306067758
    },
    {
      "zone": "bundle_all_zones",
      "date": "2020-09-04T00:00:00",
      "dec": 0,
      "inc": 36370449,
      "total": 305165199
    },
    {
      "zone": "bundle_all_zones",
      "date": "2020-09-03T00:00:00",
      "dec": 0,
      "inc": 33391168,
      "total": 304267122
    },
    {
      "zone": "bundle_all_zones",
      "date": "2020-09-02T00:00:00",
      "dec": 0,
      "inc": 37671651,
      "total": 304259267
    },
 ```
 di nota che le statistiche sono uniforme e rappresentato in modo crescente attrverso l'occurenza dell' l'attributo totale  che facilita la  lettura dei dati 
 
 # rote dell l'applicazione 
 >GET/ 
 e la rotta in cui e possibile accedere  ad un interfaccia  grafica che permette di eseguire operazioni di ricerca  e di effetuamento  delle statistiche  senza  la necessita  di utilizzare linguaggi di programazione  e/o tool esterni per effuettuare le richieste 
 >GET/DOMAINS/SEARCH
 e la rotta che permette di eseguire la ricerca su l'insieme di  domini corrispondente  diponibile e di restituire tutti domini esistente  dentro la base di dati 
 >GET/DOMAINS/TLD/
rotta in cui e possiblile  di seseguire la recerca su linsieme di domini di primo livello e accedere ai resultati secondo il un specifico paese  
>GET/DOMAINS/UPDATES/LIST
e la rotta che permette di aggiornare  la lista dei domini presente dentro la base di dati 
>GET/METADATA
rotta in cui e posssibile accedere ai  metadati  relativi all' ogetto  restituito dal servizio 
>GET/INFO /STAT/{ZONE} 
questa rotta ci permette di ottenere informazione sulle statistiche relative ad ciacuna  zona 
>GET/INFP/TLD/ZONE 
questq rotte consente di fare la restituzione delle statistiche del dominio di pro=imo livello  relativa a ciascuna zona 
  #filtri 
  Il filtro presente nel corpo della richiesta GET per filtrare i dati è una stringa in formato JSON, contenente degli oggetti dotati della seguente struttura:
  
  "
  {
    "<campo>": {
	    "<operatore>": <dato>
	}
}
  "
   
   -$eq: indica se il valore associato al campo è uguale a quello indicato nel filtro
   - $not: indica se il valore associato al campo è diverso da quello indicato nel filtro
   I valori presenti come dato su cui eseguire il filtro possono essere delle stringhe, dei valori numerici oppure (nel caso degli ultimi tre operatori sopra specificati) un array contenente più valori dello stesso tipo.

E' inoltre possibile unire più filtri insieme, mediante l'uso di una logica AND oppure OR. Per far ciò, la struttura della richiesta è la seguente:
"
{
	"<operatore logico>": [{<filtro1>},{<filtro2>},...]
}
 "
   
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
