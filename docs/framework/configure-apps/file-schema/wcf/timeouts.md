---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854973"
---
# <a name="timeouts"></a>\<timeOuts>
Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dei servizi**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del servizio**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> host**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<timeOut >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`closeTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.|  
|`openTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<host>](host.md)|Elemento di configurazione che specifica le impostazioni per un host del servizio.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Hosting](../../../wcf/feature-details/hosting.md)
