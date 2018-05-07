---
title: Scenari asincroni con trasporti HTTP, TCP o pipe con nome
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: d08f70186a59b8717c4441167ee720ba1c20b9dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Scenari asincroni con trasporti HTTP, TCP o pipe con nome
In questo argomento vengono descritti attività e trasferimenti per vari scenari Request/Reply asincroni, con richieste multithreading che utilizzano HTTP, TCP o named pipe.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Request/Reply asincroni senza errori  
 Contenuto della sezione vengono descritti attività e trasferimenti per uno scenario Request/Reply asincrono, con client multithreading.  
  
 L'attività del chiamante termina quando viene restituito `beginCall` e viene restituito `endCall`. Se viene chiamato un callback, viene restituito il callback.  
  
 L'attività chiamata termina quando viene restituito `beginCall`, viene restituito `endCall` o quando viene restituito il callback, se chiamato da tale attività.  
  
### <a name="asynchronous-client-without-callback"></a>Client asincrono senza callback  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>La propagazione è attivata su entrambi i lati, con l'utilizzo di HTTP  
 ![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")  
  
 Figura 1. Client asincrono, senza callback, `propagateActivity` = `true` su entrambi i lati, HTTP  
  
 Se `propagateActivity` = `true`, ProcessMessage indica l'attività ProcessAction da trasferire.  
  
 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di HTTP  
 Se `propagateActivity` = `false` su un lato, ProcessMessage non indica l'attività ProcessAction da trasferire. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Scenari asincroni con HTTP&#47;TCP&#47;Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")  
  
 Figura 2. Client asincrono, senza callback, `propagateActivity` = `false` su entrambi i lati, HTTP  
  
 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
 Un'attività elaborazione azione viene creata in un client asincrono quando `propagateActivity` = `false` nel chiamante o chiamato e quando il messaggio di risposta non include un'intestazione Action.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>La propagazione è attivata su entrambi i lati, con l'utilizzo di TCP o named pipe  
 ![Scenari asincroni con HTTP&#47;TCP&#47;Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")  
  
 Figura 3. Client asincrono, senza callback, `propagateActivity` = `true` su entrambi i lati, Named Pipe/TCP  
  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Come nella figura 1, se `propagateActivity` = `true`, ProcessMessage indica l'attività ProcessAction da trasferire.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di TCP o named pipe  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Come nella figura 2, se `propagateActivity` = `false` su un lato, ProcessMessage non indica l'attività ProcessAction da trasferire. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Scenari asincroni con HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")  
  
 Figura 4. Client asincrono, senza callback, `propagateActivity` = `false` su entrambi i lati, Named Pipe/TCP  
  
### <a name="asynchronous-client-with-callback"></a>Client asincrono con callback  
 Questo scenario aggiunge attività G e A', per il callback e `endCall`, e i rispettivi trasferimenti dentro/fuori.  
  
 Questa sezione viene illustrata solo l'utilizzo di HTTP con `propragateActivity` = `true`. Tuttavia, l'attività e trasferimenti aggiuntivi si applicano anche agli altri casi (ovvero, `propagateActivity` = `false`, utilizzando TCP o Named Pipe).  
  
 Il callback crea un'attività nuova (G) quando il client chiama codice utente per notificare che i risultati sono pronti. Il codice utente chiama quindi `endCall` all'interno del callback (come mostrato in Figura 5) o fuori del callback (Figura 6). Poiché non è noto quale attività utente `endCall` viene chiamata da questa attività viene etichettata `A’`. È possibile che A' sia identico ad A o diverso.  
  
 ![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")  
  
 Figura 5. Client asincrono con callback, `endCall` all'interno del callback  
  
 ![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")  
  
 Figura 6. Client asincrono con callback, `endCall` esternamente al callback  
  
### <a name="asynchronous-server-with-callback"></a>Server asincrono con callback  
 ![Scenari asincroni con HTTP&#47;TCP&#47; denominato&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")  
  
 Figura 7. Server asincrono con callback  
  
 Le stack dei canali richiama il client in Messaggio Ricevere: le tracce di questa elaborazione vengono create nell'attività ProcessRequest stessa.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Request/Reply asincroni con errori  
 I messaggi di errore vengono ricevuti durante `endCall`. In caso contrario, attività e trasferimenti sono simili agli scenari precedenti.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Unidirezionale asincrono con o senza errori  
 Al client non vengono restituite risposte né errori.
