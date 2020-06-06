---
title: Elemento <system.web> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152841"
---
# <a name="systemweb-element-web-settings"></a>Elemento \<system.web> (impostazioni Web)
Contiene informazioni sul modo in cui il livello di hosting di ASP.NET gestisce il comportamento a livello di processo.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  

No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Specifica le impostazioni di configurazione per i pool di applicazioni IIS in un file Aspnet. config.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.|  
  
## <a name="remarks"></a>Commenti  

L' `system.web` elemento e il relativo `applicationPool` elemento figlio sono stati aggiunti all'.NET Framework a partire da .NET Framework 3,5 SP1. Quando si esegue IIS 7,0 o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare il modo in cui ASP.NET gestisce i thread e come Accoda le richieste quando ASP.NET è ospitato in un pool di applicazioni IIS. Se si esegue IIS 7,0 o versioni successive in modalità classica o ISAPI, queste impostazioni verranno ignorate.  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo di ASP.NET nel file Aspnet. config quando ASP.NET è ospitato in un pool di applicazioni IIS. Nell'esempio si presuppone che IIS sia in esecuzione in modalità integrata e che l'applicazione utilizzi la .NET Framework 3,5 SP1 o una versione successiva. Questo comportamento non si verifica nelle versioni del .NET Framework precedenti al .NET Framework 3,5 SP1. I valori nell'esempio sono i valori predefiniti.  
  
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
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedi anche

- [\<applicationPool>Elemento (impostazioni Web)](applicationpool-element-web-settings.md)
