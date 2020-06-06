---
title: Elemento <settings> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089110"
---
# <a name="settings-element-network-settings"></a>Elemento \<settings> (impostazioni di rete)
Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[httpListener](httplistener-element-network-settings.md)|Personalizza i parametri utilizzati dalla <xref:System.Net.HttpListener> classe.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Personalizza i parametri della richiesta Web.|  
|[IPv6](ipv6-element-network-settings.md)|Abilita il supporto protocollo Internet versione 6 (IPv6).|  
|[\<performanceCounter>Elemento (impostazioni di rete)](performancecounter-element-network-settings.md)|Abilita i contatori delle prestazioni di rete.|  
|[servicePointManager](servicepointmanager-element-network-settings.md)|Configura le connessioni alle risorse di rete.|  
|[presa](socket-element-network-settings.md)|Specifica se le operazioni socket utilizzano le porte di completamento.|  
|[\<webProxyScript>Elemento (impostazioni di rete)](webproxyscript-element-network-settings.md)|Configura le caratteristiche dello script utilizzato per individuare i proxy Web.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="remarks"></a>Commenti  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Net?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
