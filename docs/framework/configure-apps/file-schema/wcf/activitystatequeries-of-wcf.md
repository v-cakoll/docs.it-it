---
title: '&lt;activityStateQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fbdd10680da784255a72069a0c1cc240cbe3f15e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="8438c-102">&lt;activityStateQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="8438c-102">&lt;activityStateQueries&gt; of WCF</span></span>
<span data-ttu-id="8438c-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8438c-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8438c-104">Ad esempio, è consigliabile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8438c-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8438c-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="8438c-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8438c-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="8438c-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="8438c-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8438c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="8438c-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8438c-108">\<system.serviceModel></span></span>  
<span data-ttu-id="8438c-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="8438c-109">\<tracking></span></span>  
<span data-ttu-id="8438c-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8438c-110">\<trackingProfile></span></span>  
<span data-ttu-id="8438c-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8438c-111">\<workflow></span></span>  
<span data-ttu-id="8438c-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8438c-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8438c-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8438c-113">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8438c-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8438c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="8438c-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8438c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8438c-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="8438c-116">Attributes</span></span>  
 <span data-ttu-id="8438c-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8438c-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8438c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8438c-118">Child Elements</span></span>  
  
|<span data-ttu-id="8438c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8438c-119">Element</span></span>|<span data-ttu-id="8438c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8438c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8438c-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8438c-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="8438c-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8438c-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8438c-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="8438c-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8438c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8438c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8438c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8438c-125">Element</span></span>|<span data-ttu-id="8438c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8438c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8438c-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8438c-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8438c-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8438c-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8438c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8438c-129">See Also</span></span>  
 <span data-ttu-id="8438c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="8438c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection></span></span>    
 <span data-ttu-id="8438c-131"><xref:System.Activities.Tracking.ActivityStateQuery></span><span class="sxs-lookup"><span data-stu-id="8438c-131"><xref:System.Activities.Tracking.ActivityStateQuery></span></span>    
 [<span data-ttu-id="8438c-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8438c-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8438c-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8438c-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
