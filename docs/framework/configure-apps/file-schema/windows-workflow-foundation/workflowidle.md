---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1dc186f5899935dab43c0d33894e659c4b19748c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201117"
---
# <a name="workflowidle"></a>\<workflowIdle>
Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<workflowIdle>  
  
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
|timeToPersist|Valore Timespan che specifica l'intervallo di tempo tra il momento in cui il flusso di lavoro diviene inattiva e persistente. Il valore predefinito è TimeSpan. MaxValue.<br /><br /> L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva. Questo attributo è utile se si vuole rendere persistente un'istanza del flusso di lavoro in modo più aggressivo, mantenendo comunque l'istanza in memoria per più a lungo possibile. Questo attributo è valido solo se il relativo valore è inferiore al **timeToUnload** attributo. Se è superiore, verrà ignorato. Se questo attributo scade prima del valore specificato per il **timeToUnload** attributo, persistenza deve essere completata prima che il flusso di lavoro viene scaricato. Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente. Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili. Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.|  
|timeToUnload|Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato. Il valore predefinito è 1 minuto.<br /><br /> Lo scaricamento di un flusso di lavoro lo rende anche persistente. Se questo attributo è impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo il flusso di lavoro diventa inattivo. Impostare questo attributo su TimeSpan. MaxValue in modo efficace la disabilitazione dell'operazione di scaricamento. Le istanze del flusso di lavoro inattive non vengono mai scaricate.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento > di \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
