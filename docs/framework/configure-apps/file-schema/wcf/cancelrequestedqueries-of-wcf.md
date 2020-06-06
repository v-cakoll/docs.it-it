---
title: <cancelRequestedQueries>di WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850091"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="a1f27-102">\<cancelRequestedQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="a1f27-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="a1f27-103">Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a1f27-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a1f27-104">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="a1f27-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="a1f27-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a1f27-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="a1f27-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1f27-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1f27-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a1f27-107">Attributes and elements</span></span>  

<span data-ttu-id="a1f27-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a1f27-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1f27-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="a1f27-109">Attributes</span></span>

<span data-ttu-id="a1f27-110">No.</span><span class="sxs-lookup"><span data-stu-id="a1f27-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a1f27-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a1f27-111">Child elements</span></span>
  
|<span data-ttu-id="a1f27-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1f27-112">Element</span></span>|<span data-ttu-id="a1f27-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1f27-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="a1f27-114">Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="a1f27-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1f27-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a1f27-115">Parent elements</span></span>  
  
|<span data-ttu-id="a1f27-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1f27-116">Element</span></span>|<span data-ttu-id="a1f27-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1f27-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a1f27-118">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="a1f27-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1f27-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a1f27-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="a1f27-120">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a1f27-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a1f27-121">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="a1f27-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
