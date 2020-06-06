---
title: <activityScheduledQueries>di WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850499"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="3e72a-102">\<activityScheduledQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="3e72a-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="3e72a-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3e72a-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3e72a-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3e72a-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="3e72a-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3e72a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="3e72a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e72a-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e72a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3e72a-107">Attributes and elements</span></span>  

<span data-ttu-id="3e72a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3e72a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e72a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="3e72a-109">Attributes</span></span>  

<span data-ttu-id="3e72a-110">No.</span><span class="sxs-lookup"><span data-stu-id="3e72a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e72a-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3e72a-111">Child elements</span></span>  
  
|<span data-ttu-id="3e72a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e72a-112">Element</span></span>|<span data-ttu-id="3e72a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e72a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="3e72a-114">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3e72a-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e72a-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3e72a-115">Parent elements</span></span>  
  
|<span data-ttu-id="3e72a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e72a-116">Element</span></span>|<span data-ttu-id="3e72a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e72a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="3e72a-118">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="3e72a-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e72a-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3e72a-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="3e72a-120">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3e72a-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3e72a-121">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3e72a-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
