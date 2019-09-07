---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398950"
---
# <a name="activitystatequeries"></a><span data-ttu-id="8387f-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="8387f-101">\<activityStateQueries></span></span>
<span data-ttu-id="8387f-102">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8387f-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8387f-103">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8387f-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8387f-104">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="8387f-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8387f-105">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="8387f-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="8387f-106">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8387f-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8387f-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8387f-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8387f-108">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8387f-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8387f-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="8387f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="8387f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="8387f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="8387f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8387f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="8387f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQueries**</span><span class="sxs-lookup"><span data-stu-id="8387f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8387f-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8387f-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8387f-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8387f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="8387f-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8387f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8387f-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="8387f-116">Attributes</span></span>  
 <span data-ttu-id="8387f-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8387f-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8387f-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8387f-118">Child Elements</span></span>  
  
|<span data-ttu-id="8387f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8387f-119">Element</span></span>|<span data-ttu-id="8387f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8387f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8387f-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="8387f-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="8387f-122">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8387f-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8387f-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="8387f-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8387f-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8387f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8387f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8387f-125">Element</span></span>|<span data-ttu-id="8387f-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8387f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8387f-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8387f-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="8387f-128">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="8387f-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8387f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8387f-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8387f-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8387f-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8387f-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8387f-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
