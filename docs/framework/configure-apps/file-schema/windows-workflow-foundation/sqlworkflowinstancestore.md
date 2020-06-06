---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 56a44fdb62062903ca3ad00f8105a66ccab02cca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151962"
---
# \<sqlWorkflowInstanceStore>
Comportamento del servizio che consente di configurare la funzionalità <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che supporta la persistenza delle informazioni sullo stato per le istanze del servizio flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008. Per ulteriori informazioni su questa funzionalità, vedere l' [Archivio di istanze del flusso di lavoro SQL](../../../windows-workflow-foundation/sql-workflow-instance-store.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sqlWorkflowInstanceStore>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String"
                                hostLockRenewalPeriod="TimeSpan"
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
|connectionString|Stringa contenente una stringa di connessione utilizzata per connettersi a un database di persistenza sottostante.|  
|connectionStringName|Stringa contenente una stringa di connessione denominata per il server database. Un esempio di stringa di connessione denominata è "DefaultConnectionString".|  
|hostLockRenewalPeriod|Valore TimeSpan che specifica il periodo di tempo entro il quale l'host deve rinnovare il blocco su un'istanza. Se l'host non rinnova il blocco nel periodo di tempo specificato, l'istanza viene sbloccata e può essere scelta da un altro host.<br /><br /> Lo scaricamento di un flusso di lavoro lo rende anche persistente. Se questo attributo viene impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo che il flusso di lavoro diventa inattivo. L'impostazione di questo attributo su TimeSpan.MaxValue comporta in realtà la disabilitazione dell'operazione di scaricamento. Le istanze del flusso di lavoro inattive non vengono mai scaricate.|  
|instanceCompletionAction|Valore che specifica se i dati dell'istanza del flusso di lavoro vengono conservati nell'archivio di persistenza in seguito al completamento dell'istanza del flusso di lavoro o se vengono eliminati. Questo valore è di tipo <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Le azioni enumerate consistono nell'eliminazione dei dati dell'istanza dall'archivio di persistenza o nella relativa conservazione al termine dell'operazione dell'istanza.<br /><br /> La conservazione delle istanze al completamento comporta la rapida crescita del database di persistenza e pertanto influisce sulle prestazioni del database. È consigliabile configurare criteri di cancellazione dei dati del database per eliminare questi record periodicamente e garantire che le prestazioni del database soddisfino il livello di prestazioni richiesto.|  
|instanceEncodingOption|Valore facoltativo che specifica se le informazioni sullo stato dell'istanza vengono compresse utilizzando l'algoritmo GZip prima che le informazioni vengano salvate nell'archivio di persistenza. Questo valore è di tipo <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. I valori possibili per questa proprietà sono <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None> , che non specifica alcuna compressione e <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip> , che specifica che i dati dell'istanza vengono compressi e utilizza l'algoritmo gzip.|  
|instanceLockedExceptionAction|Valore che specifica l'azione che si verifica in risposta a un'eccezione generata quando l'host tenta di bloccare un'istanza al momento bloccata da un altro host. Questo valore è di tipo <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Le opzioni consentite per questo campo sono: None, Basic Retry e Aggressive Retry. Il valore predefinito è None (Nessuna). Nell'elenco seguente sono riportate le descrizioni di queste tre opzioni:<br /><br /> -   Nessuno. L'host del servizio non tenta di bloccare l'istanza e passa <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante.<br />-Riprova di base. L'host del servizio tenta di nuovo di bloccare l'istanza con un intervallo tra tentativi lineare e passa l'eccezione al chiamante alla fine della sequenza.<br />-Tentativo aggressivo. L'host del servizio tenta di nuovo di bloccare l'istanza con un ritardo che aumenta in modo esponenziale e passa <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante alla fine della sequenza.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>di\<serviceBehaviors>](behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [Archivio di istanze del flusso di lavoro SQL](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
