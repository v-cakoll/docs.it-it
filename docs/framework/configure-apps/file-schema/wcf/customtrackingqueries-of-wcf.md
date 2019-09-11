---
title: <customTrackingQueries>di WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855442"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="08e64-102">\<> customTrackingQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="08e64-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="08e64-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="08e64-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="08e64-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="08e64-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="08e64-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="08e64-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="08e64-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08e64-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08e64-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="08e64-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="08e64-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="08e64-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="08e64-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="08e64-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="08e64-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="08e64-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="08e64-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="08e64-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="08e64-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQueries**</span><span class="sxs-lookup"><span data-stu-id="08e64-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="08e64-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08e64-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08e64-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08e64-114">Attributes and elements</span></span>

<span data-ttu-id="08e64-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08e64-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08e64-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="08e64-116">Attributes</span></span>

<span data-ttu-id="08e64-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="08e64-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="08e64-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08e64-118">Child elements</span></span>
  
|<span data-ttu-id="08e64-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="08e64-119">Element</span></span>|<span data-ttu-id="08e64-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08e64-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08e64-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="08e64-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="08e64-122">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="08e64-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08e64-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08e64-123">Parent elements</span></span>  
  
|<span data-ttu-id="08e64-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="08e64-124">Element</span></span>|<span data-ttu-id="08e64-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08e64-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08e64-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="08e64-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="08e64-127">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="08e64-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08e64-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08e64-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="08e64-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="08e64-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="08e64-130">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="08e64-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
