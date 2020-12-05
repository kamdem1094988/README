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
                
                 le statistiche possono esssere fatti  e sono in patricolare specificato la data e la zona 
 degli esemepi di  formati JSON possono essere fatti  nel seguente modo 
                
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
 
 **domain**
 **b**
