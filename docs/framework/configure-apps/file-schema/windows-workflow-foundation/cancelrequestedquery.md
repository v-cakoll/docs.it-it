---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152287"
---
# \<cancelRequestedQuery>
<span data-ttu-id="61db3-101">Rappresenta una query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="61db3-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="61db3-102">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="61db3-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="61db3-103">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="61db3-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="61db3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61db3-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61db3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61db3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="61db3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61db3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61db3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="61db3-107">Attributes</span></span>  
  
|<span data-ttu-id="61db3-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="61db3-108">Attribute</span></span>|<span data-ttu-id="61db3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61db3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61db3-110">activityName</span><span class="sxs-lookup"><span data-stu-id="61db3-110">activityName</span></span>|<span data-ttu-id="61db3-111">Stringa che specifica il nome dell'attività che richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="61db3-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="61db3-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="61db3-112">childActivityName</span></span>|<span data-ttu-id="61db3-113">Stringa che specifica il nome dell'attività figlio per la quale è stato richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="61db3-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61db3-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61db3-114">Child Elements</span></span>  
 <span data-ttu-id="61db3-115">No.</span><span class="sxs-lookup"><span data-stu-id="61db3-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61db3-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61db3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="61db3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="61db3-117">Element</span></span>|<span data-ttu-id="61db3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61db3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="61db3-119">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="61db3-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="61db3-120">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="61db3-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61db3-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="61db3-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="61db3-122">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="61db3-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="61db3-123">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="61db3-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
