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
# <a name="workflowidle"></a><span data-ttu-id="7d05a-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="7d05a-101">\<workflowIdle></span></span>
<span data-ttu-id="7d05a-102">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="7d05a-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="7d05a-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d05a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d05a-104">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7d05a-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="7d05a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamenti>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7d05a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7d05a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7d05a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7d05a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di comportamento**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7d05a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7d05a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>workflowIdle**</span><span class="sxs-lookup"><span data-stu-id="7d05a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d05a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d05a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d05a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d05a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d05a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d05a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d05a-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="7d05a-112">Attributes</span></span>  
  
|<span data-ttu-id="7d05a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d05a-113">Attribute</span></span>|<span data-ttu-id="7d05a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d05a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d05a-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="7d05a-115">timeToPersist</span></span>|<span data-ttu-id="7d05a-116">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene reso persistente.</span><span class="sxs-lookup"><span data-stu-id="7d05a-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="7d05a-117">Il valore predefinito è TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="7d05a-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="7d05a-118">L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="7d05a-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="7d05a-119">Questo attributo è utile se si desidera imporre la persistenza di un'istanza del flusso di lavoro e al tempo stesso memorizzare l'istanza per il periodo di tempo più lungo possibile.</span><span class="sxs-lookup"><span data-stu-id="7d05a-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="7d05a-120">Questo attributo è valido solo se il relativo valore è minore dell'attributo **timeToUnload.**</span><span class="sxs-lookup"><span data-stu-id="7d05a-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="7d05a-121">Se è superiore, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="7d05a-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="7d05a-122">Se questo attributo scade prima del valore specificato dall'attributo **timeToUnload,** la persistenza deve essere completata prima dello scaricamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7d05a-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="7d05a-123">Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente.</span><span class="sxs-lookup"><span data-stu-id="7d05a-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="7d05a-124">Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="7d05a-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="7d05a-125">Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="7d05a-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="7d05a-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="7d05a-126">timeToUnload</span></span>|<span data-ttu-id="7d05a-127">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="7d05a-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="7d05a-128">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="7d05a-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="7d05a-129">Lo scaricamento di un flusso di lavoro lo rende anche persistente.</span><span class="sxs-lookup"><span data-stu-id="7d05a-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="7d05a-130">Se questo attributo viene impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo che il flusso di lavoro diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="7d05a-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="7d05a-131">L'impostazione di questo attributo su TimeSpan.MaxValue comporta in realtà la disabilitazione dell'operazione di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="7d05a-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="7d05a-132">Le istanze del flusso di lavoro inattive non vengono mai scaricate.</span><span class="sxs-lookup"><span data-stu-id="7d05a-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d05a-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d05a-133">Child Elements</span></span>  
 <span data-ttu-id="7d05a-134">No.</span><span class="sxs-lookup"><span data-stu-id="7d05a-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d05a-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d05a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7d05a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d05a-136">Element</span></span>|<span data-ttu-id="7d05a-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d05a-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d05a-138">\<comportamento> \<di serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7d05a-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="7d05a-139">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="7d05a-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d05a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d05a-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
