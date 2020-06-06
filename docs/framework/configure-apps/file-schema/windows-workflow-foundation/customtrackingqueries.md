---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152261"
---
# \<customTrackingQueries>
<span data-ttu-id="f6cc7-101">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f6cc7-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f6cc7-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f6cc7-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f6cc7-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f6cc7-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="f6cc7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6cc7-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6cc7-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f6cc7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f6cc7-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f6cc7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6cc7-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f6cc7-107">Attributes</span></span>  
 <span data-ttu-id="f6cc7-108">No.</span><span class="sxs-lookup"><span data-stu-id="f6cc7-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6cc7-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f6cc7-109">Child Elements</span></span>  
  
|<span data-ttu-id="f6cc7-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6cc7-110">Element</span></span>|<span data-ttu-id="f6cc7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6cc7-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="f6cc7-112">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="f6cc7-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6cc7-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f6cc7-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f6cc7-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6cc7-114">Element</span></span>|<span data-ttu-id="f6cc7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6cc7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f6cc7-116">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="f6cc7-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6cc7-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f6cc7-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f6cc7-118">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f6cc7-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f6cc7-119">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f6cc7-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
