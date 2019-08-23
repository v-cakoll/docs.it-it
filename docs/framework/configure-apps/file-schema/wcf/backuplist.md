---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: d5feab6cb374f98e683cf15f797de4f478e23131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919914"
---
# <a name="backuplist"></a>\<> di backup
Rappresenta una sezione di configurazione per la definizione di un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario. Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.  In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.  
  
 \<system.serviceModel>  
\<routing>  
\<> backupLists  
\<> di backup  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|name|Stringa che specifica il nome usato per identificare l'elenco di endpoint.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Elenco di endpoint di backup.|  
  
## <a name="remarks"></a>Note  
 Questa sezione include una raccolta ordinata di endpoint ai quali verrà trasmesso un messaggio nel caso venga generata un'eccezione di comunicazione durante l'invio all'endpoint primario.  
  
 Se un invio all'endpoint primario elencato nell' `endpointName` attributo di [ \<Add >](add-of-entries.md) ha esito negativo con un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio al primo endpoint in questa sezione di configurazione. Se anche questo invio non riesce e viene generata un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso in questa sezione fino a quando il tentativo di invio non ha esito positivo, non viene restituito un errore diverso da un'eccezione di comunicazione o tutti gli endpoint inclusi nella raccolta non restituiscono un errore.  
  
 Nell'esempio seguente, se un invio all'endpoint primario denominato "Destination" restituisce un'eccezione di comunicazione, il servizio tenterà di inviare il messaggio a "alternateServiceQueue". Se anche questo tentativo restituisce un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso nella raccolta.  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
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

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
