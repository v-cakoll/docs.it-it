---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 457cc3aaa921016e553eb40bcee72af5de3c7179
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="8756b-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8756b-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="8756b-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8756b-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8756b-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="8756b-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="8756b-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8756b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8756b-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8756b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8756b-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="8756b-107">\<tracking></span></span>  
<span data-ttu-id="8756b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8756b-108">\<trackingProfile></span></span>  
<span data-ttu-id="8756b-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8756b-109">\<workflow></span></span>  
<span data-ttu-id="8756b-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="8756b-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8756b-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8756b-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8756b-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8756b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8756b-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8756b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8756b-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8756b-114">Attributes</span></span>  
 <span data-ttu-id="8756b-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8756b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8756b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8756b-116">Child Elements</span></span>  
  
|<span data-ttu-id="8756b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8756b-117">Element</span></span>|<span data-ttu-id="8756b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8756b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8756b-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="8756b-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="8756b-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="8756b-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8756b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8756b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8756b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8756b-122">Element</span></span>|<span data-ttu-id="8756b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8756b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8756b-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="8756b-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8756b-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="8756b-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8756b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8756b-126">See Also</span></span>  
 [<span data-ttu-id="8756b-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8756b-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8756b-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8756b-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
