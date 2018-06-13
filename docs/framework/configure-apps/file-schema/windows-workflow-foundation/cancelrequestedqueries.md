---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 2abb2dc05bfec4419ca49d1517084ebc208e81e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757021"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="542f0-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="542f0-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="542f0-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="542f0-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="542f0-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="542f0-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="542f0-105">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="542f0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="542f0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="542f0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="542f0-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="542f0-107">\<tracking></span></span>  
<span data-ttu-id="542f0-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="542f0-108">\<trackingProfile></span></span>  
<span data-ttu-id="542f0-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="542f0-109">\<workflow></span></span>  
<span data-ttu-id="542f0-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="542f0-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="542f0-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="542f0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="542f0-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="542f0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="542f0-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="542f0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="542f0-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="542f0-114">Attributes</span></span>  
 <span data-ttu-id="542f0-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="542f0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="542f0-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="542f0-116">Child Elements</span></span>  
  
|<span data-ttu-id="542f0-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="542f0-117">Element</span></span>|<span data-ttu-id="542f0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="542f0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="542f0-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="542f0-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="542f0-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="542f0-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="542f0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="542f0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="542f0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="542f0-122">Element</span></span>|<span data-ttu-id="542f0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="542f0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="542f0-124">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="542f0-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="542f0-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="542f0-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="542f0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="542f0-126">See Also</span></span>  
 [<span data-ttu-id="542f0-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="542f0-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="542f0-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="542f0-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
