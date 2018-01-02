---
title: '&lt;appDomainResourceMonitoring&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58caa7458d96ca7bb9088b607a83b2d6be667cae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainresourcemonitoringgt-element"></a>&lt;appDomainResourceMonitoring&gt; elemento
Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.  
  
 \<configuration>  
\<runtime >  
\<appDomainResourceMonitoring >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime raccoglie le statistiche per il monitoraggio delle risorse al dominio di applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Vengono raccolte statistiche per il monitoraggio delle risorse al dominio di applicazione.|  
|`false`|Non vengono raccolte statistiche per il monitoraggio delle risorse al dominio di applicazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Monitoraggio delle risorse di dominio di applicazione è disponibile tramite la classe di dominio di applicazione gestita, l'hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaccia e event tracing for Windows (ETW). Quando il monitoraggio è abilitato, vengono raccolte statistiche per tutti i domini applicazione nel processo per tutta la durata del processo.  
  
 Per abilitare il monitoraggio da codice gestito, utilizzare il <xref:System.AppDomain.MonitoringIsEnabled%2A> proprietà.  
  
 È disponibile solo in questo elemento di configurazione di [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare il monitoraggio delle risorse al dominio di applicazione.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
