---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152131"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="1e4ae-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1e4ae-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="1e4ae-102">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1e4ae-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1e4ae-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1e4ae-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="1e4ae-106">Per ulteriori informazioni sulle query dei profili di rilevamento, vedere [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1e4ae-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1e4ae-107">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e4ae-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e4ae-108">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1e4ae-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1e4ae-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1e4ae-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1e4ae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1e4ae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1e4ae-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1e4ae-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1e4ae-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span><span class="sxs-lookup"><span data-stu-id="1e4ae-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e4ae-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e4ae-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e4ae-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e4ae-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1e4ae-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e4ae-116">Attributes</span><span class="sxs-lookup"><span data-stu-id="1e4ae-116">Attributes</span></span>  
 <span data-ttu-id="1e4ae-117">No.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e4ae-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e4ae-118">Child Elements</span></span>  
  
|<span data-ttu-id="1e4ae-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e4ae-119">Element</span></span>|<span data-ttu-id="1e4ae-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e4ae-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e4ae-121">\<>faultPropagationQuery</span><span class="sxs-lookup"><span data-stu-id="1e4ae-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="1e4ae-122">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1e4ae-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="1e4ae-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e4ae-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e4ae-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1e4ae-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e4ae-125">Element</span></span>|<span data-ttu-id="1e4ae-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e4ae-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e4ae-127">\<>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1e4ae-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1e4ae-128">Elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dalla proprietà **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="1e4ae-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e4ae-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e4ae-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e4ae-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1e4ae-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e4ae-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="1e4ae-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
