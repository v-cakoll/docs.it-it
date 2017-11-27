---
title: '&lt;host&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bded8d718259bf4fc84bfe790db069a77fc2a703
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lthostgt"></a>&lt;host&gt;
Specifica impostazioni per un host del servizio.  
  
 \<System. ServiceModel >  
\<Services >  
\<servizio >  
\<host >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.|  
|[\<Timeout >](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<servizio >](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Specifica le impostazioni di un servizio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
