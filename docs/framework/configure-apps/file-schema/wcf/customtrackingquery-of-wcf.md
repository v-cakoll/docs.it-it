---
title: <customTrackingQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855429"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="4d095-102">\<customTrackingQuery>di WCF</span><span class="sxs-lookup"><span data-stu-id="4d095-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="4d095-103">Rappresenta una query utilizzata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="4d095-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="4d095-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4d095-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="4d095-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4d095-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="4d095-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d095-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d095-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d095-107">Attributes and elements</span></span>  

<span data-ttu-id="4d095-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d095-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d095-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d095-109">Attributes</span></span>  
  
|<span data-ttu-id="4d095-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d095-110">Attribute</span></span>|<span data-ttu-id="4d095-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d095-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="4d095-112">Stringa che specifica il nome dell'attività che ha generato il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="4d095-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="4d095-113">Stringa che specifica il nome del record di rilevamento personalizzato generato.</span><span class="sxs-lookup"><span data-stu-id="4d095-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d095-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d095-114">Child elements</span></span>

<span data-ttu-id="4d095-115">No.</span><span class="sxs-lookup"><span data-stu-id="4d095-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4d095-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d095-116">Parent elements</span></span>

|<span data-ttu-id="4d095-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d095-117">Element</span></span>|<span data-ttu-id="4d095-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d095-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="4d095-119">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="4d095-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="4d095-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4d095-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4d095-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4d095-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4d095-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4d095-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
