---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398856"
---
# \<bookmarkResumptionQuery>
<span data-ttu-id="4b679-101">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4b679-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4b679-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="4b679-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="4b679-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4b679-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="4b679-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b679-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b679-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b679-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4b679-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b679-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b679-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b679-107">Attributes</span></span>  
  
|<span data-ttu-id="4b679-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4b679-108">Attribute</span></span>|<span data-ttu-id="4b679-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b679-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b679-110">name</span><span class="sxs-lookup"><span data-stu-id="4b679-110">name</span></span>|<span data-ttu-id="4b679-111">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="4b679-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b679-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b679-112">Child Elements</span></span>  
 <span data-ttu-id="4b679-113">No.</span><span class="sxs-lookup"><span data-stu-id="4b679-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b679-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b679-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4b679-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b679-115">Element</span></span>|<span data-ttu-id="4b679-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b679-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="4b679-117">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4b679-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b679-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4b679-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4b679-119">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4b679-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4b679-120">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4b679-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
