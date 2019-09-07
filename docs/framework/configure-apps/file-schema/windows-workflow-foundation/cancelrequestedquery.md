---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5de459717fdc0dbf946f12dceda18dce79ca4b06
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398810"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="14fec-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="14fec-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="14fec-102">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="14fec-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="14fec-103">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="14fec-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="14fec-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="14fec-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="14fec-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14fec-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="14fec-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="14fec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="14fec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="14fec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cancelRequestedQueries**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="14fec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="14fec-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> cancelRequestedQuery**</span><span class="sxs-lookup"><span data-stu-id="14fec-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fec-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14fec-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14fec-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14fec-113">Attributes and Elements</span></span>  
 <span data-ttu-id="14fec-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14fec-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14fec-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="14fec-115">Attributes</span></span>  
  
|<span data-ttu-id="14fec-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="14fec-116">Attribute</span></span>|<span data-ttu-id="14fec-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="14fec-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14fec-118">activityName</span><span class="sxs-lookup"><span data-stu-id="14fec-118">activityName</span></span>|<span data-ttu-id="14fec-119">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="14fec-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="14fec-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="14fec-120">childActivityName</span></span>|<span data-ttu-id="14fec-121">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="14fec-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14fec-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14fec-122">Child Elements</span></span>  
 <span data-ttu-id="14fec-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="14fec-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14fec-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14fec-124">Parent Elements</span></span>  
  
|<span data-ttu-id="14fec-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="14fec-125">Element</span></span>|<span data-ttu-id="14fec-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14fec-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14fec-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="14fec-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="14fec-128">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="14fec-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="14fec-129">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="14fec-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14fec-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14fec-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="14fec-131">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="14fec-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="14fec-132">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="14fec-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
