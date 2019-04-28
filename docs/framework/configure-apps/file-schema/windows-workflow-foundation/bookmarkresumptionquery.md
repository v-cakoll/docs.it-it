---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790273"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="82ecb-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="82ecb-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="82ecb-102">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82ecb-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="82ecb-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="82ecb-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="82ecb-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="82ecb-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="82ecb-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="82ecb-105">\<system.serviceModel></span></span>  
<span data-ttu-id="82ecb-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="82ecb-106">\<tracking></span></span>  
<span data-ttu-id="82ecb-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="82ecb-107">\<trackingProfile></span></span>  
<span data-ttu-id="82ecb-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="82ecb-108">\<workflow></span></span>  
<span data-ttu-id="82ecb-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="82ecb-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="82ecb-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="82ecb-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ecb-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82ecb-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82ecb-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="82ecb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="82ecb-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="82ecb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82ecb-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="82ecb-114">Attributes</span></span>  
  
|<span data-ttu-id="82ecb-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="82ecb-115">Attribute</span></span>|<span data-ttu-id="82ecb-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82ecb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82ecb-117">name</span><span class="sxs-lookup"><span data-stu-id="82ecb-117">name</span></span>|<span data-ttu-id="82ecb-118">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="82ecb-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82ecb-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="82ecb-119">Child Elements</span></span>  
 <span data-ttu-id="82ecb-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="82ecb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82ecb-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="82ecb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="82ecb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="82ecb-122">Element</span></span>|<span data-ttu-id="82ecb-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82ecb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82ecb-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="82ecb-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="82ecb-125">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82ecb-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82ecb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82ecb-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="82ecb-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="82ecb-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="82ecb-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="82ecb-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
