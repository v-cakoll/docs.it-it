---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5fb89ce5a942db40b07a65f59ddd05ab4cd624aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749595"
---
# <a name="ltbackuplistsgt"></a>&lt;backupLists&gt;
Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori. Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile. Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.  In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.  
  
 \<system.serviceModel>  
\<routing >  
\<backupLists >  
  
## <a name="syntax"></a>Sintassi  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|Contiene un elenco di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile. .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione a tabelle inviare messaggi quando un filtro trovata una corrispondenza.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
