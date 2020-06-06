---
title: <appDomainResourceMonitoring> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154376"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring> Elemento
Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
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
  
|Valore|Description|  
|-----------|-----------------|  
|`true`|Vengono raccolte le statistiche per il monitoraggio delle risorse del dominio applicazione.|  
|`false`|Le statistiche per il monitoraggio delle risorse del dominio applicazione non vengono raccolte.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Commenti  
 Il monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio dell'applicazione gestita, l'interfaccia [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) di hosting e Event Tracing for Windows (ETW). Quando il monitoraggio è abilitato, le statistiche vengono raccolte per tutti i domini applicazione nel processo per il ciclo di vita del processo.  
  
 Per abilitare il monitoraggio dal codice gestito, usare la <xref:System.AppDomain.MonitoringIsEnabled%2A> Proprietà.  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare il monitoraggio delle risorse del dominio applicazione.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
