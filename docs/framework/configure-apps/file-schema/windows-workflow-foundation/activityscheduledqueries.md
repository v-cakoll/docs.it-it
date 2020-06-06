---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152424"
---
# \<activityScheduledQueries>
<span data-ttu-id="f9aed-101">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="f9aed-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="f9aed-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f9aed-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="f9aed-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f9aed-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="f9aed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9aed-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9aed-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9aed-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f9aed-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9aed-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9aed-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9aed-107">Attributes</span></span>  
 <span data-ttu-id="f9aed-108">No.</span><span class="sxs-lookup"><span data-stu-id="f9aed-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9aed-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9aed-109">Child Elements</span></span>  
  
|<span data-ttu-id="f9aed-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9aed-110">Element</span></span>|<span data-ttu-id="f9aed-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9aed-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="f9aed-112">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="f9aed-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9aed-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9aed-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f9aed-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9aed-114">Element</span></span>|<span data-ttu-id="f9aed-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9aed-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f9aed-116">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="f9aed-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9aed-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f9aed-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f9aed-118">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f9aed-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f9aed-119">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f9aed-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
