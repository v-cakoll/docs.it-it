---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: ad41c1afec0b46a404f8f24882587c1dfeb68a80
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267807"
---
# <a name="activitystatequeries"></a><span data-ttu-id="731d7-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="731d7-101">\<activityStateQueries></span></span>
<span data-ttu-id="731d7-102">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="731d7-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="731d7-103">Ad esempio, è possibile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="731d7-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="731d7-104">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="731d7-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="731d7-105">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="731d7-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="731d7-106">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="731d7-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="731d7-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="731d7-107">\<system.serviceModel></span></span>  
<span data-ttu-id="731d7-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="731d7-108">\<tracking></span></span>  
<span data-ttu-id="731d7-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="731d7-109">\<trackingProfile></span></span>  
<span data-ttu-id="731d7-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="731d7-110">\<workflow></span></span>  
<span data-ttu-id="731d7-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="731d7-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731d7-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="731d7-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="731d7-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="731d7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="731d7-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="731d7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="731d7-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="731d7-115">Attributes</span></span>  
 <span data-ttu-id="731d7-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="731d7-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="731d7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="731d7-117">Child Elements</span></span>  
  
|<span data-ttu-id="731d7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="731d7-118">Element</span></span>|<span data-ttu-id="731d7-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="731d7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="731d7-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="731d7-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="731d7-121">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="731d7-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="731d7-122">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="731d7-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="731d7-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="731d7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="731d7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="731d7-124">Element</span></span>|<span data-ttu-id="731d7-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="731d7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="731d7-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="731d7-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="731d7-127">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="731d7-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="731d7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="731d7-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="731d7-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="731d7-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="731d7-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="731d7-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
