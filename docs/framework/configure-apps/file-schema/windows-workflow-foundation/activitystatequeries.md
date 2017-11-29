---
title: '&lt;activityStateQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9bcf80d215f9b889c59ab6e68d07ca656ffe93b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="ef0f2-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="ef0f2-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="ef0f2-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ef0f2-104">Ad esempio, è consigliabile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ef0f2-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ef0f2-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ef0f2-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ef0f2-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ef0f2-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-108">\<system.serviceModel></span></span>  
<span data-ttu-id="ef0f2-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-109">\<tracking></span></span>  
<span data-ttu-id="ef0f2-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-110">\<trackingProfile></span></span>  
<span data-ttu-id="ef0f2-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-111">\<workflow></span></span>  
<span data-ttu-id="ef0f2-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0f2-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef0f2-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef0f2-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef0f2-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ef0f2-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef0f2-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef0f2-116">Attributes</span></span>  
 <span data-ttu-id="ef0f2-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef0f2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef0f2-118">Child Elements</span></span>  
  
|<span data-ttu-id="ef0f2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef0f2-119">Element</span></span>|<span data-ttu-id="ef0f2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef0f2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef0f2-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="ef0f2-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ef0f2-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef0f2-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef0f2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ef0f2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef0f2-125">Element</span></span>|<span data-ttu-id="ef0f2-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef0f2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef0f2-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="ef0f2-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ef0f2-128">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="ef0f2-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef0f2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef0f2-129">See Also</span></span>  
 <span data-ttu-id="ef0f2-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ef0f2-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ef0f2-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ef0f2-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ef0f2-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef0f2-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ef0f2-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="ef0f2-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
