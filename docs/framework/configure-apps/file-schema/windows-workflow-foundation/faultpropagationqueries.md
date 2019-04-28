---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790156"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="f8008-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="f8008-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="f8008-102">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f8008-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f8008-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="f8008-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f8008-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f8008-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f8008-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="f8008-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="f8008-106">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f8008-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f8008-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f8008-107">\<system.serviceModel></span></span>  
<span data-ttu-id="f8008-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f8008-108">\<tracking></span></span>  
<span data-ttu-id="f8008-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f8008-109">\<trackingProfile></span></span>  
<span data-ttu-id="f8008-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="f8008-110">\<workflow></span></span>  
<span data-ttu-id="f8008-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="f8008-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8008-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8008-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8008-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8008-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f8008-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8008-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8008-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8008-115">Attributes</span></span>  
 <span data-ttu-id="f8008-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f8008-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f8008-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8008-117">Child Elements</span></span>  
  
|<span data-ttu-id="f8008-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8008-118">Element</span></span>|<span data-ttu-id="f8008-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8008-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8008-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f8008-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="f8008-121">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f8008-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f8008-122">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="f8008-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8008-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8008-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f8008-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8008-124">Element</span></span>|<span data-ttu-id="f8008-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8008-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8008-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f8008-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f8008-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8008-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8008-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8008-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f8008-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8008-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f8008-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f8008-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
