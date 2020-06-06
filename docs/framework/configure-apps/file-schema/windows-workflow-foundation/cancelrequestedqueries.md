---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152307"
---
# \<cancelRequestedQueries>
<span data-ttu-id="e0527-101">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e0527-101">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e0527-102">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="e0527-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="e0527-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e0527-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="e0527-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0527-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0527-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e0527-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e0527-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e0527-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0527-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="e0527-107">Attributes</span></span>  
 <span data-ttu-id="e0527-108">No.</span><span class="sxs-lookup"><span data-stu-id="e0527-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0527-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e0527-109">Child Elements</span></span>  
  
|<span data-ttu-id="e0527-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0527-110">Element</span></span>|<span data-ttu-id="e0527-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0527-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery.md)|<span data-ttu-id="e0527-112">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e0527-112">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0527-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e0527-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e0527-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0527-114">Element</span></span>|<span data-ttu-id="e0527-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0527-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="e0527-116">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="e0527-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0527-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e0527-117">See also</span></span>

- [<span data-ttu-id="e0527-118">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e0527-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e0527-119">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="e0527-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
