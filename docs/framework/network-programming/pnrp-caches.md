---
title: Cache PNRP
ms.date: 03/30/2017
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
ms.openlocfilehash: 3ed3e11e702c8933b500421de5654b212cdd80d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64622987"
---
# <a name="pnrp-caches"></a>Cache PNRP
Le cache PNRP (Peer Name Resolution Protocol) sono raccolte locali di endpoint peer selezionati tramite algoritmo e mantenuti disponibili nel peer.  
  
## <a name="pnrp-cache-initialization"></a>Inizializzazione della cache PNRP  
 Per inizializzare la cache PNRP, o raccolta di record di nomi di peer, un nodo di peer può usare i metodi seguenti all'avvio:  
  
- Le voci di cache persistenti presenti al momento della chiusura del nodo vengono caricate dallo spazio di archiviazione su disco rigido.  
  
- Se un'applicazione usa l'infrastruttura di collaborazione P2P, le informazioni di collaborazione sono disponibili in Gestione contatto per il nodo.  
  
## <a name="scaling-peer-name-resolution-with-a-multi-level-cache"></a>Scalabilità della risoluzione dei nomi di peer con una cache multilivello  
 Per limitare le dimensioni delle cache PNRP, i nodi di peer usano una cache multilivello, nella quale ciascun livello contiene un numero massimo di voci. Ogni livello della cache rappresenta un decimo dello spazio del numero ID PNRP (2<sup>256</sup>). Il livello minimo presente nella cache contiene un ID PNRP registrato localmente e altri ID PNRP numericamente vicini. Quando un livello di cache risulta riempito con il massimo di 20 voci, viene creato un nuovo livello inferiore. Il numero massimo di livelli della cache è nell'ordine di log10(Numero totale di ID PNRP nel cloud). Ad esempio, per un cloud globale con 100 milioni di ID PNRP, nella cache non vi sono più di 8 (=log10(100.000.000)) livelli e un numero simile di hop per risolvere un ID PNRP durante la risoluzione dei nomi. Questo meccanismo consente una tabella hash distribuita per la quale un ID PNRP arbitrario può essere risolto inoltrando messaggi di richiesta PNRP al successivo peer più vicino fino al reperimento del peer con il CPA corrispondente.  
  
 Per garantire il completamento della risoluzione, ogni volta che un nodo aggiunge una voce al livello più basso della sua cache, invia una copia della stessa a tutti i nodi nell'ultimo livello della cache.  
  
 Le voci della cache vengono aggiornate nel corso del tempo, mentre quelle non aggiornate vengono rimosse. Di conseguenza, la tabella hash distribuita di ID PNRP si basa su endpoint attivi, diversamente da DNS in cui i record di indirizzo e il protocollo DNS non garantiscono che il nodo associato all'indirizzo sia attivamente in rete.  
  
## <a name="other-pnrp-caches"></a>Altre cache PNRP  
 Un altro archivio dati permanente è la cache locale.  Oltre agli altri oggetti necessari per l'attività PNRP, esso può includere i record associati a un cloud o una sessione di collaborazione PNRP pubblicata e sincronizzata tra tutti i membri del cloud in modo sicuro. Questo archivio replicato rappresenta la visualizzazione dei dati del gruppo, che dovrebbero essere uguali per tutti i membri del gruppo. Tecnicamente, questi oggetti non sono record di per sé, ma piuttosto dati dell'applicazione, di presenza e di oggetti destinati a una cache locale. L'uso del cloud PNRP garantisce che gli oggetti vengano propagati a tutti i nodi nella sessione di collaborazione o nel cloud PNRP.  La replica dei record tra i membri del cloud usa SSL per fornire la crittografia e l'integrità dei dati.  
  
 Quando un peer viene aggiunto a un cloud, non riceve automaticamente i dati nella cache locale dal peer host a cui si collega, ma deve sottoscrivere il peer host per ricevere gli aggiornamenti nei dati dell'applicazione, di presenza e di oggetti. Dopo la sincronizzazione iniziale, i peer risincronizzano periodicamente i rispettivi archivi replicati per garantire che tutti i membri del gruppo dispongano in modo coerente della stessa vista.  Anche la sessione di collaborazione o le applicazioni all'interno della sessione di collaborazione possono svolgere la stessa funzione.  
  
 Dopo l'avvio di una sessione di collaborazione per un cloud, le applicazioni possono registrare i peer e iniziare a pubblicare le informazioni usando il livello di sicurezza definito dall'ambito del cloud. Quando un peer viene aggiunto a un cloud, i meccanismi di sicurezza per il cloud vengono applicati al peer, assegnandogli un ambito per la partecipazione.  I record del peer possono quindi essere pubblicati in modo sicuro all'interno dell'ambito del cloud. Si noti che l'ambito del cloud potrebbe non essere lo stesso dell'ambito di applicazione della collaborazione.  
  
 I peer possono registrare l'interesse a ricevere oggetti da altri peer. Quando viene aggiornato un oggetto, l'applicazione di collaborazione riceve una notifica e il nuovo oggetto viene passato a tutti i sottoscrittori dell'applicazione. Ad esempio, un peer in un'applicazione di chat di gruppo può registrare l'interesse a ricevere informazioni dell'applicazione, che invierà quindi al peer tutti i record di chat come dati dell'applicazione.  Ciò consente di monitorare l'attività di chat all'interno del cloud.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer>
