---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152209"
---
# \<customTrackingQuery>
<span data-ttu-id="6db88-101">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6db88-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6db88-102">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6db88-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6db88-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6db88-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="6db88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6db88-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6db88-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6db88-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6db88-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6db88-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6db88-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6db88-107">Attributes</span></span>  
  
|<span data-ttu-id="6db88-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6db88-108">Attribute</span></span>|<span data-ttu-id="6db88-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6db88-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6db88-110">activityName</span><span class="sxs-lookup"><span data-stu-id="6db88-110">activityName</span></span>|<span data-ttu-id="6db88-111">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="6db88-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="6db88-112">name</span><span class="sxs-lookup"><span data-stu-id="6db88-112">name</span></span>|<span data-ttu-id="6db88-113">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="6db88-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6db88-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6db88-114">Child Elements</span></span>  
 <span data-ttu-id="6db88-115">No.</span><span class="sxs-lookup"><span data-stu-id="6db88-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6db88-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6db88-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6db88-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6db88-117">Element</span></span>|<span data-ttu-id="6db88-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6db88-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="6db88-119">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="6db88-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6db88-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6db88-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6db88-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6db88-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6db88-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6db88-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
