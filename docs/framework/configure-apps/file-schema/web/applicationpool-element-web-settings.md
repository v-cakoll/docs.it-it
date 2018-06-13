---
title: '&lt;applicationPool&gt; elemento (impostazioni Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2eafc6b5ad1446fd07518f877a8ec001ad8dbd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757697"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;applicationPool&gt; elemento (impostazioni Web)
Specifica le impostazioni di configurazione che sono utilizzate da ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET viene eseguita in modalità integrata in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versione successiva.  
  
> [!IMPORTANT]
>  Questo elemento e la funzionalità supporta funziona solo se l'applicazione ASP.NET è ospitato in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive.  
  
 \<configuration>  
\<System. Web > elemento (impostazioni Web)  
\<applicationPool > elemento (impostazioni Web)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Specifica il numero di richieste simultaneo consentiti da ASP.NET per CPU.|  
|`maxConcurrentThreadsPerCPU`|Specifica che può essere in esecuzione il numero di thread simultaneo per un pool di applicazioni per ogni CPU. Ciò fornisce un modo alternativo per controllare la concorrenza ASP.NET, poiché è possibile limitare il numero di thread gestiti che può essere usato per CPU per elaborare le richieste. Per impostazione predefinita questa impostazione è 0, che indica che ASP.NET non limita il numero di thread che possono essere creati per ogni CPU, anche se il pool di thread CLR consente anche di limitare il numero di thread che possono essere creati.|  
|`requestQueueLimit`|Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un unico processo. Quando due o più applicazioni ASP.NET eseguite in un singolo pool di applicazioni, il set cumulativo di richieste a qualsiasi applicazione nel pool di applicazioni è soggetto a questa impostazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene informazioni sulla modalità di interazione di ASP.NET con un'applicazione host.|  
  
## <a name="remarks"></a>Note  
 Quando si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versione successiva in modalità integrata, questa combinazione di elementi consente di configurare come ASP.NET gestisce le richieste di code e i thread quando l'applicazione è ospitata in un pool di applicazioni IIS. Se si esegue IIS 6 o [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in modalità classica o ISAPI, queste impostazioni vengono ignorate.  
  
 Il `applicationPool` impostazioni si applicano a tutti i pool di applicazioni eseguite in una particolare versione di .NET Framework. Le impostazioni sono contenute in un file Aspnet. config. È disponibile una versione di questo file per le versioni 2.0 e 4.0 di .NET Framework. (Le versioni 3.0 e 3.5 di .NET Framework condividono file Aspnet. config con la versione 2.0)  
  
> [!IMPORTANT]
>  Se si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] su [!INCLUDE[win7](../../../../../includes/win7-md.md)], è possibile configurare un file Aspnet. config separato per ogni pool di applicazioni. Ciò consente di adattare le prestazioni dei thread per ogni pool di applicazioni.  
  
 Per il `maxConcurrentRequestsPerCPU` impostazione, l'impostazione predefinita "5000" il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in modo efficace consente di disattivare la limitazione delle richieste controllata da ASP.NET, a meno che non effettivamente 5000 o più richieste per ogni CPU. L'impostazione predefinita dipende invece il pool di thread CLR per gestire automaticamente la concorrenza per CPU. L'aumento del limite predefinito in saranno vantaggioso per le applicazioni che usano ampiamente elaborazione asincrona della richiesta o che hanno un numero di richieste a esecuzione prolungata bloccate sui / o, rete di [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Impostazione `maxConcurrentRequestsPerCPU` su zero disattiva l'utilizzo di thread gestiti per l'elaborazione delle richieste ASP.NET. Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste restano nel thread dei / o IIS e pertanto la concorrenza è limitata dalle impostazioni di thread IIS.  
  
 Il `requestQueueLimit` impostazione funziona esattamente come il `requestQueueLimit` attributo del [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) elemento, che è impostato nel file Web. config per le applicazioni ASP.NET. Tuttavia, il `requestQueueLimit` esegue l'override di impostazione in un file Aspnet. config di `requestQueueLimit` impostazione in un file Web. config. In altre parole, se sono impostati entrambi gli attributi (per impostazione predefinita, questo è true), il `requestQueueLimit` impostazione nel file Aspnet. config ha la precedenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo ASP.NET nel file Aspnet. config nelle circostanze seguenti:  
  
-   L'applicazione è ospitata in un [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] pool di applicazioni.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] è in esecuzione in modalità integrata.  
  
-   L'applicazione usa il [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o versione successiva.  
  
 I valori nell'esempio sono i valori predefiniti.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Informazioni sull'elemento  
  
|||  
|-|-|  
|Spazio dei nomi||  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche  
 [Elemento \<system.web> (impostazioni Web)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
