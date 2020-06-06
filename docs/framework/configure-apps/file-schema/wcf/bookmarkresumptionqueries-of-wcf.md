---
title: <bookmarkResumptionQueries>di WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850135"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="80010-102">\<bookmarkResumptionQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="80010-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="80010-103">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="80010-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="80010-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="80010-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="80010-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="80010-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="80010-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80010-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80010-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="80010-107">Attributes and elements</span></span>  
  
<span data-ttu-id="80010-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="80010-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80010-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="80010-109">Attributes</span></span>  
  
<span data-ttu-id="80010-110">No.</span><span class="sxs-lookup"><span data-stu-id="80010-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80010-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="80010-111">Child elements</span></span>  
  
|<span data-ttu-id="80010-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="80010-112">Element</span></span>|<span data-ttu-id="80010-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80010-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="80010-114">Query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="80010-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="80010-115">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="80010-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80010-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="80010-116">Parent elements</span></span>  
  
|<span data-ttu-id="80010-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="80010-117">Element</span></span>|<span data-ttu-id="80010-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80010-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="80010-119">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="80010-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80010-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="80010-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="80010-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="80010-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80010-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="80010-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
