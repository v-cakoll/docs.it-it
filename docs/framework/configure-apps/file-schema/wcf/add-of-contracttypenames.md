---
title: '&lt;add&gt; di &lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bebea15e6d1f24c95905355dbced33aa9c5150f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a>&lt;add&gt; di &lt;contractTypeNames&gt;
Elemento di configurazione che specifica il nome del contratto dei servizi ricercati e i criteri usati in genere durante la ricerca di un servizio. Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti. Si noti che in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] un endpoint può supportare un solo contratto.  
  
 \<System. ServiceModel >  
\<standardEndpoints >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa che specifica il nome del tipo di contratto.|  
|namespace|Stringa che specifica lo spazio dei nomi del tipo di contratto.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<contractTypeNames >](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Raccolta di nomi di tipi di contratto.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
