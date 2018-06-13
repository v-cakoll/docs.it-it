---
title: '&lt;activityStateQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: b2685da4d5ede9f3d880f6627e86db79b57ee395
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745341"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="9badf-102">&lt;activityStateQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="9badf-102">&lt;activityStateQueries&gt; of WCF</span></span>
<span data-ttu-id="9badf-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9badf-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="9badf-104">Ad esempio, è consigliabile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9badf-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="9badf-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="9badf-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="9badf-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="9badf-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="9badf-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9badf-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="9badf-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9badf-108">\<system.serviceModel></span></span>  
<span data-ttu-id="9badf-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="9badf-109">\<tracking></span></span>  
<span data-ttu-id="9badf-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9badf-110">\<trackingProfile></span></span>  
<span data-ttu-id="9badf-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9badf-111">\<workflow></span></span>  
<span data-ttu-id="9badf-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="9badf-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9badf-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9badf-113">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9badf-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9badf-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9badf-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9badf-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9badf-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="9badf-116">Attributes</span></span>  
 <span data-ttu-id="9badf-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9badf-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9badf-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9badf-118">Child Elements</span></span>  
  
|<span data-ttu-id="9badf-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9badf-119">Element</span></span>|<span data-ttu-id="9badf-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9badf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9badf-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="9badf-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="9badf-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="9badf-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9badf-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="9badf-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9badf-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9badf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9badf-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="9badf-125">Element</span></span>|<span data-ttu-id="9badf-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9badf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9badf-127">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="9badf-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9badf-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="9badf-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9badf-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9badf-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
 <xref:System.Activities.Tracking.ActivityStateQuery>    
 [<span data-ttu-id="9badf-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9badf-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9badf-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9badf-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
