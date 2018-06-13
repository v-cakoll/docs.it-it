---
title: '&lt;Voci&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746709"
---
# <a name="ltentriesgt"></a>&lt;Voci&gt;
Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.  
  
 \<system.serviceModel>  
\<routing >  
\<routingTables >  
\<tabella >  
\<le voci >  
  
## <a name="syntax"></a>Sintassi  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<i filtri >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Esegue il mapping di un filtro a un endpoint client definito in precedenza. I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sezione di configurazione contenente una tabella di routing.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
