---
title: Elemento <applicationPool> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 9783844ff0fe719b0581c1c9e1fb96eb31933b89
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801866"
---
# <a name="applicationpool-element-web-settings"></a>\<elemento > applicationPool (impostazioni Web)
Specifica le impostazioni di configurazione usate da ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET è in esecuzione in modalità integrata in IIS 7,0 o versione successiva.  
  
> [!IMPORTANT]
> Questo elemento e la funzionalità che supporta funzionano solo se l'applicazione ASP.NET è ospitata in IIS 7,0 o versioni successive.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<> System. Web**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<applicationPool >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  

Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Specifica il numero di richieste simultanee consentite da ASP.NET per CPU.|  
|`maxConcurrentThreadsPerCPU`|Specifica il numero di thread simultanei che possono essere in esecuzione per un pool di applicazioni per ogni CPU. Si tratta di un metodo alternativo per controllare la concorrenza ASP.NET, in quanto è possibile limitare il numero di thread gestiti che possono essere usati per CPU per gestire le richieste. Per impostazione predefinita, questa impostazione è 0, il che significa che ASP.NET non limita il numero di thread che possono essere creati per CPU, anche se il pool di thread CLR limita anche il numero di thread che è possibile creare.|  
|`requestQueueLimit`|Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un singolo processo. Quando due o più applicazioni ASP.NET vengono eseguite in un unico pool di applicazioni, il set cumulativo di richieste effettuate a qualsiasi applicazione nel pool di applicazioni è soggetto a questa impostazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Contiene informazioni sul modo in cui ASP.NET interagisce con un'applicazione host.|  
  
## <a name="remarks"></a>Note  

Quando si esegue IIS 7,0 o una versione successiva in modalità integrata, questa combinazione di elementi consente di configurare il modo in cui ASP.NET gestisce i thread e le richieste di Accodamento quando l'applicazione è ospitata in un pool di applicazioni IIS. Se si esegue IIS 6 oppure si esegue IIS 7,0 in modalità classica o in modalità ISAPI, queste impostazioni verranno ignorate.  
  
Le impostazioni `applicationPool` si applicano a tutti i pool di applicazioni eseguiti in una determinata versione del .NET Framework. Le impostazioni sono contenute in un file Aspnet. config. Esiste una versione di questo file per le versioni 2,0 e 4,0 del .NET Framework. (Le versioni 3,0 e 3,5 del .NET Framework condividono il file Aspnet. config con la versione 2,0).  
  
> [!IMPORTANT]
> Se si esegue IIS 7,0 in Windows 7, è possibile configurare un file Aspnet. config separato per ogni pool di applicazioni. In questo modo è possibile personalizzare le prestazioni dei thread per ogni pool di applicazioni.  
  
Per l'impostazione di `maxConcurrentRequestsPerCPU`, l'impostazione predefinita di "5000" nella .NET Framework 4 Disattiva in modo efficace la limitazione delle richieste controllata da ASP.NET, a meno che non siano effettivamente presenti 5000 o più richieste per CPU. L'impostazione predefinita dipende invece dal pool di thread CLR per la gestione automatica della concorrenza per CPU. Le applicazioni che usano in modo esteso l'elaborazione di richieste asincrone o con numerose richieste a esecuzione prolungata bloccate sull'I/O di rete trarranno vantaggio dall'aumento del limite predefinito nel .NET Framework 4. Impostando `maxConcurrentRequestsPerCPU` su zero si disattiva l'uso di thread gestiti per l'elaborazione delle richieste ASP.NET. Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste vengono mantenute nel thread di I/O di IIS e pertanto la concorrenza è limitata dalle impostazioni del thread IIS.  
  
L'impostazione `requestQueueLimit` funziona allo stesso modo dell'attributo `requestQueueLimit` dell'elemento [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , che viene impostato nei file Web. config per le applicazioni ASP.NET. Tuttavia, l'impostazione `requestQueueLimit` in un file Aspnet. config sostituisce l'impostazione di `requestQueueLimit` in un file Web. config. In altre parole, se entrambi gli attributi sono impostati (per impostazione predefinita, questo è true), l'impostazione `requestQueueLimit` nel file Aspnet. config ha la precedenza.  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo di ASP.NET nel file Aspnet. config nelle circostanze seguenti:  
  
- L'applicazione è ospitata in un pool di applicazioni IIS 7,0.  
  
- IIS 7,0 viene eseguito in modalità integrata.  
  
- L'applicazione usa la .NET Framework 3,5 SP1 o una versione successiva.  
  
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
|Nome schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche

- [Elemento \<system.web> (impostazioni Web)](system-web-element-web-settings.md)
