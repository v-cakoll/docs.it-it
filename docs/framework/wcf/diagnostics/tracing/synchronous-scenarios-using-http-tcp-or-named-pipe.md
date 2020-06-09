---
title: Scenari sincroni con trasporti HTTP, TCP o pipe con nome
ms.date: 03/30/2017
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
ms.openlocfilehash: 662067fc5564c9421ce24b28b291d06690b129ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589184"
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a>Scenari sincroni con trasporti HTTP, TCP o pipe con nome
In questo argomento vengono descritte le attività e i trasferimenti di esecuzione in vari scenari request/reply sincroni che prevedono un client a thread singolo e che utilizzano un trasporto HTTP, TCP o pipe con nome. Per altre informazioni sulle richieste multithread, vedere [scenari asincroni con http, TCP o named pipe](asynchronous-scenarios-using-http-tcp-or-named-pipe.md) .  
  
## <a name="synchronous-requestreply-without-errors"></a>Request/reply sincrono senza errori  
 Contenuto della sezione vengono descritte le attività e i trasferimenti di esecuzione in uno scenario request/reply sincrono senza errori con un client a thread singolo.  
  
### <a name="client"></a>Client  
  
#### <a name="establishing-communication-with-service-endpoint"></a>Apertura delle comunicazioni con un endpoint di servizio  
 Un client viene costruito e aperto. Per ognuno di questi passaggi, l'attività di ambiente (A) viene trasferita rispettivamente a un'attività "Costruisci client" (B) e "Apri client" (C). Ogni volta che viene trasferita a un'altra attività, l'attività di ambiente viene sospesa fino al trasferimento di restituzione, ovvero fino all'esecuzione del codice di ServiceModel.  
  
#### <a name="making-a-request-to-service-endpoint"></a>Invio di una richiesta all'endpoint di servizio  
 L'attività di ambiente viene trasferita a un'attività "ProcessAction" (D). Questa attività prevede l'invio di un messaggio di richiesta e la ricezione di un messaggio di risposta. L'attività termina quando il controllo viene restituito al codice utente. Poiché si tratta di una richiesta sincrona, l'attività di ambiente viene sospesa fino alla restituzione del controllo.  
  
#### <a name="closing-communication-with-service-endpoint"></a>Chiusura delle comunicazioni con un endpoint di servizio  
 L'attività di chiusura del client (I) viene creata a partire dall'attività di ambiente. Il comportamento è identico a quelli di apertura e di creazione.  
  
### <a name="server"></a>Server  
  
#### <a name="setting-up-a-service-host"></a>Configurazione di un ServiceHost  
 Le attività di creazione (N) e di apertura (O) di ServiceHost vengono create a partire dall'attività di ambiente (M).  
  
 Un'attività di listener (P) viene creata tramite l'apertura di un ServiceHost per ogni listener. L'attività di listener attende la ricezione e l'elaborazione dei dati.  
  
#### <a name="receiving-data-on-the-wire"></a>Ricezione di dati in transito  
 Quando i dati arrivano in rete, viene creata un'attività "ReceiveBytes" se non esiste già (Q) per elaborare i dati ricevuti. Inoltre, questa attività può essere riutilizzata per più messaggi appartenenti a una connessione o a una coda.  
  
 Se dispone di una quantità sufficiente di dati per formare un messaggio di azione SOAP, l'attività "ReceiveBytes" avvia un'attività "ProcessMessage" (R).  
  
 L'attività R prevede l'elaborazione delle intestazioni di messaggio e la verifica dell'intestazione activityID. Se questa intestazione è presente, l'ID attività viene impostato sull'attività "ProcessAction". In caso contrario, viene creato un nuovo ID.  
  
 Quando la chiamata viene elaborata, l'attività ProcessAction (S) viene creata e l'esecuzione viene trasferita a tale attività. Questa attività termina al completamento di ogni elaborazione relativa al messaggio in ingresso, compresa l'esecuzione del codice utente (T) e, se necessario, l'invio del messaggio di risposta.  
  
#### <a name="closing-a-service-host"></a>Chiusura di un ServiceHost  
 L'attività di chiusura di un ServiceHost (Z) viene creata a partire dall'attività di ambiente.  
  
 ![Diagramma che mostra scenari sincroni: HTTP, TCP o named pipe.](./media/synchronous-scenarios-using-http-tcp-or-named-pipe/synchronous-scenario-http-tcp-named-pipes.gif)  
  
 In \<A: name> , `A` è un simbolo di collegamento che descrive l'attività nel testo precedente e nella tabella 3. mentre `Name` è un nome abbreviato dell'attività.  
  
 Se `propagateActivity` = `true` , l'azione elabora sul client e sul servizio hanno lo stesso ID attività.  
  
## <a name="synchronous-requestreply-with-errors"></a>Request/reply sincrono con errori  
 L'unica differenza rispetto allo scenario precedente è che viene restituito un messaggio di errore SOAP come messaggio di risposta. Se `propagateActivity` = `true` , l'ID attività del messaggio di richiesta viene aggiunto al messaggio di errore SOAP.  
  
## <a name="synchronous-one-way-without-errors"></a>Unidirezionale sincrono senza errori  
 L'unica differenza rispetto al primo scenario è che non viene restituito alcun messaggio al server. Inoltre, per i protocolli basati su HTTP, il sistema invia al client uno stato che indica l'eventuale presenza di errori. Questo è dovuto al fatto che HTTP è l'unico protocollo con una semantica di richiesta-risposta che fa parte dello stack del protocollo WCF. Poiché l'elaborazione TCP è nascosta da WCF, nessun riconoscimento viene inviato al client.  
  
## <a name="synchronous-one-way-with-errors"></a>Unidirezionale sincrono con errori  
 Se durante l'elaborazione del messaggio (Q o successivo) si verifica un errore, al client non viene restituita alcuna notifica. Questo comportamento è identico allo scenario "Sincrono unidirezionale senza errori". Se si desidera ricevere un messaggio di errore, evitare di utilizzare uno scenario unidirezionale.  
  
## <a name="duplex"></a>Duplex  
 La differenza rispetto agli scenari precedenti è che il client, analogamente a un servizio di uno scenario asincrono, crea le attività "ReceiveBytes" e "ProcessMessage".
