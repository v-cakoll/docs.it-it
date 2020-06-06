---
title: <customTrackingQueries>di WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855442"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="9e7f6-102">\<customTrackingQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="9e7f6-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="9e7f6-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9e7f6-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="9e7f6-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9e7f6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="9e7f6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e7f6-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e7f6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e7f6-107">Attributes and elements</span></span>

<span data-ttu-id="9e7f6-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e7f6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e7f6-109">Attributes</span></span>

<span data-ttu-id="9e7f6-110">No.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9e7f6-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e7f6-111">Child elements</span></span>
  
|<span data-ttu-id="9e7f6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e7f6-112">Element</span></span>|<span data-ttu-id="9e7f6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e7f6-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="9e7f6-114">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e7f6-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e7f6-115">Parent elements</span></span>  
  
|<span data-ttu-id="9e7f6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e7f6-116">Element</span></span>|<span data-ttu-id="9e7f6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e7f6-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="9e7f6-118">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="9e7f6-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e7f6-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9e7f6-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9e7f6-120">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9e7f6-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9e7f6-121">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9e7f6-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
