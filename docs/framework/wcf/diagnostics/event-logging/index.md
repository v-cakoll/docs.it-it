---
title: Registrazione eventi in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: 0c74b93be026007a5593372c938cf73e08fafb15
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797804"
---
# <a name="event-logging-in-wcf"></a>Registrazione eventi in WCF
Windows Communication Foundation (WCF) traccia gli eventi interni nel registro eventi di Windows.  
  
## <a name="viewing-event-logs"></a>Visualizzazione dei registri eventi  
 La registrazione degli eventi è abilitata automaticamente per impostazione predefinita e non è disponibile un meccanismo per disabilitarlo. Gli eventi registrati da WCF possono essere visualizzati usando il Visualizzatore eventi. Per avviare lo strumento, fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, fare doppio clic su **strumenti di amministrazione**, quindi fare doppio clic su **Visualizzatore eventi**.  
  
### <a name="application-event-log"></a>Registro eventi dell'applicazione  
 Il **registro eventi dell'applicazione** contiene la maggior parte degli eventi generati da WCF. La maggior parte delle voci riguardano errori nell'avvio di una particolare funzionalità per un'applicazione. Ecco alcuni esempi:  
  
- Registrazione/traccia messaggi: WCF scrive un evento nel registro eventi quando la registrazione dei messaggi e della traccia non riesce. Tuttavia, non tutti gli errori di traccia generano un evento. Per evitare che il registro eventi venga completamente riempito con errori di traccia, WCF implementa un periodo di blackout di 10 minuti per tale evento. Ciò significa che se WCF scrive un errore di traccia nel registro eventi, questa operazione non verrà eseguita di nuovo per almeno 10 minuti.  
  
- Listener condiviso: Il servizio di condivisione porte TCP WCF registra un evento quando l'avvio non riesce.  
  
- CardSpace Registra gli eventi quando il servizio non viene avviato.  
  
- Eventi critici e di errore, quali errori di avvio o arresti anomali del sistema  
  
- Registrazione messaggi attivata: Registra gli eventi quando la registrazione dei messaggi è attivata. Questa funzionalità consente di notificare all'amministratore che informazioni riservate specifiche dell'applicazione possono essere registrate nelle intestazioni e nel corpo del messaggio.  
  
- Viene registrato un evento quando è impostato l'attributo `enableLoggingKnownPII` dell'elemento `machineSettings` nel file `machine.config`. Questo attributo specifica se un'applicazione in esecuzione sul computer può registrare informazioni che consentono l'identificazione personale (PII).  
  
- Se l'attributo `logKnownPii` nel file `app.config` o `web.config` è impostato su `true` affinché un'applicazione specifica attivi la registrazione delle informazioni che consentono l'identificazione personale, ma l'attributo `enableLoggingKnownPII` nell'elemento `machineSettings` del file `machine.config` è impostato su `false`, viene registrato un evento. In aggiunta, se `logKnownPii` e `enableLoggingKnownPII` sono impostati su `true` viene registrato un evento. Per ulteriori informazioni su queste impostazioni di configurazione, vedere la sezione sicurezza dell'argomento [configurazione della registrazione dei messaggi](../configuring-message-logging.md) .  
  
### <a name="security-event-log"></a>Registro eventi di sicurezza  
 Il **registro eventi di sicurezza** contiene gli eventi di controllo di sicurezza registrati da WCF.  
  
### <a name="system-event-log"></a>Registro eventi di sistema  
 WCF non registra alcun elemento nel **registro eventi di sistema**.  
  
### <a name="event-log-entries"></a>Voci del registro eventi  
 L' **origine** di un evento è il nome dell'assembly che genera la voce di log.  
  
 Il tipo di una voce del registro eventi consente di determinare la gravità di una voce. Ogni evento deve appartenere a un solo tipo, che l'applicazione indica quando riferisce l'evento. Il Visualizzatore eventi utilizza tale tipo per scegliere l'icona da visualizzare nella vista elenco del registro. Per i diversi tipi di evento di una voce del registro eventi, vedere <xref:System.Diagnostics.EventLogEntryType>.  
  
 Quando si fa clic su "ulteriori informazioni" durante la visualizzazione di un evento nella Visualizzatore eventi, è possibile che l'Visualizzatore eventi invii informazioni attraverso Internet. Per ulteriori informazioni, vedere la Guida del Visualizzatore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Amministrazione e diagnostica](../index.md)
- [Riferimenti generali sugli eventi](events-general-reference.md)
