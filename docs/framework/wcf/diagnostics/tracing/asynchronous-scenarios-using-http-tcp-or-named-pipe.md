---
title: Scenari asincroni con trasporti HTTP, TCP o pipe con nome
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 6ae96c0aac5010adf37eb78ed57d1549885ece58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185776"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Scenari asincroni con trasporti HTTP, TCP o pipe con nome
In questo argomento vengono descritti attività e trasferimenti per vari scenari Request/Reply asincroni, con richieste multithreading che utilizzano HTTP, TCP o named pipe.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Request/Reply asincroni senza errori  
 Contenuto della sezione vengono descritti attività e trasferimenti per uno scenario Request/Reply asincrono, con client multithreading.  
  
 L'attività del chiamante termina quando viene restituito `beginCall` e viene restituito `endCall`. Se viene chiamato un callback, viene restituito il callback.  
  
 L'attività chiamata termina quando viene restituito `beginCall`, viene restituito `endCall` o quando viene restituito il callback, se chiamato da tale attività.  
  
### <a name="asynchronous-client-without-callback"></a>Client asincrono senza callback  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>La propagazione è attivata su entrambi i lati, con l'utilizzo di HTTP  
 ![Client asincrono senza callback in cui propagateActivity è impostato su true su entrambi i lati.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 Se `propagateActivity=true`, ProcessMessage indica l'attività ProcessAction a cui eseguire il trasferimento.  
  
 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di HTTP  
 Se `propagateActivity=false` su entrambi i lati, ProcessMessage non indica l'attività ProcessAction a cui eseguire il trasferimento. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Client asincrono senza callback in cui propagateActivity è impostato su false su entrambi i lati.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
 Un'attività Di elaborazione azione `propagateActivity=false` viene creata in un client asincrono quando si trova al chiamante o al destinatario della chiamata e quando il messaggio di risposta non include un'intestazione Action.A Process Action activity is created on an asynchronous client when at the caller or callee e when the response message does not include an Action header.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>La propagazione è attivata su entrambi i lati, con l'utilizzo di TCP o named pipe  
 ![Client asincrono senza callback in cui propagateActivity è impostata su true su entrambi i lati e named pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Simile alla prima immagine, if `propagateActivity=true`, ProcessMessage indica a quale attività ProcessAction trasferire.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di TCP o named pipe  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Simile alla seconda immagine, se `propagateActivity=false` su entrambi i lati, ProcessMessage non indica l'attività ProcessAction a cui eseguire il trasferimento. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Client asincrono senza callback in cui propagateActivity è impostato su false su entrambi i lati e named pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a>Client asincrono con callback  
 Questo scenario aggiunge attività G e A', per il callback e `endCall`, e i rispettivi trasferimenti dentro/fuori.  
  
 In questa sezione viene `propagateActivity` = `true`illustrato solo l'utilizzo di HTTP con . Tuttavia, le attività e i trasferimenti aggiuntivi `propagateActivity` = `false`si applicano anche agli altri casi, ovvero , utilizzando TCP o Named-Pipe.  
  
 Il callback crea un'attività nuova (G) quando il client chiama codice utente per notificare che i risultati sono pronti. Il codice utente chiama quindi `endCall` all'interno del callback (come mostrato in Figura 5) o fuori del callback (Figura 6). Poiché non è noto quale attività `endCall` utente viene `A’`chiamata da, questa attività viene etichettata come . È possibile che A' sia identico ad A o diverso.  
  
 ![Mostra un client asincrono con callback, endcall in callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Mostra un client asincrono con callback, endcall esterno callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a>Server asincrono con callback  
 ![Mostra un server asincrono con callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 Le stack dei canali richiama il client in Messaggio Ricevere: le tracce di questa elaborazione vengono create nell'attività ProcessRequest stessa.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Request/Reply asincroni con errori  
 I messaggi di errore vengono ricevuti durante `endCall`. In caso contrario, attività e trasferimenti sono simili agli scenari precedenti.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Unidirezionale asincrono con o senza errori  
 Al client non vengono restituite risposte né errori.
