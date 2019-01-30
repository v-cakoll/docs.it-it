---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: ba65d3858cdbdf6b49c50e60f4e3cc9624fef136
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254405"
---
# <a name="filtertable"></a>\<filterTable>
Rappresenta una tabella di routing contenente un elenco di filtri per valutare i messaggi da e per indirizzare messaggi agli endpoint client se il filtro restituisce true.  
  
 \<system.serviceModel>  
\<routing>  
\<routingTables>  
\<tabella >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|name|Stringa contenente il nome univoco di questo elemento di configurazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filters>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sezione di configurazione contenente tabelle di routing.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
