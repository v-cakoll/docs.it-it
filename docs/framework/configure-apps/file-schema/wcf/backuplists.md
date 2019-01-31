---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6ac7ff19c76097cb54e7b77db21cad50b49513c0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280748"
---
# <a name="backuplists"></a>\<backupLists>
Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori. Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario. Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.  In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.  
  
 \<system.serviceModel>  
\<routing>  
\<backupLists>  
  
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
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|Contiene un elenco di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario. .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
