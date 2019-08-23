---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947171"
---
# <a name="workflowidle"></a><span data-ttu-id="a3fdc-101">\<> workflowIdle</span><span class="sxs-lookup"><span data-stu-id="a3fdc-101">\<workflowIdle></span></span>
<span data-ttu-id="a3fdc-102">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="a3fdc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a3fdc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3fdc-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="a3fdc-104">\<behaviors></span></span>  
<span data-ttu-id="a3fdc-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3fdc-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a3fdc-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a3fdc-106">\<behavior></span></span>  
<span data-ttu-id="a3fdc-107">\<> workflowIdle</span><span class="sxs-lookup"><span data-stu-id="a3fdc-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3fdc-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3fdc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3fdc-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3fdc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3fdc-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3fdc-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3fdc-111">Attributes</span></span>  
  
|<span data-ttu-id="a3fdc-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a3fdc-112">Attribute</span></span>|<span data-ttu-id="a3fdc-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a3fdc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3fdc-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="a3fdc-114">timeToPersist</span></span>|<span data-ttu-id="a3fdc-115">Valore TimeSpan che specifica l'intervallo di tempo tra il momento in cui il flusso di lavoro diventa inattivo e viene reso permanente.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="a3fdc-116">Il valore predefinito è TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="a3fdc-117">L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="a3fdc-118">Questo attributo è utile se si desidera mantenere un'istanza del flusso di lavoro in modo più aggressivo mantenendo comunque l'istanza in memoria per il periodo di tempo più lungo possibile.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="a3fdc-119">Questo attributo è valido solo se il relativo valore è minore dell'attributo **TimeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="a3fdc-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="a3fdc-120">Se è superiore, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="a3fdc-121">Se questo attributo scade prima del valore specificato dall'attributo **TimeToUnload** , è necessario completare la persistenza prima di scaricare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="a3fdc-122">Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="a3fdc-123">Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="a3fdc-124">Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a3fdc-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="a3fdc-125">timeToUnload</span></span>|<span data-ttu-id="a3fdc-126">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="a3fdc-127">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="a3fdc-128">Lo scaricamento di un flusso di lavoro lo rende anche persistente.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="a3fdc-129">Se questo attributo è impostato su zero, l'istanza del flusso di lavoro viene resa permanente e scaricata immediatamente dopo che il flusso di lavoro diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="a3fdc-130">Se si imposta questo attributo su TimeSpan. MaxValue, l'operazione di scaricamento viene disabilitata.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="a3fdc-131">Le istanze del flusso di lavoro inattive non vengono mai scaricate.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3fdc-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3fdc-132">Child Elements</span></span>  
 <span data-ttu-id="a3fdc-133">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3fdc-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3fdc-134">Parent Elements</span></span>  
  
|<span data-ttu-id="a3fdc-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3fdc-135">Element</span></span>|<span data-ttu-id="a3fdc-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3fdc-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3fdc-137">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a3fdc-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a3fdc-138">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3fdc-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3fdc-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
