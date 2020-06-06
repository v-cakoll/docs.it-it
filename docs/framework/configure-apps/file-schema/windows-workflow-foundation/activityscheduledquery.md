---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152411"
---
# \<activityScheduledQuery>
<span data-ttu-id="9c01f-101">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="9c01f-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9c01f-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="9c01f-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="9c01f-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9c01f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="9c01f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c01f-104">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c01f-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c01f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9c01f-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c01f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c01f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c01f-107">Attributes</span></span>  
  
|<span data-ttu-id="9c01f-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="9c01f-108">Attribute</span></span>|<span data-ttu-id="9c01f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c01f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c01f-110">activityName</span><span class="sxs-lookup"><span data-stu-id="9c01f-110">activityName</span></span>|<span data-ttu-id="9c01f-111">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="9c01f-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="9c01f-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="9c01f-112">childActivityName</span></span>|<span data-ttu-id="9c01f-113">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="9c01f-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c01f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c01f-114">Child Elements</span></span>  
 <span data-ttu-id="9c01f-115">No.</span><span class="sxs-lookup"><span data-stu-id="9c01f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c01f-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c01f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9c01f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c01f-117">Element</span></span>|<span data-ttu-id="9c01f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c01f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="9c01f-119">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="9c01f-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c01f-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9c01f-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9c01f-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9c01f-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c01f-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9c01f-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
