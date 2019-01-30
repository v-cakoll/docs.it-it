---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 7fb298bcbc5b4bf5d699d3c79936ca3c15f67c0e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268184"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="a07da-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a07da-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="a07da-102">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a07da-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a07da-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="a07da-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="a07da-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a07da-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a07da-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a07da-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a07da-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a07da-106">\<tracking></span></span>  
<span data-ttu-id="a07da-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a07da-107">\<trackingProfile></span></span>  
<span data-ttu-id="a07da-108">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="a07da-108">\<workflow></span></span>  
<span data-ttu-id="a07da-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a07da-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="a07da-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a07da-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a07da-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a07da-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a07da-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a07da-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a07da-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a07da-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a07da-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a07da-114">Attributes</span></span>  
  
|<span data-ttu-id="a07da-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="a07da-115">Attribute</span></span>|<span data-ttu-id="a07da-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a07da-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a07da-117">name</span><span class="sxs-lookup"><span data-stu-id="a07da-117">name</span></span>|<span data-ttu-id="a07da-118">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="a07da-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a07da-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a07da-119">Child Elements</span></span>  
 <span data-ttu-id="a07da-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a07da-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a07da-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a07da-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a07da-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a07da-122">Element</span></span>|<span data-ttu-id="a07da-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a07da-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a07da-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a07da-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="a07da-125">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a07da-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a07da-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a07da-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a07da-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a07da-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a07da-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="a07da-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
