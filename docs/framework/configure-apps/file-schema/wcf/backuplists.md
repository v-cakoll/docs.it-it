---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926441"
---
# <a name="backuplists"></a>\<> backupLists
Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori. Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario. Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.  In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.  
  
 \<system.serviceModel>  
\<routing>  
\<> backupLists  
  
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
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<filter>](filter.md)|Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario. .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
