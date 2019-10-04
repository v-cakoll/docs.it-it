---
title: <bookmarkResumptionQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833999"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="3c8c2-102">\<> oggetto BookmarkResumptionQuery di WCF</span><span class="sxs-lookup"><span data-stu-id="3c8c2-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="3c8c2-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3c8c2-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="3c8c2-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3c8c2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="3c8c2-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c8c2-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3c8c2-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="3c8c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="3c8c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="3c8c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="3c8c2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="3c8c2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> bookmarkResumptionQueries**](bookmarkresumptionqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)</span></span>\
<span data-ttu-id="3c8c2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oggetto BookmarkResumptionQuery**</span><span class="sxs-lookup"><span data-stu-id="3c8c2-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8c2-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c8c2-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c8c2-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3c8c2-115">Attributes and elements</span></span>

<span data-ttu-id="3c8c2-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c8c2-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="3c8c2-117">Attributes</span></span>  
  
|<span data-ttu-id="3c8c2-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="3c8c2-118">Attribute</span></span>|<span data-ttu-id="3c8c2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c8c2-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="3c8c2-120">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-120">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c8c2-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3c8c2-121">Child elements</span></span>

<span data-ttu-id="3c8c2-122">No.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3c8c2-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3c8c2-123">Parent elements</span></span>  
  
|<span data-ttu-id="3c8c2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c8c2-124">Element</span></span>|<span data-ttu-id="3c8c2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c8c2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c8c2-126">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="3c8c2-126">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="3c8c2-127">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3c8c2-127">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c8c2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c8c2-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3c8c2-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3c8c2-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c8c2-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3c8c2-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
