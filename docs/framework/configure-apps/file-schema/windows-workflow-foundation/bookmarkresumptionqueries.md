---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398858"
---
# \<bookmarkResumptionQueries>
<span data-ttu-id="fe842-101">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe842-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="fe842-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="fe842-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="fe842-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fe842-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="fe842-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe842-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe842-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fe842-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fe842-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fe842-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe842-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="fe842-107">Attributes</span></span>  
 <span data-ttu-id="fe842-108">No.</span><span class="sxs-lookup"><span data-stu-id="fe842-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe842-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fe842-109">Child Elements</span></span>  
  
|<span data-ttu-id="fe842-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe842-110">Element</span></span>|<span data-ttu-id="fe842-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe842-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="fe842-112">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe842-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="fe842-113">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="fe842-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe842-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fe842-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fe842-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe842-115">Element</span></span>|<span data-ttu-id="fe842-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe842-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="fe842-117">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="fe842-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe842-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fe842-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fe842-119">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe842-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fe842-120">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="fe842-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
