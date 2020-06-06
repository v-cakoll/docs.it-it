---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151845"
---
# \<workflowIdle>
<span data-ttu-id="c90be-101">Un comportamento del servizio che controlla quando istanze del flusso di lavoro inattive vengono scaricate e rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="c90be-101">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a><span data-ttu-id="c90be-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c90be-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c90be-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c90be-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c90be-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c90be-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c90be-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="c90be-105">Attributes</span></span>  
  
|<span data-ttu-id="c90be-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="c90be-106">Attribute</span></span>|<span data-ttu-id="c90be-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c90be-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c90be-108">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c90be-108">timeToPersist</span></span>|<span data-ttu-id="c90be-109">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene reso persistente.</span><span class="sxs-lookup"><span data-stu-id="c90be-109">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c90be-110">Il valore predefinito è TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c90be-110">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c90be-111">L'intervallo di tempo inizia quando l'istanza del flusso di lavoro diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="c90be-111">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c90be-112">Questo attributo è utile se si desidera imporre la persistenza di un'istanza del flusso di lavoro e al tempo stesso memorizzare l'istanza per il periodo di tempo più lungo possibile.</span><span class="sxs-lookup"><span data-stu-id="c90be-112">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c90be-113">Questo attributo è valido solo se il relativo valore è minore dell'attributo **TimeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="c90be-113">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c90be-114">Se è superiore, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="c90be-114">If it is greater, it is ignored.</span></span> <span data-ttu-id="c90be-115">Se questo attributo scade prima del valore specificato dall'attributo **TimeToUnload** , è necessario completare la persistenza prima di scaricare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c90be-115">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c90be-116">Questo significa che l'operazione di scaricamento può essere ritardata fino a quando il flusso di lavoro non verrà reso persistente.</span><span class="sxs-lookup"><span data-stu-id="c90be-116">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c90be-117">Il livello di persistenza è responsabile della gestione dei tentativi effettuati in presenza di errori temporanei e genera eccezioni solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="c90be-117">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c90be-118">Le eventuali eccezioni generate durante la persistenza vengono pertanto considerate fatali e l'istanza del flusso di lavoro viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="c90be-118">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c90be-119">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c90be-119">timeToUnload</span></span>|<span data-ttu-id="c90be-120">Valore TimeSpan che specifica l'intervallo di tempo tra l'ora in cui il flusso di lavoro diventa inattivo e quella in cui viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="c90be-120">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c90be-121">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="c90be-121">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c90be-122">Lo scaricamento di un flusso di lavoro lo rende anche persistente.</span><span class="sxs-lookup"><span data-stu-id="c90be-122">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c90be-123">Se questo attributo viene impostato su zero, l'istanza del flusso di lavoro viene resa persistente e scaricata immediatamente dopo che il flusso di lavoro diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="c90be-123">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c90be-124">L'impostazione di questo attributo su TimeSpan.MaxValue comporta in realtà la disabilitazione dell'operazione di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="c90be-124">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c90be-125">Le istanze del flusso di lavoro inattive non vengono mai scaricate.</span><span class="sxs-lookup"><span data-stu-id="c90be-125">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c90be-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c90be-126">Child Elements</span></span>  
 <span data-ttu-id="c90be-127">No.</span><span class="sxs-lookup"><span data-stu-id="c90be-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c90be-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c90be-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c90be-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="c90be-129">Element</span></span>|<span data-ttu-id="c90be-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c90be-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c90be-131">\<behavior>di\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c90be-131">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c90be-132">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c90be-132">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c90be-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c90be-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
