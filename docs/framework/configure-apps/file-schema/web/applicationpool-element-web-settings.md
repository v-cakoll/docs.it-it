---
title: Elemento <applicationPool> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152854"
---
# <a name="applicationpool-element-web-settings"></a>\<Elemento applicationPool> (impostazioni Web)
Specifica le impostazioni di configurazione utilizzate dai ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET è in esecuzione in modalità integrata in IIS 7.0 o versione successiva.  
  
> [!IMPORTANT]
> Questo elemento e la funzionalità che supporta funzionano solo se l'applicazione ASP.NET è ospitata in IIS 7.0 o versioni successive.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;[**\<>system.web**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<>applicationPool**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Specifica il numero di richieste simultanee ASP.NET consentite per CPU.|  
|`maxConcurrentThreadsPerCPU`|Specifica il numero di thread simultanei che possono essere in esecuzione per un pool di applicazioni per ogni CPU. Ciò fornisce un modo alternativo per controllare ASP.NET concorrenza, perché è possibile limitare il numero di thread gestiti che possono essere utilizzati per ogni CPU per gestire le richieste. Per impostazione predefinita, questa impostazione è 0, il che significa che ASP.NET non limita il numero di thread che possono essere creati per CPU, anche se il pool di thread CLR limita anche il numero di thread che possono essere creati.|  
|`requestQueueLimit`|Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un singolo processo. Quando due o più applicazioni ASP.NET vengono eseguite in un singolo pool di applicazioni, il set cumulativo di richieste effettuate a qualsiasi applicazione nel pool di applicazioni è soggetto a questa impostazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>system.web](system-web-element-web-settings.md)|Contiene informazioni sull'interazione dei ASP.NET con un'applicazione host.|  
  
## <a name="remarks"></a>Osservazioni  

Quando si esegue IIS 7.0 o versione successiva in modalità integrata, questa combinazione di elementi consente di configurare la modalità di gestione delle richieste di thread e code ASP.NET quando l'applicazione è ospitata in un pool di applicazioni IIS. Se si esegue IIS 6 o si esegue IIS 7.0 in modalità classica o in modalità ISAPI, queste impostazioni vengono ignorate.  
  
Le `applicationPool` impostazioni si applicano a tutti i pool di applicazioni eseguiti in una particolare versione di .NET Framework. Le impostazioni sono contenute in un file aspnet.config. Esiste una versione di questo file per le versioni 2.0 e 4.0 di .NET Framework. Le versioni 3.0 e 3.5 di .NET Framework condividono il file aspnet.config con la versione 2.0.  
  
> [!IMPORTANT]
> Se si esegue IIS 7.0 in Windows 7, è possibile configurare un file aspnet.config separato per ogni pool di applicazioni. In questo modo è possibile personalizzare le prestazioni dei thread per ogni pool di applicazioni.  
  
Per `maxConcurrentRequestsPerCPU` l'impostazione, l'impostazione predefinita di "5000" in .NET Framework 4 disattiva in modo efficace la limitazione delle richieste controllata da ASP.NET, a meno che non si disponga effettivamente di 5000 o più richieste per CPU. L'impostazione predefinita dipende invece dal pool di thread CLR per gestire automaticamente la concorrenza per CPU. Le applicazioni che fanno ampio uso dell'elaborazione delle richieste asincrone o che hanno molte richieste a esecuzione prolungata bloccate sull'I/O di rete, trarranno vantaggio dall'aumento del limite predefinito in .NET Framework 4. L'impostazione `maxConcurrentRequestsPerCPU` su zero disattiva l'utilizzo dei thread gestiti per l'elaborazione delle richieste ASP.NET. Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste rimangono nel thread di I/O iIS e pertanto la concorrenza viene limitata dalle impostazioni del thread IIS.  
  
L'impostazione `requestQueueLimit` funziona allo `requestQueueLimit` stesso modo dell'attributo dell'elemento [processModel,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) impostato nei file Web.config per le applicazioni ASP.NET. Tuttavia, `requestQueueLimit` l'impostazione in un file `requestQueueLimit` aspnet.config esegue l'override dell'impostazione in un file Web.config. In altre parole, se entrambi gli attributi sono impostati (per impostazione predefinita, questo è vero), l'impostazione `requestQueueLimit` nel file aspnet.config ha la precedenza.  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come configurare ASP.NET comportamento a livello di processo nel file aspnet.config nelle seguenti circostanze:  
  
- L'applicazione è ospitata in un pool di applicazioni IIS 7.0.  
  
- IIS 7.0 è in esecuzione in modalità integrata.  
  
- L'applicazione utilizza .NET Framework 3.5 SP1 o versione successiva.  
  
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
|Schema Name||  
|File di convalida||  
|Può essere Vuoto||  
  
## <a name="see-also"></a>Vedere anche

- [\<elemento> system.web (impostazioni Web)](system-web-element-web-settings.md)
