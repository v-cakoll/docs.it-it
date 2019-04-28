---
title: <appDomainResourceMonitoring> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71cc69eba17de8465cc7999f334c724e4ec14e7d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704999"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring > elemento
Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.  
  
 \<configuration>  
\<runtime>  
\<appDomainResourceMonitoring>  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime raccoglie le statistiche per il monitoraggio delle risorse del dominio applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Statistiche di monitoraggio delle risorse del dominio dell'applicazione vengono raccolte.|  
|`false`|Statistiche di monitoraggio delle risorse del dominio applicazione non vengono raccolte.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio di applicazione gestita, l'hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaccia e event tracing for Windows (ETW). Quando il monitoraggio è abilitato, vengono raccolte statistiche per tutti i domini applicazione del processo per il ciclo di vita del processo.  
  
 Per abilitare il monitoraggio dal codice gestito, usare il <xref:System.AppDomain.MonitoringIsEnabled%2A> proprietà.  
  
 Questo elemento di configurazione è disponibile solo nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare Monitoraggio risorse del dominio applicazione.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
