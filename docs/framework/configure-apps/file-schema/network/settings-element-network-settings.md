---
title: '&lt;impostazioni&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9d6189c736e1f2843a986c3a96f8547e9a231db0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075148"
---
# <a name="ltsettingsgt-element-network-settings"></a>&lt;impostazioni&gt; (impostazioni di rete)
Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Consente di personalizzare i parametri usati dal <xref:System.Net.HttpListener> classe.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Consente di personalizzare i parametri della richiesta Web.|  
|[IPv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Abilita protocollo Internet versione 6 (IPv6) supportano.|  
|[\<performanceCounter > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|I contatori delle prestazioni di rete.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Consente di configurare le connessioni alle risorse di rete.|  
|[socket](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Specifica se le operazioni socket usano le porte di completamento.|  
|[\<webProxyScript > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Consente di configurare le caratteristiche dello script utilizzato per individuare i proxy Web.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="remarks"></a>Note  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net?displayProperty=nameWithType>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
