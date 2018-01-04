---
title: Registrazione eventi in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4028772caef8e5c0301ab3a6a0bde2f180d821ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="event-logging-in-wcf"></a>Registrazione eventi in WCF
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tiene traccia degli eventi interni nel registro eventi di Windows.  
  
## <a name="viewing-event-logs"></a>Visualizzazione dei registri eventi  
 La registrazione degli eventi è abilitata automaticamente per impostazione predefinita e non è disponibile un meccanismo per disabilitarlo. Gli eventi registrati da [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] possono essere visualizzati utilizzando il Visualizzatore eventi. Per avviare questo strumento, fare clic su **avviare**, fare clic su **Pannello di controllo**, fare doppio clic su **strumenti di amministrazione**, quindi fare doppio clic su **Visualizzatore eventi**.  
  
### <a name="application-event-log"></a>Registro eventi dell'applicazione  
 Il **registro eventi dell'applicazione** contiene la maggior parte degli eventi generati da [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. La maggior parte delle voci riguardano errori nell'avvio di una particolare funzionalità per un'applicazione. Gli esempi includono:  
  
-   Registrazione/traccia dei messaggi: [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scrive un evento nel registro eventi quando si verificano errori nella traccia e nella registrazione dei messaggi. Tuttavia, non tutti gli errori di traccia generano un evento. Per impedire che il registro eventi venga riempito completamente da errori di traccia, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] implementa un periodo di blackout di 10 minuti per questo tipo di evento. Pertanto, se [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scrive un errore di traccia nel registro eventi, non ripeterà questa operazione per almeno 10 minuti.  
  
-   Listener condiviso: il servizio di condivisione porte TCP WCF registra un evento quando non può essere avviato.  
  
-   [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: registra eventi quando il servizio non può essere avviato.  
  
-   Eventi critici e di errore, quali errori di avvio o arresti anomali del sistema  
  
-   Registrazione messaggi attivata: gli eventi vengono registrati quando la registrazione dei messaggi è attivata. Questa funzionalità consente di notificare all'amministratore che informazioni riservate specifiche dell'applicazione possono essere registrate nelle intestazioni e nel corpo del messaggio.  
  
-   Viene registrato un evento quando è impostato l'attributo `enableLoggingKnownPII` dell'elemento `machineSettings` nel file `machine.config`. Questo attributo specifica se un'applicazione in esecuzione sul computer può registrare informazioni che consentono l'identificazione personale (PII).  
  
-   Se l'attributo `logKnownPii` nel file `app.config` o `web.config` è impostato su `true` affinché un'applicazione specifica attivi la registrazione delle informazioni che consentono l'identificazione personale, ma l'attributo `enableLoggingKnownPII` nell'elemento `machineSettings` del file `machine.config` è impostato su `false`, viene registrato un evento. In aggiunta, se `logKnownPii` e `enableLoggingKnownPII` sono impostati su `true` viene registrato un evento. Per ulteriori informazioni su queste impostazioni di configurazione, vedere la sezione sicurezza del [la configurazione di registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) argomento.  
  
### <a name="security-event-log"></a>Registro eventi di sicurezza  
 Il **registro eventi di sicurezza** contiene eventi di controllo di sicurezza che vengono registrati da WCF.  
  
### <a name="system-event-log"></a>Registro eventi di sistema  
 WCF non registra alcun **registro eventi di sistema**.  
  
### <a name="event-log-entries"></a>Voci del registro eventi  
 Il **origine** di un evento è il nome dell'assembly che genera la voce di log.  
  
 Il tipo di una voce del registro eventi consente di determinare la gravità di una voce. Ogni evento deve appartenere a un solo tipo, che l'applicazione indica quando riferisce l'evento. Il Visualizzatore eventi utilizza tale tipo per scegliere l'icona da visualizzare nella vista elenco del registro. Per i diversi tipi di evento di una voce del registro eventi, vedere <xref:System.Diagnostics.EventLogEntryType>.  
  
 Quando si fa clic su "ulteriori informazioni" quando si visualizza un evento nel Visualizzatore eventi, il Visualizzatore eventi può inviare informazioni via Internet. Per ulteriori informazioni, vedere la Guida del Visualizzatore eventi.  
  
## <a name="see-also"></a>Vedere anche  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Riferimenti generali sugli eventi](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
