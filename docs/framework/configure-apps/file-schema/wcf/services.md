---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854983"
---
# <a name="services"></a>\<> dei servizi
I servizi vengono definiti nella sezione `services` del file di configurazione. Ogni servizio dispone di una propria sezione di configurazione `service`.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<> dei servizi**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<service>](service.md)|Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServicesSection>
