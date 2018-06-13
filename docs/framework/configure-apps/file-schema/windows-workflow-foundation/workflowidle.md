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
ms.locfileid: "32756904"
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="93823-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="93823-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="93823-103">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="93823-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="93823-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93823-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93823-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="93823-105">\<behaviors></span></span>  
<span data-ttu-id="93823-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="93823-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="93823-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="93823-107">\<behavior></span></span>  
<span data-ttu-id="93823-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="93823-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93823-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93823-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93823-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93823-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93823-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93823-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93823-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="93823-112">Attributes</span></span>  
  
|<span data-ttu-id="93823-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="93823-113">Attribute</span></span>|<span data-ttu-id="93823-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93823-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93823-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="93823-115">timeToPersist</span></span>|<span data-ttu-id="93823-116">Un valore Timespan che specifica la durata tra il momento il flusso di lavoro diventa inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="93823-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="93823-117">Il valore predefinito è di tipo TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="93823-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="93823-118">L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="93823-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="93823-119">Questo attributo è utile se si desidera rendere persistente un'istanza del flusso di lavoro in modo più aggressivo e continuare a mantenere l'istanza in memoria per il maggior tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="93823-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="93823-120">Questo attributo è valido solo se il relativo valore è inferiore a quello di **timeToUnload** attributo.</span><span class="sxs-lookup"><span data-stu-id="93823-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="93823-121">Se è superiore, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="93823-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="93823-122">Se questo attributo scade prima che il valore specificato per il **timeToUnload** attributo, persistenza deve essere completata prima che il flusso di lavoro viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="93823-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="93823-123">Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente.</span><span class="sxs-lookup"><span data-stu-id="93823-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="93823-124">Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="93823-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="93823-125">Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="93823-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="93823-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="93823-126">timeToUnload</span></span>|<span data-ttu-id="93823-127">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="93823-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="93823-128">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="93823-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="93823-129">Lo scaricamento di un flusso di lavoro lo rende anche persistente.</span><span class="sxs-lookup"><span data-stu-id="93823-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="93823-130">Se questo attributo è impostato su zero l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo il flusso di lavoro diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="93823-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="93823-131">L'impostazione di questo attributo su TimeSpan. MaxValue in modo efficace disabilita l'operazione di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="93823-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="93823-132">Le istanze del flusso di lavoro inattive non vengono mai scaricate.</span><span class="sxs-lookup"><span data-stu-id="93823-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93823-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93823-133">Child Elements</span></span>  
 <span data-ttu-id="93823-134">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="93823-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93823-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93823-135">Parent Elements</span></span>  
  
|<span data-ttu-id="93823-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="93823-136">Element</span></span>|<span data-ttu-id="93823-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93823-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93823-138">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="93823-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="93823-139">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="93823-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93823-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93823-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
