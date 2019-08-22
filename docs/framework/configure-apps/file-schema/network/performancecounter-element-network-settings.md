---
title: Elemento <performanceCounter> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 05aac6c1ed3c04bce263a45cafdb9bec906bd75b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664054"
---
# <a name="performancecounter-element-network-settings"></a>\<Elemento > performanceCounter (impostazioni di rete)
Abilita o Disabilita i contatori delle prestazioni di rete.  
  
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
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`enabled`|Specifica se i contatori delle prestazioni di rete sono abilitati. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
 I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare. Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione. Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete. Per ulteriori informazioni sui contatori delle prestazioni di rete specifici, vedere [contatori delle prestazioni di rete](../../../debug-trace-profile/performance-counters.md#networking).  
  
 Il valore predefinito è che i contatori delle prestazioni di rete sono disabilitati.  
  
 È <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente dell'attributo **Enabled** dai file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare gli <xref:System.Net> spazi dei nomi e correlati per abilitare i contatori delle prestazioni di rete.  
  
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
- [Schema delle impostazioni di rete](index.md)
- [Contatori delle prestazioni di rete](../../../debug-trace-profile/performance-counters.md#networking)
