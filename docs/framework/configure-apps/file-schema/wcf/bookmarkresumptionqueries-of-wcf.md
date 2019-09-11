---
title: <bookmarkResumptionQueries>di WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850135"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="b5a4e-102">\<> bookmarkResumptionQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="b5a4e-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="b5a4e-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b5a4e-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="b5a4e-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b5a4e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="b5a4e-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b5a4e-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b5a4e-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="b5a4e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="b5a4e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="b5a4e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="b5a4e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="b5a4e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQueries**</span><span class="sxs-lookup"><span data-stu-id="b5a4e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="b5a4e-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5a4e-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5a4e-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b5a4e-114">Attributes and elements</span></span>  
  
<span data-ttu-id="b5a4e-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5a4e-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="b5a4e-116">Attributes</span></span>  
  
<span data-ttu-id="b5a4e-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5a4e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b5a4e-118">Child elements</span></span>  
  
|<span data-ttu-id="b5a4e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5a4e-119">Element</span></span>|<span data-ttu-id="b5a4e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5a4e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a4e-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="b5a4e-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="b5a4e-122">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b5a4e-123">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5a4e-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b5a4e-124">Parent elements</span></span>  
  
|<span data-ttu-id="b5a4e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5a4e-125">Element</span></span>|<span data-ttu-id="b5a4e-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5a4e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a4e-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b5a4e-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b5a4e-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5a4e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5a4e-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b5a4e-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5a4e-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b5a4e-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b5a4e-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
