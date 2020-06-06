---
title: <activityScheduledQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850472"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="9f15f-102">\<activityScheduledQuery>di WCF</span><span class="sxs-lookup"><span data-stu-id="9f15f-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="9f15f-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="9f15f-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9f15f-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="9f15f-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="9f15f-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9f15f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="9f15f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f15f-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f15f-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9f15f-107">Attributes and elements</span></span>  

<span data-ttu-id="9f15f-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9f15f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f15f-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="9f15f-109">Attributes</span></span>  
  
|<span data-ttu-id="9f15f-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="9f15f-110">Attribute</span></span>|<span data-ttu-id="9f15f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f15f-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9f15f-112">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="9f15f-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="9f15f-113">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="9f15f-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f15f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9f15f-114">Child elements</span></span>

<span data-ttu-id="9f15f-115">No.</span><span class="sxs-lookup"><span data-stu-id="9f15f-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9f15f-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9f15f-116">Parent elements</span></span>  
  
|<span data-ttu-id="9f15f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f15f-117">Element</span></span>|<span data-ttu-id="9f15f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f15f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="9f15f-119">Raccolta di query utilizzate per tenere traccia di un'attività pianificata per l'esecuzione da un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="9f15f-119">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f15f-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9f15f-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="9f15f-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9f15f-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9f15f-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9f15f-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
