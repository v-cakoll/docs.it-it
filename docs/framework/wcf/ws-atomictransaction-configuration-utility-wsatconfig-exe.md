---
title: Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: 31b2b3cf16857bf08a4f8d09f47f80d9b34a53b8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659960"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)
L'utilità di configurazione WS-AtomicTransaction viene utilizzata per configurare le impostazioni di base per il supporto WS-AtomicTransaction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Note  
 Questo strumento da riga di comando può essere utilizzato per configurare soltanto impostazioni WS-AT di base in un computer locale. Se è necessario configurare le impostazioni nei computer locali e remoti, è necessario usare lo snap-in MMC come descritto in [configurazione del supporto transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Lo strumento da riga di comando si trova specificamente nel percorso di installazione di Windows SDK.   
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe  
  
 Se si sta eseguendo [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], è necessario scaricare un aggiornamento prima di eseguire WsatConfig.exe. Per altre informazioni su questo aggiornamento, vedere [aggiornare per e-Commerce Server 2007 (KB912817)](https://go.microsoft.com/fwlink/?LinkId=95340) e [disponibilità di Windows XP COM+ Hotfix Rollup Package 13](https://go.microsoft.com/fwlink/?LinkId=95341).  
  
 Nella tabella riportata di seguito vengono illustrate le opzioni che possono essere utilizzate con l’utilità di configurazione WS-AtomicTransaction (wsatConfig.exe).  
  
> [!NOTE]
>  Impostando un certificato SSL per una porta selezionata, il certificato SSL originale associato a quella porta, se presente, viene sovrascritto.  
  
|Opzioni|Descrizione|  
|-------------|-----------------|  
|-account:\<account >|Specifica un elenco con valori delimitati da virgole di account che possono partecipare in WS-AtomicTransaction. La validità di questi account non viene controllata.|  
|-accountsCerts:\<thumb >&#124;"Issuer\SubjectName.," >|Specifica un elenco con valori delimitati da virgole di certificati che possono partecipare in WS-AtomicTransaction. I certificati sono indicati tramite identificazione digitale o dalla coppia Issuer\SubjectName. Utilizzare {Vuoto} per il nome del soggetto se è vuoto.|  
|-endpointCert: < computer&#124;\<thumb >&#124;"Issuer\SubjectName." >|Utilizza il certificato del computer o un altro certificato dell'endpoint locale specificato tramite identificazione digitale o dalla coppia Issuer\SubjectName. Utilizza {Vuoto} per il nome del soggetto se è vuoto.|  
|-maxTimeout:\<sec >|Specifica il timeout massimo in secondi. I valori validi sono da 0 e 3600.|  
|-rete:\<abilitare&#124;Disabilita >|Abilita o disabilita il supporto di rete WS-AtomicTransaction.|  
|-porta:\<portNum >|Imposta la porta HTTPS per WS-AtomicTransaction.<br /><br /> Se prima di eseguire questo strumento è già stato abilitato un firewall, la porta viene automaticamente registrata nell'elenco delle eccezioni. Se il firewall è stato disabilitato prima di eseguire questo strumento, non avviene nessun’altra configurazione riguardante il firewall.<br /><br /> Se si abilita il firewall dopo aver configurato WS-AT, è necessario eseguire di nuovo questo strumento e fornire il numero della porta che utilizza questo parametro. Se si disabilita il firewall dopo la configurazione, WS-AT rimane in funzione senza input aggiuntivo.|  
|-timeout:\<sec >|Specifica il timeout predefinito in secondi. I valori validi sono compresi tra 1 e 3600.|  
|-traceActivity:\<abilitare&#124;Disabilita >|Abilita o disabilita la traccia degli eventi di attività.|  
|-traceLevel:\<Off&#124;errore&#124;critico&#124;avviso&#124;informazioni&#124; dettagliato&#124;tutte >}|Specifica il livello di traccia.|  
|-tracePII:\<abilitare&#124;Disabilita >|Abilita o disabilita la traccia delle informazioni personali.|  
|-traceProp:\<abilitare&#124;Disabilita >|Abilita o disabilita la traccia degli eventi di propagazione.|  
|-riavvia|Riavvia MSDTC per attivare immediatamente le modifiche. Se tale funzionalità non è specificata, le modifiche hanno effetto quando MSDTC viene riavviato.|  
|-mostra|Visualizza le impostazioni del protocollo WS-AtomicTransaction correnti.|  
|-virtualServer:\<virtualServer >|Specifica il nome del cluster della risorsa DTC.|  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di WS-AtomicTransaction](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)  
 [Configurazione del supporto di transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
