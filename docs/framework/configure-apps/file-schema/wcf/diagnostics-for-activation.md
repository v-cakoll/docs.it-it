---
title: '&lt;diagnostics&gt; per Activation'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 28f051a7ab06dbc1b40f804c56071818eb37e88b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144977"
---
# <a name="ltdiagnosticsgt-for-activation"></a>&lt;diagnostics&gt; per Activation
Configura le funzionalità di diagnostica del listener di Windows Communication Foundation (WCF).  
  
 \<system.serviceModel.activation>  
\<diagnostica >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`performanceCountersEnabled`|Valore booleano che indica se sono i contatori delle prestazioni stati attivati a fini diagnostici.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
