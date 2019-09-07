---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398856"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="5c80d-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="5c80d-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="5c80d-102">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5c80d-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="5c80d-103">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="5c80d-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="5c80d-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5c80d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c80d-106">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5c80d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5c80d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5c80d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5c80d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> bookmarkResumptionQueries**](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="5c80d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="5c80d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oggetto BookmarkResumptionQuery**</span><span class="sxs-lookup"><span data-stu-id="5c80d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c80d-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c80d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c80d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5c80d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5c80d-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5c80d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c80d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="5c80d-115">Attributes</span></span>  
  
|<span data-ttu-id="5c80d-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="5c80d-116">Attribute</span></span>|<span data-ttu-id="5c80d-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5c80d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c80d-118">name</span><span class="sxs-lookup"><span data-stu-id="5c80d-118">name</span></span>|<span data-ttu-id="5c80d-119">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="5c80d-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c80d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5c80d-120">Child Elements</span></span>  
 <span data-ttu-id="5c80d-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5c80d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c80d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5c80d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5c80d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c80d-123">Element</span></span>|<span data-ttu-id="5c80d-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5c80d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c80d-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="5c80d-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="5c80d-126">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5c80d-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c80d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c80d-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5c80d-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5c80d-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5c80d-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5c80d-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
