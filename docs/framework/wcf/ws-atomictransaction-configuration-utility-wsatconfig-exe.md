---
title: "Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: adb44bfee98d01594c9babcf19e19fbf11ba3878
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)
L'utilità di configurazione WS-AtomicTransaction viene utilizzata per configurare le impostazioni di base per il supporto WS-AtomicTransaction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Note  
 Questo strumento da riga di comando può essere utilizzato per configurare soltanto impostazioni WS-AT di base in un computer locale. Se è necessario configurare le impostazioni nei computer locali e remoti, utilizzare lo snap-in MMC come descritto in [configurazione del supporto transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Lo strumento da riga di comando si trova specificamente nel percorso di installazione di Windows SDK.   
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe  
  
 Se si sta eseguendo [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], è necessario scaricare un aggiornamento prima di eseguire WsatConfig.exe. Per ulteriori informazioni su questo aggiornamento, vedere [aggiornamento per Commerce Server 2007 (KB912817)](http://go.microsoft.com/fwlink/?LinkId=95340) e [disponibilità di Windows XP COM+ Hotfix Rollup pacchetto 13](http://go.microsoft.com/fwlink/?LinkId=95341).  
  
 Nella tabella riportata di seguito vengono illustrate le opzioni che possono essere utilizzate con l’utilità di configurazione WS-AtomicTransaction (wsatConfig.exe).  
  
> [!NOTE]
>  Impostando un certificato SSL per una porta selezionata, il certificato SSL originale associato a quella porta, se presente, viene sovrascritto.  
  
|Opzioni|Descrizione|  
|-------------|-----------------|  
|-account:\<account >|Specifica un elenco con valori delimitati da virgole di account che possono partecipare in WS-AtomicTransaction. La validità di questi account non viene controllata.|  
|-accountsCerts:\<thumb > &#124; " Issuer\SubjectName.">|Specifica un elenco con valori delimitati da virgole di certificati che possono partecipare in WS-AtomicTransaction. I certificati sono indicati tramite identificazione digitale o dalla coppia Issuer\SubjectName. Utilizzare {Vuoto} per il nome del soggetto se è vuoto.|  
|-endpointCert: < computer &#124; \<thumb > &#124; " Issuer\SubjectName.">|Utilizza il certificato del computer o un altro certificato dell'endpoint locale specificato tramite identificazione digitale o dalla coppia Issuer\SubjectName. Utilizza {Vuoto} per il nome del soggetto se è vuoto.|  
|-maxTimeout:\<sec >|Specifica il timeout massimo in secondi. I valori validi sono compresi tra 0 e 3600.|  
|-rete:\<Abilita &#124; Disabilita >|Abilita o disabilita il supporto di rete WS-AtomicTransaction.|  
|-porta:\<portNum >|Imposta la porta HTTPS per WS-AtomicTransaction.<br /><br /> Se prima di eseguire questo strumento è già stato abilitato un firewall, la porta viene automaticamente registrata nell'elenco delle eccezioni. Se il firewall è stato disabilitato prima di eseguire questo strumento, non avviene nessun’altra configurazione riguardante il firewall.<br /><br /> Se si abilita il firewall dopo aver configurato WS-AT, è necessario eseguire di nuovo questo strumento e fornire il numero della porta che utilizza questo parametro. Se si disabilita il firewall dopo la configurazione, WS-AT rimane in funzione senza input aggiuntivo.|  
|-timeout:\<sec >|Specifica il timeout predefinito in secondi. I valori validi sono compresi tra 1 e 3600.|  
|-traceActivity:\<Abilita &#124; Disabilita >|Abilita o disabilita la traccia degli eventi di attività.|  
|-traceLevel:\<Off &#124; Errore &#124; Critico &#124; Avviso &#124; informazioni &#124; Verbose &#124; Tutti i >}|Specifica il livello di traccia.|  
|-tracePII:\<Abilita &#124; Disabilita >|Abilita o disabilita la traccia delle informazioni personali.|  
|-traceProp:\<Abilita &#124; Disabilita >|Abilita o disabilita la traccia degli eventi di propagazione.|  
|-riavvia|Riavvia MSDTC per attivare immediatamente le modifiche. Se tale funzionalità non è specificata, le modifiche hanno effetto quando MSDTC viene riavviato.|  
|-mostra|Visualizza le impostazioni del protocollo WS-AtomicTransaction correnti.|  
|-virtualServer:\<virtualServer >|Specifica il nome del cluster della risorsa DTC.|  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di WS-AtomicTransaction](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)  
 [Configurazione del supporto di transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
