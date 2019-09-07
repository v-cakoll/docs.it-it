---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398737"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="addb9-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="addb9-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="addb9-102">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="addb9-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="addb9-103">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="addb9-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="addb9-104">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="addb9-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="addb9-105">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="addb9-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="addb9-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="addb9-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="addb9-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="addb9-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="addb9-108">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="addb9-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="addb9-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="addb9-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="addb9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="addb9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="addb9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="addb9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="addb9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQueries**</span><span class="sxs-lookup"><span data-stu-id="addb9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="addb9-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="addb9-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="addb9-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="addb9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="addb9-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="addb9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="addb9-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="addb9-116">Attributes</span></span>  
 <span data-ttu-id="addb9-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="addb9-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="addb9-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="addb9-118">Child Elements</span></span>  
  
|<span data-ttu-id="addb9-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="addb9-119">Element</span></span>|<span data-ttu-id="addb9-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="addb9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="addb9-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="addb9-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="addb9-122">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="addb9-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="addb9-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="addb9-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="addb9-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="addb9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="addb9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="addb9-125">Element</span></span>|<span data-ttu-id="addb9-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="addb9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="addb9-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="addb9-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="addb9-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="addb9-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="addb9-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="addb9-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="addb9-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="addb9-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="addb9-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="addb9-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
