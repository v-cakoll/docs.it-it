---
title: Panoramica della traccia analitica
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: f6ffed3d9f0bf5e3dc5698d51276eb1db276993c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837493"
---
# <a name="analytic-tracing-overview"></a>Panoramica della traccia analitica
La traccia analitica in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] è una funzionalità di traccia a prestazioni elevate e verbosità ridotta impostata in base a Traccia eventi per Windows (ETW). ETW è in esecuzione al livello del kernel per ridurre notevolmente il sovraccarico delle operazioni di traccia. Memorizza nel buffer gli eventi in modalità kernel e utente in modo efficace e consente l'abilitazione dinamica della registrazione senza richiedere riavvii del servizio. I dati della traccia sono disponibili nei log eventi in seguito alla generazione e alla ricezione.  
  
 Per ulteriori informazioni su ETW, vedere [migliorare il debug e l'ottimizzazione delle prestazioni con ETW](https://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Oltre a utilizzare i registri eventi di sistema, sicurezza e applicazione di Windows per analizzare l'applicazione, Windows Vista e [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] hanno introdotto log aggiuntivi nel nodo di livello superiore registri applicazioni e servizi. Lo scopo di questi nuovi log consiste nell'archiviare eventi per una particolare applicazione o un componente specifico anziché eventi globali con un impatto a livello di sistema (ad esempio il tipo di eventi che potrebbero essere registrati dal registro eventi relativo alla sicurezza). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] unifica e correla la registrazione di eventi di traccia WCF, log dei messaggi WCF e record di rilevamento [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] ai registri applicazioni e servizi.  
  
## <a name="concepts-and-capabilities"></a>Concetti e funzionalità  
 I concetti e le funzionalità seguenti si applicano alla traccia analitica di WCF.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Abilitazione di impostazioni di diagnostica WCF  
 La diagnostica WCF è abilitata all'interno della sezione di configurazione \<System. serviceModel >\<Diagnostics >.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 Le impostazioni di diagnostica WCF per un'applicazione virtuale IIS ospitata su Web sono abilitate nel relativo file Web.config. Un'altra opzione consiste nella creazione di un file Web.config in una sottodirectory all'interno dell'applicazione.  Con questa scelta, le impostazioni vengono applicate a tutti i servizi all'interno di una sottodirectory.  Per verificare che le impostazioni di diagnostica siano inizializzate in modo coerente per tutti i servizi all'interno dell'applicazione, le impostazioni devono trovarsi all'interno del file Web.config nella directory dell'applicazione e non in una delle singole sottodirectory all'interno dell'applicazione.  
  
### <a name="channels"></a>Canali  
 ETW consente ai componenti software di dirigere eventi della traccia a un particolare gruppo di destinatari in base all'utilizzo di canali. È ad esempio possibile inviare eventi per gli amministratori di sistema a un canale ed eventi di particolare interesse per gli sviluppatori di applicazioni a un altro canale. I canali vengono denominati e registrati con Windows. In questo modo gli utenti possono visualizzare gli eventi di un canale utilizzando il Visualizzatore eventi.  
  
 La funzionalità di traccia analitica per WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] scrive nel canale Microsoft-Windows-Application-Server-Applications. Questo canale è appositamente progettato per gli utenti che desiderano monitorare l'integrità dei servizi WCF nell'ambiente di produzione. Definisce un set di eventi di dimensioni ridotte che può essere utilizzato in diversi scenari di monitoraggio dell'integrità e risoluzione di problemi.  
  
 Per abilitare il manifest di Traccia eventi per Windows in modo che i messaggi vengano decodificati correttamente nel registro eventi, utilizzare lo strumento ServiceModelReg nella riga di comando come segue:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>configurazione dinamica  
 L'infrastruttura ETW consente l'abilitazione e la configurazione dinamica della traccia mediante strumenti standard di Windows. Per ulteriori informazioni, vedere [Abilitazione dinamica della traccia analitica](dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Traccia del flusso di messaggi  
 Per ulteriori informazioni su come abilitare la traccia del flusso di messaggi, vedere [configurazione della traccia del flusso di messaggi](configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Parole chiave  
 Le parole chiave vengono utilizzate per filtrare i messaggi di traccia e definire quale componente della .NET Framework ha generato l'evento. Per ulteriori informazioni, vedere [Abilitazione dinamica della traccia analitica](dynamically-enabling-analytic-tracing.md).
