---
title: Elemento <performanceCounter> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 4603a942788d31a049196fb699d07a13551fa443
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279760"
---
# <a name="performancecounter-element-network-settings"></a>\<performanceCounter > (impostazioni di rete)
Abilita o disabilita i contatori delle prestazioni di rete.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<performanceCounters>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Specifica se sono abilitati i contatori delle prestazioni di rete. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
 I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare. Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione. Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete. Per altre informazioni sui contatori di prestazioni di rete specifico, vedere [contatori delle prestazioni della rete](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).  
  
 Il valore predefinito è che le prestazioni di rete i contatori sono disabilitati.  
  
 Il <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del **abilitata** attributo dal file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il <xref:System.Net> e relativi spazi dei nomi per abilitare i contatori delle prestazioni di rete.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [I contatori delle prestazioni di rete](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
