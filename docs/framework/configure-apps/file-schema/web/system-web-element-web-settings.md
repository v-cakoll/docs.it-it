---
title: '&lt;System. Web&gt; elemento (impostazioni Web)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44a978eae9ae85e1ba12f117288a3c9ce4db75b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;System. Web&gt; elemento (impostazioni Web)
Contiene informazioni su come il livello di hosting ASP.NET gestisce il comportamento a livello di processo.  
  
 \<configuration>  
\<System. Web > elemento (impostazioni Web)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Specifica le impostazioni di configurazione per il pool di applicazioni IIS in un file Aspnet. config.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
  
## <a name="remarks"></a>Note  
 Il `system.web` elemento e del relativo figlio `applicationPool` elemento sono stati aggiunti per il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] da [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Quando si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare la modalità ASP.NET gestisce i thread e mette in coda le richieste quando ASP.NET è ospitato in un pool di applicazioni IIS. Se si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive in modalità classica o ISAPI, queste impostazioni vengono ignorate.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo ASP.NET nel file Aspnet. config quando ASP.NET è ospitato in un pool di applicazioni IIS. Nell'esempio si presuppone che IIS sia in esecuzione in modalità integrata modalità e l'applicazione usa il [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o versione successiva. Questo comportamento non avviene nelle versioni del [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] antecedente la [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. I valori nell'esempio sono i valori predefiniti.  
  
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
 [Elemento \<applicationPool> (impostazioni Web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
