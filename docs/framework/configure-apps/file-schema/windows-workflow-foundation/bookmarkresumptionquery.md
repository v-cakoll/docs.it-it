---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945965"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="85844-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="85844-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="85844-102">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="85844-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="85844-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="85844-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="85844-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="85844-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="85844-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="85844-105">\<system.serviceModel></span></span>  
<span data-ttu-id="85844-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="85844-106">\<tracking></span></span>  
<span data-ttu-id="85844-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="85844-107">\<trackingProfile></span></span>  
<span data-ttu-id="85844-108">\<> flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="85844-108">\<workflow></span></span>  
<span data-ttu-id="85844-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="85844-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="85844-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="85844-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85844-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85844-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85844-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="85844-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85844-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="85844-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85844-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="85844-114">Attributes</span></span>  
  
|<span data-ttu-id="85844-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="85844-115">Attribute</span></span>|<span data-ttu-id="85844-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="85844-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85844-117">name</span><span class="sxs-lookup"><span data-stu-id="85844-117">name</span></span>|<span data-ttu-id="85844-118">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="85844-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85844-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="85844-119">Child Elements</span></span>  
 <span data-ttu-id="85844-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="85844-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85844-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="85844-121">Parent Elements</span></span>  
  
|<span data-ttu-id="85844-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="85844-122">Element</span></span>|<span data-ttu-id="85844-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85844-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85844-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="85844-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="85844-125">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="85844-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85844-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85844-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="85844-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="85844-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="85844-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="85844-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
