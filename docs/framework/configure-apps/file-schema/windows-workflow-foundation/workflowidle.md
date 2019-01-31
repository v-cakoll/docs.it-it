---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: af8a2568eb13bb3007065c4b4a3564aae27de7ac
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280930"
---
# <a name="workflowidle"></a><span data-ttu-id="d6cad-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="d6cad-101">\<workflowIdle></span></span>
<span data-ttu-id="d6cad-102">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="d6cad-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="d6cad-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6cad-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6cad-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d6cad-104">\<behaviors></span></span>  
<span data-ttu-id="d6cad-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6cad-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="d6cad-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d6cad-106">\<behavior></span></span>  
<span data-ttu-id="d6cad-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="d6cad-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6cad-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6cad-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6cad-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6cad-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d6cad-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6cad-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6cad-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6cad-111">Attributes</span></span>  
  
|<span data-ttu-id="d6cad-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d6cad-112">Attribute</span></span>|<span data-ttu-id="d6cad-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6cad-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6cad-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="d6cad-114">timeToPersist</span></span>|<span data-ttu-id="d6cad-115">Valore Timespan che specifica l'intervallo di tempo tra il momento in cui il flusso di lavoro diviene inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="d6cad-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="d6cad-116">Il valore predefinito è TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="d6cad-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="d6cad-117">L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="d6cad-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="d6cad-118">Questo attributo è utile se si vuole rendere persistente un'istanza del flusso di lavoro in modo più aggressivo, mantenendo comunque l'istanza in memoria per più a lungo possibile.</span><span class="sxs-lookup"><span data-stu-id="d6cad-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="d6cad-119">Questo attributo è valido solo se il relativo valore è inferiore al **timeToUnload** attributo.</span><span class="sxs-lookup"><span data-stu-id="d6cad-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="d6cad-120">Se è superiore, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="d6cad-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="d6cad-121">Se questo attributo scade prima del valore specificato per il **timeToUnload** attributo, persistenza deve essere completata prima che il flusso di lavoro viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="d6cad-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="d6cad-122">Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente.</span><span class="sxs-lookup"><span data-stu-id="d6cad-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="d6cad-123">Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="d6cad-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="d6cad-124">Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="d6cad-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d6cad-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="d6cad-125">timeToUnload</span></span>|<span data-ttu-id="d6cad-126">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="d6cad-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="d6cad-127">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="d6cad-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="d6cad-128">Lo scaricamento di un flusso di lavoro lo rende anche persistente.</span><span class="sxs-lookup"><span data-stu-id="d6cad-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="d6cad-129">Se questo attributo è impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo il flusso di lavoro diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="d6cad-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="d6cad-130">Impostare questo attributo su TimeSpan. MaxValue in modo efficace la disabilitazione dell'operazione di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="d6cad-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="d6cad-131">Le istanze del flusso di lavoro inattive non vengono mai scaricate.</span><span class="sxs-lookup"><span data-stu-id="d6cad-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6cad-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6cad-132">Child Elements</span></span>  
 <span data-ttu-id="d6cad-133">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d6cad-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6cad-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6cad-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d6cad-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6cad-135">Element</span></span>|<span data-ttu-id="d6cad-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6cad-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6cad-137">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d6cad-137">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d6cad-138">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="d6cad-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6cad-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6cad-139">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
