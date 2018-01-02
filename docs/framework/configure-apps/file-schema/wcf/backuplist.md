---
title: '&lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00a4c84ee5c9a833cc789c8871df79a3886fa0e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Rappresenta una sezione di configurazione per la definizione di un elenco di backup che enumera un set di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile. Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.  In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.  
  
 \<System. ServiceModel >  
\<routing >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>Sintassi  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa che specifica il nome usato per identificare l'elenco di endpoint.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Elenco di endpoint di backup.|  
  
## <a name="remarks"></a>Note  
 Questa sezione include una raccolta ordinata di endpoint ai quali verrà trasmesso un messaggio nel caso venga generata un'eccezione di comunicazione durante l'invio all'endpoint primario.  
  
 Se un invio all'endpoint primario è elencato nella `endpointName` attributo di [ \<aggiungere >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) ha esito negativo con un'eccezione di comunicazione, il servizio di Routing tenterà di inviare il messaggio al primo endpoint in questo sezione di configurazione. Se anche questo invio non riesce e viene generata un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso in questa sezione fino a quando il tentativo di invio non ha esito positivo, non viene restituito un errore diverso da un'eccezione di comunicazione o tutti gli endpoint inclusi nella raccolta non restituiscono un errore.  
  
 Nell'esempio seguente, se un invio all'endpoint primario denominato "Destination" restituisce un'eccezione di comunicazione, il servizio tenterà di inviare il messaggio a "alternateServiceQueue". Se anche questo tentativo restituisce un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso nella raccolta.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
