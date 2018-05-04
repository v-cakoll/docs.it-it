---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.  
  
\<system.ServiceModel>  
\<i comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<workflowIdle >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|timeToPersist|Un valore Timespan che specifica la durata tra il momento il flusso di lavoro diventa inattiva e persistente. Il valore predefinito è di tipo TimeSpan. MaxValue.<br /><br /> L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva. Questo attributo è utile se si desidera rendere persistente un'istanza del flusso di lavoro in modo più aggressivo e continuare a mantenere l'istanza in memoria per il maggior tempo possibile. Questo attributo è valido solo se il relativo valore è inferiore a quello di **timeToUnload** attributo. Se è superiore, verrà ignorato. Se questo attributo scade prima che il valore specificato per il **timeToUnload** attributo, persistenza deve essere completata prima che il flusso di lavoro viene scaricato. Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente. Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili. Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.|  
|timeToUnload|Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato. Il valore predefinito è 1 minuto.<br /><br /> Lo scaricamento di un flusso di lavoro lo rende anche persistente. Se questo attributo è impostato su zero l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo il flusso di lavoro diventa inattivo. L'impostazione di questo attributo su TimeSpan. MaxValue in modo efficace disabilita l'operazione di scaricamento. Le istanze del flusso di lavoro inattive non vengono mai scaricate.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento > di \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
