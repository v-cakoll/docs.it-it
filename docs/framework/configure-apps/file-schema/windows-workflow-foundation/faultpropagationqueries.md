---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152131"
---
# \<faultPropagationQueries>
<span data-ttu-id="44cf5-101">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="44cf5-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="44cf5-102">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="44cf5-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="44cf5-103">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="44cf5-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="44cf5-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="44cf5-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="44cf5-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="44cf5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="44cf5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44cf5-106">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44cf5-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44cf5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="44cf5-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44cf5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44cf5-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="44cf5-109">Attributes</span></span>  
 <span data-ttu-id="44cf5-110">No.</span><span class="sxs-lookup"><span data-stu-id="44cf5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44cf5-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44cf5-111">Child Elements</span></span>  
  
|<span data-ttu-id="44cf5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="44cf5-112">Element</span></span>|<span data-ttu-id="44cf5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44cf5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="44cf5-114">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="44cf5-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="44cf5-115">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="44cf5-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44cf5-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44cf5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="44cf5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="44cf5-117">Element</span></span>|<span data-ttu-id="44cf5-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44cf5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="44cf5-119">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="44cf5-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44cf5-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="44cf5-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="44cf5-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="44cf5-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="44cf5-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="44cf5-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
