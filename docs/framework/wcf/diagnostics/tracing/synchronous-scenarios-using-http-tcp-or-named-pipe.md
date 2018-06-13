---
title: Scenari sincroni con trasporti HTTP, TCP o pipe con nome
ms.date: 03/30/2017
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
ms.openlocfilehash: 11a5d8f43d12d35728c65c7a60ad8a4fa2fc1b3a
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810174"
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a>Scenari sincroni con trasporti HTTP, TCP o pipe con nome
In questo argomento vengono descritte le attività e i trasferimenti di esecuzione in vari scenari request/reply sincroni che prevedono un client a thread singolo e che utilizzano un trasporto HTTP, TCP o pipe con nome. Vedere [scenari asincroni con HTTP, TCP o Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md) per ulteriori informazioni sulle richieste a thread multipli.  
  
## <a name="synchronous-requestreply-without-errors"></a>Request/reply sincrono senza errori  
 Contenuto della sezione vengono descritte le attività e i trasferimenti di esecuzione in uno scenario request/reply sincrono senza errori con un client a thread singolo.  
  
### <a name="client"></a>Client  
  
#### <a name="establishing-communication-with-service-endpoint"></a>Apertura delle comunicazioni con un endpoint di servizio  
 Un client viene costruito e aperto. Per ognuno di questi passaggi, l'attività di ambiente (A) viene trasferita a un "Costruzione Client" (B) e "Apertura Client" (C) attività rispettivamente. Ogni volta che viene trasferita a un'altra attività, l'attività di ambiente viene sospesa fino al trasferimento di restituzione, ovvero fino all'esecuzione del codice di ServiceModel.  
  
#### <a name="making-a-request-to-service-endpoint"></a>Invio di una richiesta all'endpoint di servizio  
 L'attività di ambiente viene trasferita a un'attività "ProcessAction" (D). Questa attività prevede l'invio di un messaggio di richiesta e la ricezione di un messaggio di risposta. L'attività termina quando il controllo viene restituito al codice utente. Poiché si tratta di una richiesta sincrona, l'attività di ambiente viene sospesa fino alla restituzione del controllo.  
  
#### <a name="closing-communication-with-service-endpoint"></a>Chiusura delle comunicazioni con un endpoint di servizio  
 L'attività di chiusura del client (I) viene creata a partire dall'attività di ambiente. Il comportamento è identico a quelli di apertura e di creazione.  
  
### <a name="server"></a>Server  
  
#### <a name="setting-up-a-service-host"></a>Configurazione di un ServiceHost  
 Le attività di creazione (N) e di apertura (O) di ServiceHost vengono create a partire dall'attività di ambiente (M).  
  
 Un'attività di listener (P) viene creata tramite l'apertura di un ServiceHost per ogni listener. L'attività di listener attende la ricezione e l'elaborazione dei dati.  
  
#### <a name="receiving-data-on-the-wire"></a>Ricezione di dati in transito  
 All'arrivo dei dati in transito, un'attività "ReceiveBytes" viene creata se non esiste già (Q) per elaborare i dati ricevuti. Inoltre, questa attività può essere riutilizzata per più messaggi appartenenti a una connessione o a una coda.  
  
 Se dispone di una quantità sufficiente di dati per formare un messaggio di azione SOAP, l'attività "ReceiveBytes" avvia un'attività "ProcessMessage" (R).  
  
 L'attività R prevede l'elaborazione delle intestazioni di messaggio e la verifica dell'intestazione activityID. Se questa intestazione è presente, l'ID attività viene impostato sull'attività "ProcessAction". In caso contrario, viene creato un nuovo ID.  
  
 Quando la chiamata viene elaborata, l'attività ProcessAction (S) viene creata e l'esecuzione viene trasferita a tale attività. Questa attività termina al completamento di ogni elaborazione relativa al messaggio in ingresso, compresa l'esecuzione del codice utente (T) e, se necessario, l'invio del messaggio di risposta.  
  
#### <a name="closing-a-service-host"></a>Chiusura di un ServiceHost  
 L'attività di chiusura di un ServiceHost (Z) viene creata a partire dall'attività di ambiente.  
  
 ![Scenari sincroni con HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/sync.gif "sincronizzazione")  
  
 In \<a: name >, `A` è un simbolo di scelta rapida che descrive l'attività contenuta nel testo precedente e nella tabella 3. mentre `Name` è un nome abbreviato dell'attività.  
  
 Se `propagateActivity` = `true`, elaborazione azione nel client e servizio hanno lo stesso ID di attività.  
  
## <a name="synchronous-requestreply-with-errors"></a>Request/reply sincrono con errori  
 L'unica differenza rispetto allo scenario precedente è che viene restituito un messaggio di errore SOAP come messaggio di risposta. Se `propagateActivity` = `true`, l'ID attività del messaggio di richiesta viene aggiunta al messaggio di errore SOAP.  
  
## <a name="synchronous-one-way-without-errors"></a>Unidirezionale sincrono senza errori  
 L'unica differenza rispetto al primo scenario è che non viene restituito alcun messaggio al server. Inoltre, per i protocolli basati su HTTP, il sistema invia al client uno stato che indica l'eventuale presenza di errori. Infatti, quest'ultimo è l'unico protocollo avente una semantica request / reply che fa parte dello stack di protocolli WCF. Poiché l'elaborazione TCP è nascosta da WCF, viene inviato alcun acknowledgement al client.  
  
## <a name="synchronous-one-way-with-errors"></a>Unidirezionale sincrono con errori  
 Se durante l'elaborazione del messaggio (Q o successivo) si verifica un errore, al client non viene restituita alcuna notifica. Questo comportamento è identico allo scenario "Sincrono unidirezionale senza errori". Se si desidera ricevere un messaggio di errore, evitare di utilizzare uno scenario unidirezionale.  
  
## <a name="duplex"></a>Duplex  
 La differenza rispetto agli scenari precedenti è che il client, analogamente a un servizio di uno scenario asincrono, crea le attività "ReceiveBytes" e "ProcessMessage".
