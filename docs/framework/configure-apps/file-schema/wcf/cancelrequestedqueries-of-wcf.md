---
title: <cancelRequestedQueries>di WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850091"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="4be59-102">\<> cancelRequestedQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="4be59-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="4be59-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4be59-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4be59-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="4be59-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="4be59-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4be59-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4be59-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4be59-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="4be59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="4be59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="4be59-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="4be59-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4be59-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="4be59-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> cancelRequestedQueries**</span><span class="sxs-lookup"><span data-stu-id="4be59-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be59-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4be59-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4be59-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4be59-114">Attributes and elements</span></span>  

<span data-ttu-id="4be59-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4be59-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4be59-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="4be59-116">Attributes</span></span>

<span data-ttu-id="4be59-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4be59-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4be59-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4be59-118">Child elements</span></span>
  
|<span data-ttu-id="4be59-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4be59-119">Element</span></span>|<span data-ttu-id="4be59-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4be59-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4be59-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="4be59-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="4be59-122">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4be59-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4be59-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4be59-123">Parent elements</span></span>  
  
|<span data-ttu-id="4be59-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4be59-124">Element</span></span>|<span data-ttu-id="4be59-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4be59-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4be59-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4be59-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="4be59-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="4be59-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4be59-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4be59-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="4be59-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4be59-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4be59-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4be59-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
