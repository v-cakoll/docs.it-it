---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151845"
---
# <a name="workflowidle"></a>\<workflowIdle>
Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamenti>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di comportamento**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>workflowIdle**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|timeToPersist|Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene reso persistente. Il valore predefinito è TimeSpan.MaxValue.<br /><br /> L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva. Questo attributo è utile se si desidera imporre la persistenza di un'istanza del flusso di lavoro e al tempo stesso memorizzare l'istanza per il periodo di tempo più lungo possibile. Questo attributo è valido solo se il relativo valore è minore dell'attributo **timeToUnload.** Se è superiore, verrà ignorato. Se questo attributo scade prima del valore specificato dall'attributo **timeToUnload,** la persistenza deve essere completata prima dello scaricamento del flusso di lavoro. Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente. Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili. Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.|  
|timeToUnload|Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato. Il valore predefinito è 1 minuto.<br /><br /> Lo scaricamento di un flusso di lavoro lo rende anche persistente. Se questo attributo viene impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo che il flusso di lavoro diventa inattivo. L'impostazione di questo attributo su TimeSpan.MaxValue comporta in realtà la disabilitazione dell'operazione di scaricamento. Le istanze del flusso di lavoro inattive non vengono mai scaricate.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento> \<di serviceBehaviors>](behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
