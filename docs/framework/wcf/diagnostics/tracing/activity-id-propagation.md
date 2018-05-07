---
title: Propagazione di ID attività
ms.date: 03/30/2017
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
ms.openlocfilehash: e51970f693d9ca2d2f81bf4efc97969896de4828
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="activity-id-propagation"></a>Propagazione di ID attività
La propagazione si verifica quando la traccia attività ServiceModel viene attivata (propagazione di ServiceModel) o disattivata (propagazione di attività utente-utente).  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a>Traccia attività ServiceModel attivata  
 Se la traccia attività ServiceModel è attivata, la propagazione si verifica tra le attività ProcessAction.  
  
### <a name="server"></a>Server  
 Quando il `propagateActivity` attributo è impostato su `true` su entrambi client e server, l'ID del `ProcessAction` attività nel server è identico all'ID nel propagato `ActivityId` intestazione del messaggio.  
  
 Se non si `ActivityId` intestazione è presente nel messaggio (vale a dire `propagateActivity` = `false` sul client), o quando `propagateActivity` = `false` sul server, il server genera un nuovo ID di attività.  
  
### <a name="client"></a>Client  
 Se il client è a thread singolo in modalità sincrona, ignora qualsiasi impostazione di `propagateActivity` sul client o sul server. La risposta viene invece gestita nell'attività di richiesta. Se il client può essere sincrona o asincrona con multithreading, `propagateActivity` = `true` nel client e vi è un'intestazione ID attività nel messaggio inviato dal server, il client recupera l'ID attività dal messaggio e lo trasferisce al Attività elaborazione azione che contiene l'ID attività propagato. In caso contrario, il client esegue il trasferimento dall'attività Elaborazione messaggio a una nuova attività Elaborazione azione. Questo ulteriore trasferimento a una nuova attività Elaborazione azione viene eseguito per coerenza. In questa attività, il client recupera l'ID attività dell'attività BeginCall dal contesto del thread locale, quando il thread viene allocato per l'elaborazione del messaggio di risposta. Trasferisce quindi tale ID all'attività Elaborazione azione.  
  
 Se il client è duplex, agisce da server alla ricezione del messaggio.  
  
### <a name="propagation-in-fault-messages"></a>Propagazione nei messaggi di errore  
 Non c'è differenza nello gestire messaggi validi e di errore. Se `propagateActivity` = `true`, l'ID attività aggiunto alle intestazioni di messaggio di errore SOAP è identico all'attività dell'ambiente.  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a>Traccia attività ServiceModel disattivata  
 Se la traccia attività ServiceModel è disattivata, la propagazione si verifica direttamente tra le attività del codice utente, senza passare per le attività ServiceModel. Viene inoltre propagato un ID attività definito dall'utente tramite l'intestazione ID attività del messaggio.  
  
 Se `propagateActivity` = `true` e `ActivityTracing` = `off` per un listener di traccia ServiceModel (indipendentemente dal fatto se è attivata su ServiceModel), sul client o server si verifica quanto segue:  
  
-   Alla richiesta di un'operazione o all'invio di una risposta, l'ID attività in TLS viene propagato fuori dal codice utente fino a quando non viene formato un messaggio. Viene inoltre inserita un'intestazione ID attività nel messaggio prima dell'invio.  
  
-   Alla ricezione di una richiesta o una risposta, l'ID attività viene recuperato dall'intestazione del messaggio non appena viene creato l'oggetto messaggio. L'ID attività in TLS viene propagato non appena il messaggio scompare dall'ambito, fino a quando non viene raggiunto il codice utente.  
  
 Questa garanzia delle azioni che le tracce dell'utente saranno visualizzate nella stessa attività se la propagazione è su. Tuttavia, non costituisce per le tracce ServiceModel. Le tracce ServiceModel si verificano in un'attività del codice utente solo se l'elaborazione di tali tracce viene eseguita sullo stesso thread dove l'attività del codice utente è impostata.  
  
 In generale, le traccie ServiceModel possono essere osservate nelle posizioni seguenti:  
  
-   Se la traccia ServiceModel è disattivata, tutte le tracce emesse vengono visualizzate in attività utente. Se la propagazione è attivata sul server e sul client, queste tracce si troveranno nella stessa attività.  
  
-   Se la traccia ServiceModel è attivata, ma ActivityTracing è disattivata, le tracce utente verranno visualizzate nella stessa attività, se la propagazione è attivata su entrambe le estremità. Le tracce ServiceModel si trovano nell'attività 0000 predefinita, a meno che non si verifichino nello stesso thread dell'elaborazione del codice utente in cui l'attività è inizialmente impostata.  
  
-   Se entrambe le tracce ServiceModel e ActivityTracing sono attivate, le traccie dell'utente sono visualizzate in attività definite dall'utente e le traccie ServiceModel sono visualizzate in attività definite da ServiceModel. La propagazione si verificherà a livello di ServiceModel.
