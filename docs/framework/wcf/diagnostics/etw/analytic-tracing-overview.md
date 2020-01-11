---
title: Panoramica della traccia analitica
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 7718c8f2a82178bedc080eda0cd0fdf728213a27
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900635"
---
# <a name="analytic-tracing-overview"></a>Panoramica della traccia analitica

La traccia analitica in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] è una funzionalità di traccia a prestazioni elevate e verbosità ridotta impostata in base a Traccia eventi per Windows (ETW). ETW è in esecuzione al livello del kernel per ridurre notevolmente il sovraccarico delle operazioni di traccia. Memorizza nel buffer gli eventi in modalità kernel e utente in modo efficace e consente l'abilitazione dinamica della registrazione senza richiedere riavvii del servizio. I dati della traccia sono disponibili nei log eventi in seguito alla generazione e alla ricezione.

Per ulteriori informazioni su ETW, vedere [migliorare il debug e l'ottimizzazione delle prestazioni con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).

 Oltre a utilizzare i registri eventi di sistema, sicurezza e applicazione di Windows per analizzare l'applicazione, Windows Vista e Windows Server 2008 hanno introdotto log aggiuntivi nel nodo di livello superiore registri applicazioni e servizi. Lo scopo di questi nuovi log consiste nell'archiviare eventi per una particolare applicazione o un componente specifico anziché eventi globali con un impatto a livello di sistema (ad esempio il tipo di eventi che potrebbero essere registrati dal registro eventi relativo alla sicurezza). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] unifica e correla la registrazione di eventi di traccia WCF, log dei messaggi WCF e record di rilevamento [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] ai registri applicazioni e servizi.

Nelle sezioni seguenti vengono illustrati i concetti e le funzionalità che si applicano alla traccia analitica WCF.

## <a name="enable-wcf-diagnostics-settings"></a>Abilita impostazioni di diagnostica WCF

La diagnostica WCF è abilitata all'interno della sezione di configurazione `<system.serviceModel><diagnostics>`.

```xml
<system.serviceModel>
  <diagnostics>
```

Le impostazioni di diagnostica WCF per un'applicazione virtuale IIS ospitata su Web sono abilitate nel relativo file *Web. config* . Un'altra opzione consiste nel creare un file *Web. config* in una sottodirectory all'interno dell'applicazione. Questa scelta applica le impostazioni a tutti i servizi all'interno di una sottodirectory. Per assicurarsi che le impostazioni di diagnostica siano inizializzate in modo coerente per tutti i servizi all'interno dell'applicazione, le impostazioni devono trovarsi all'interno del file *Web. config* nella directory dell'applicazione e non in una delle singole sottodirectory all'interno dell'applicazione.

## <a name="channels"></a>Canali

ETW consente ai componenti software di dirigere eventi della traccia a un particolare gruppo di destinatari in base all'utilizzo di canali. Ad esempio, è possibile inviare eventi per gli amministratori di sistema a un canale ed eventi interessati da sviluppatori di applicazioni a un altro canale. I canali vengono denominati e registrati con Windows in modo che i consumer possano visualizzare gli eventi di un canale usando Visualizzatore eventi.

 La funzionalità di traccia analitica per WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] scrive nel canale Microsoft-Windows-Application-Server-Applications. Questo canale è progettato per gli utenti che desiderano monitorare l'integrità dei servizi WCF nell'ambiente di produzione. Definisce un piccolo set di eventi che possono essere usati in molti scenari di monitoraggio dell'integrità e risoluzione dei problemi.

 Per abilitare il manifest di Traccia eventi per Windows in modo che i messaggi vengano decodificati correttamente nel registro eventi, utilizzare lo strumento ServiceModelReg nella riga di comando come segue:

 `ServiceModelReg.exe -i -c:etw`

## <a name="dynamic-configuration"></a>configurazione dinamica

L'infrastruttura ETW consente l'abilitazione e la configurazione dinamica della traccia mediante strumenti standard di Windows. Per ulteriori informazioni, vedere [Abilitazione dinamica della traccia analitica](dynamically-enabling-analytic-tracing.md).

## <a name="message-flow-tracing"></a>Traccia del flusso di messaggi

Per ulteriori informazioni su come abilitare la traccia del flusso di messaggi, vedere [configurazione della traccia del flusso di messaggi](configuring-message-flow-tracing.md).

## <a name="keywords"></a>Parole chiave

Le parole chiave vengono utilizzate per filtrare i messaggi di traccia e definire quale componente della .NET Framework ha generato l'evento. Per ulteriori informazioni, vedere [Abilitazione dinamica della traccia analitica](dynamically-enabling-analytic-tracing.md).
