---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152287"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="e685e-101">\<RequestedQuery></span><span class="sxs-lookup"><span data-stu-id="e685e-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="e685e-102">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e685e-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e685e-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="e685e-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="e685e-104">Per ulteriori informazioni sulle query dei profili di rilevamento, vedere [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e685e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e685e-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e685e-106">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e685e-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e685e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e685e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e685e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="e685e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="e685e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>cancelRequestedQuery**</span><span class="sxs-lookup"><span data-stu-id="e685e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e685e-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e685e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e685e-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e685e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e685e-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e685e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e685e-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="e685e-115">Attributes</span></span>  
  
|<span data-ttu-id="e685e-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="e685e-116">Attribute</span></span>|<span data-ttu-id="e685e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e685e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e685e-118">activityName</span><span class="sxs-lookup"><span data-stu-id="e685e-118">activityName</span></span>|<span data-ttu-id="e685e-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="e685e-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="e685e-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="e685e-120">childActivityName</span></span>|<span data-ttu-id="e685e-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="e685e-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e685e-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e685e-122">Child Elements</span></span>  
 <span data-ttu-id="e685e-123">No.</span><span class="sxs-lookup"><span data-stu-id="e685e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e685e-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e685e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e685e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e685e-125">Element</span></span>|<span data-ttu-id="e685e-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e685e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e685e-127">\<>faultPropagationQuery</span><span class="sxs-lookup"><span data-stu-id="e685e-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="e685e-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e685e-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e685e-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="e685e-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e685e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e685e-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e685e-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e685e-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e685e-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e685e-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
