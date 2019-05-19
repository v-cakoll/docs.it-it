---
title: Scenari asincroni con trasporti HTTP, TCP o pipe con nome
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 48957ec0abd1b4b0623f9b613fcd94912a38845b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881658"
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
  
 Se `propagateActivity` = `true`, ProcessMessage indica l'attività processaction nella quale da trasferire.  
  
 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di HTTP  
 Se `propagateActivity` = `false` su un lato, ProcessMessage non indica attività processaction nella quale da trasferire. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Client asincrono senza callback in cui propagateActivity è impostata su false in entrambi i lati.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  
    
 Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.  
  
 Un'attività Processaction viene creata in un client asincrono quando `propagateActivity` = `false` nel chiamante o chiamato e quando il messaggio di risposta non include un'intestazione Action.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>La propagazione è attivata su entrambi i lati, con l'utilizzo di TCP o named pipe  
 ![Client asincrono senza callback in cui propagateActivity è impostata a true su entrambi i lati e named pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Simile alla prima immagine, se `propagateActivity` = `true`, ProcessMessage indica l'attività processaction nella quale da trasferire.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>La propagazione è disattivata su uno dei due lati, con l'utilizzo di TCP o named pipe  
 Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.  
  
 Simile alla seconda immagine, se `propagateActivity` = `false` su un lato, ProcessMessage non indica attività processaction nella quale da trasferire. Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID. Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale. L'effettiva attività ProcessAction può essere trasferita con tale ID.  
  
 ![Client asincrono senza callback, in cui propagateActivity è impostato su false in entrambi i lati e denominato pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  
    
### <a name="asynchronous-client-with-callback"></a>Client asincrono con callback  
 Questo scenario aggiunge attività G e A', per il callback e `endCall`, e i rispettivi trasferimenti dentro/fuori.  
  
 In questa sezione illustra solo tramite HTTP con `propragateActivity` = `true`. Tuttavia, altre attività e trasferimenti si applicano anche agli altri casi (vale a dire `propagateActivity` = `false`, utilizzo di TCP o Named Pipe).  
  
 Il callback crea un'attività nuova (G) quando il client chiama codice utente per notificare che i risultati sono pronti. Il codice utente chiama quindi `endCall` all'interno del callback (come mostrato in Figura 5) o fuori del callback (Figura 6). Poiché non è possibile sapere quale attività dell'utente `endCall` viene chiamato da questa attività viene etichettata `A’`. È possibile che A' sia identico ad A o diverso.  
  
 ![Viene illustrato un client asincrono con callback, endcall in callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  
    
 ![Viene illustrato un client asincrono con callback, endcall all'esterno di callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  
    
### <a name="asynchronous-server-with-callback"></a>Server asincrono con callback  
 ![Viene illustrato un server asincrono con callback.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  
    
 Le stack dei canali richiama il client in Messaggio Ricevere: le tracce di questa elaborazione vengono create nell'attività ProcessRequest stessa.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Request/Reply asincroni con errori  
 I messaggi di errore vengono ricevuti durante `endCall`. In caso contrario, attività e trasferimenti sono simili agli scenari precedenti.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Unidirezionale asincrono con o senza errori  
 Al client non vengono restituite risposte né errori.
