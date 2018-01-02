---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 530d515c3913bb103fcc1b5f0c76670db03b71b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsqlworkflowinstancestoregt"></a>&lt;sqlWorkflowInstanceStore&gt;
Un comportamento del servizio che consente di configurare il <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> funzionalità, che supporta mantenimento delle informazioni di stato per le istanze del servizio del flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008. Per ulteriori informazioni su questa funzionalità, vedere [archivio di istanze del flusso di lavoro SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
\<System. ServiceModel >  
\<i comportamenti >  
\<serviceBehaviors >  
\<comportamento >  
\<sqlWorkflowInstanceStore >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|connectionString|Stringa che contiene una stringa di connessione utilizzata per connettersi a un database di persistenza sottostante.|  
|connectionStringName|Stringa che contiene una stringa di connessione denominata al server di database. Un esempio di una stringa di connessione denominata è "DefaultConnectionString".|  
|honstLockRenewalPeriod|Valore TimeSpan che specifica il periodo di tempo entro il quale l'host deve rinnovare il blocco su un'istanza. Se l'host non rinnova il blocco nel periodo di tempo specificato, l'istanza viene sbloccata e può essere scelta da un altro host.<br /><br /> Lo scaricamento di un flusso di lavoro lo rende anche persistente. Se questo attributo è impostato su zero l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo il flusso di lavoro diventa inattivo. L'impostazione di questo attributo su TimeSpan. MaxValue in modo efficace disabilita l'operazione di scaricamento. Le istanze del flusso di lavoro inattive non vengono mai scaricate.|  
|instanceCompletionAction|Valore che specifica se i dati dell'istanza del flusso di lavoro vengono conservati nell'archivio di persistenza in seguito al completamento dell'istanza del flusso di lavoro o se vengono eliminati. Questo valore è di tipo <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Le azioni enumerate consistono nell'eliminazione dei dati dell'istanza dall'archivio di persistenza o nella relativa conservazione al termine dell'operazione dell'istanza.<br /><br /> La conservazione delle istanze al completamento comporta la rapida crescita del database di persistenza e pertanto influisce sulle prestazioni del database. È consigliabile configurare criteri di cancellazione dei dati del database per eliminare questi record periodicamente e garantire che le prestazioni del database soddisfino il livello di prestazioni richiesto.|  
|instanceEncodingOption|Valore facoltativo che specifica se le informazioni sullo stato dell'istanza vengono compresse usando l'algoritmo GZip prima che le informazioni vengano salvate nell'archivio di persistenza. Questo valore è di tipo `System.Activities.DurableInstancing.InstanceEncodingAction`. I valori possibili per questa proprietà sono "None", che non specifica alcuna compressione e "GZip", che specifica tale istanza di dati viene compresso e l'algoritmo gzip.|  
|instanceLockedExceptionAction|Valore che specifica l'azione che si verifica in risposta a un'eccezione generata quando l'host tenta di bloccare un'istanza al momento bloccata da un altro host. Questo valore è di tipo <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Le opzioni consentite per questo campo sono: None, Basic Retry e Aggressive Retry. Il valore predefinito è None. Nell'elenco seguente sono riportate le descrizioni di queste tre opzioni:<br /><br /> -   Nessuno. L'host del servizio non tenta di bloccare l'istanza e passa <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante.<br />-Nuovo tentativo di base. L'host del servizio tenta di nuovo di bloccare l'istanza con un intervallo tra tentativi lineare e passa l'eccezione al chiamante alla fine della sequenza.<br />-Nuovo tentativo aggressiva. L'host del servizio tenta di nuovo di bloccare l'istanza con un ritardo che aumenta in modo esponenziale e passa <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante alla fine della sequenza.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento > di \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
 [Archivio di istanze del flusso di lavoro SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
