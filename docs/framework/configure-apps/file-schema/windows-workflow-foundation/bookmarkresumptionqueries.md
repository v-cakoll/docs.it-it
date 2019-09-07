---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398858"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="7f9d7-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="7f9d7-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="7f9d7-102">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7f9d7-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="7f9d7-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7f9d7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f9d7-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="7f9d7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="7f9d7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="7f9d7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7f9d7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="7f9d7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQueries**</span><span class="sxs-lookup"><span data-stu-id="7f9d7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="7f9d7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f9d7-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f9d7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f9d7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7f9d7-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f9d7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f9d7-114">Attributes</span></span>  
 <span data-ttu-id="7f9d7-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f9d7-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f9d7-116">Child Elements</span></span>  
  
|<span data-ttu-id="7f9d7-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f9d7-117">Element</span></span>|<span data-ttu-id="7f9d7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f9d7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f9d7-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="7f9d7-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="7f9d7-120">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7f9d7-121">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="7f9d7-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f9d7-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f9d7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7f9d7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f9d7-123">Element</span></span>|<span data-ttu-id="7f9d7-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f9d7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f9d7-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7f9d7-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="7f9d7-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="7f9d7-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f9d7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f9d7-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7f9d7-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7f9d7-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7f9d7-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="7f9d7-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
