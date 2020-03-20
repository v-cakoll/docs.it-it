---
title: Pubblicazione e risoluzione di nomi di peer
ms.date: 03/30/2017
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
ms.openlocfilehash: 4a0787972a61f5700d1e8728be96db8ef9ee749e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64623195"
---
# <a name="peer-name-publication-and-resolution"></a>Pubblicazione e risoluzione di nomi di peer

## <a name="publishing-a-peer-name"></a>Pubblicazione di un nome di peer  

 Per pubblicare un nuovo ID PNRP, un peer esegue le operazioni seguenti:  
  
- Invia i messaggi di pubblicazione PNRP ai suoi vicini di cache (i peer che hanno registrato ID PNRP nel livello più basso della cache) per inizializzare le rispettive cache.  
  
- Sceglie casualmente nodi nel cloud che non sono adiacenti e invia loro richieste di risoluzione dei nomi PNRP per il proprio ID P2P. Il processo di determinazione dell'endpoint risultante inizializza le cache dei nodi casuali nel cloud con l'ID PNRP del peer di pubblicazione.  
  
I nodi della versione 2 PNRP non pubblicano ID PNRP se stanno solo risolvendo altri ID P2P. Il valore del Registro di sistema HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 (tipo REG_DWORD) specifica che i peer possono usare PNRP solo per la risoluzione dei nomi e mai per la pubblicazione dei nomi. Questo valore del Registro di sistema può essere configurato anche tramite Criteri di gruppo.  
  
## <a name="resolving-a-peer-name"></a>Risoluzione di un nome di peer

 L'individuazione di altri peer in una rete o cloud PNRP è un processo costituito da due fasi:  
  
1. Determinazione dell'endpoint  
  
2. Risoluzione dell'ID PNRP  
  
 Nella fase di determinazione dell'endpoint peer, un peer che sta tentando di risolvere l'ID PNRP di un servizio in un altro computer determina l'indirizzo IPv6 di tale peer remoto.  Il peer remoto è quello che ha pubblicato o che è associato all'ID PNRP del computer o del servizio.  
  
 Dopo avere verificato che l'endpoint remoto sia stato registrato nel cloud PNRP, nella fase di risoluzione dell'ID PNRP il peer richiedente invia una richiesta dell'ID PNRP del servizio desiderato a tale endpoint. L'endpoint invia una risposta confermando l'ID PNRP del servizio, un commento e fino a 4 kilobyte di informazioni aggiuntive che il peer richiedente può usare per comunicazioni future. Ad esempio, se l'endpoint desiderato è un server di gioco, i dati dei record dei nomi di peer aggiuntivi possono contenere informazioni sul gioco, il livello e il numero attuale di giocatori.  
  
 Nella fase di determinazione dell'endpoint, PNRP usa un processo iterativo per individuare il nodo che ha pubblicato l'ID PNRP. Nel processo, il nodo che esegue la risoluzione ha il compito di contattare in successione i nodi più vicini all'ID PNRP di destinazione.  
  
 Per eseguire la risoluzione dei nomi in PNRP, il peer esamina le voci nella propria cache per individuare una voce corrispondente all'ID PNRP di destinazione. Se viene trovata, il peer invia un messaggio di richiesta PNRP al peer e attende una risposta. In caso negativo, il peer invia un messaggio di richiesta PNRP al peer che corrisponde alla voce che ha l'ID PNRP che assomiglia di più all'ID PNRP. Il nodo che riceve il messaggio di richiesta PNRP controlla nella sua cache ed esegue le operazioni seguenti:  
  
- Se trova l'ID PNRP, il peer dell'endpoint richiesto risponde direttamente al peer richiedente.  
  
- Se l'ID PNRP non viene trovato e un ID PNRP nella cache si avvicina di più all'ID PNRP di destinazione, il peer richiesto invia una risposta al peer richiedente contenente l'indirizzo IPv6 del peer che rappresenta la voce con un ID PNRP più simile all'ID PNRP di destinazione. Usando l'indirizzo IP nella risposta, il nodo richiedente invia un altro messaggio di richiesta PNRP all'indirizzo IPv6 per rispondere o esaminarne la cache.  
  
- Se non trova l'ID PNRP e se nella sua cache non è presente alcun ID PNRP più simile a quello di destinazione, il peer che ha ricevuto la richiesta invia al richiedente una risposta con la situazione accertata. Il peer richiedente sceglie quindi il secondo ID PNRP più vicino.  
  
Il peer richiedente continua questo processo con iterazioni successive, fino a individuare il nodo che ha registrato l'ID PNRP.  
  
 All'interno dello spazio dei nomi <xref:System.Net.PeerToPeer> esiste una relazione molti-a-molti tra i record <xref:System.Net.PeerToPeer.PeerName> che contengono gli endpoint e i cloud o le reti PNRP in cui comunicano. In presenza di voci duplicate o non aggiornate o di più nodi con lo stesso nome di peer, i nodi PNRP possono ottenere informazioni aggiornate usando la classe <xref:System.Net.PeerToPeer.PeerNameResolver>. I metodi <xref:System.Net.PeerToPeer.PeerNameResolver> usano un singolo nome di peer per semplificare la prospettiva per i record dei nomi uno-a-molti per i peer e uno-a-molti per i cloud. Il meccanismo è simile all'esecuzione di una query tramite un join su una tabella relazionale. Al completamento, l'oggetto Resolver restituisce un <xref:System.Net.PeerToPeer.PeerNameRecordCollection> per il nome di peer specificato.  Ad esempio, un nome di peer comparirebbe in tutti i record di nomi di peer della raccolta, ordinati in base al cloud. Queste sono le istanze del nome di peer i cui dati di supporto potrebbero essere richiesti da un'applicazione basata sul protocollo PNRP.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer>
