---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152307"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="46045-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="46045-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="46045-102">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="46045-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="46045-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="46045-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="46045-104">Per altre informazioni sulle query del profilo di rilevamento, vedere [Profili di rilevamentoFor more](../../../windows-workflow-foundation/tracking-profiles.md) information on tracking profile queries, see Tracking Profiles</span><span class="sxs-lookup"><span data-stu-id="46045-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="46045-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="46045-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="46045-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="46045-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="46045-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="46045-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="46045-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="46045-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="46045-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="46045-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="46045-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span><span class="sxs-lookup"><span data-stu-id="46045-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46045-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46045-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46045-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="46045-112">Attributes and Elements</span></span>  
 <span data-ttu-id="46045-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="46045-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46045-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="46045-114">Attributes</span></span>  
 <span data-ttu-id="46045-115">No.</span><span class="sxs-lookup"><span data-stu-id="46045-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46045-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="46045-116">Child Elements</span></span>  
  
|<span data-ttu-id="46045-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="46045-117">Element</span></span>|<span data-ttu-id="46045-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46045-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46045-119">\<>cancelRequestedQuery</span><span class="sxs-lookup"><span data-stu-id="46045-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="46045-120">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="46045-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46045-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="46045-121">Parent Elements</span></span>  
  
|<span data-ttu-id="46045-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="46045-122">Element</span></span>|<span data-ttu-id="46045-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46045-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46045-124">\<>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="46045-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="46045-125">Elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dalla proprietà **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="46045-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46045-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46045-126">See also</span></span>

- [<span data-ttu-id="46045-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="46045-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="46045-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="46045-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
