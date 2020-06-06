---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398950"
---
# \<activityStateQueries>
<span data-ttu-id="3ef29-101">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ef29-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3ef29-102">È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ef29-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3ef29-103">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="3ef29-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3ef29-104">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="3ef29-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3ef29-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3ef29-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="3ef29-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ef29-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ef29-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ef29-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3ef29-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ef29-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ef29-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ef29-109">Attributes</span></span>  
 <span data-ttu-id="3ef29-110">No.</span><span class="sxs-lookup"><span data-stu-id="3ef29-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ef29-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ef29-111">Child Elements</span></span>  
  
|<span data-ttu-id="3ef29-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ef29-112">Element</span></span>|<span data-ttu-id="3ef29-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ef29-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="3ef29-114">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="3ef29-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3ef29-115">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="3ef29-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ef29-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ef29-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3ef29-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ef29-117">Element</span></span>|<span data-ttu-id="3ef29-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ef29-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="3ef29-119">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="3ef29-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ef29-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3ef29-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3ef29-121">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3ef29-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3ef29-122">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="3ef29-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
