---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398723"
---
# \<faultPropagationQuery>

<span data-ttu-id="f4c2a-101">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-101">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4c2a-102">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f4c2a-103">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f4c2a-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="f4c2a-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f4c2a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="f4c2a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4c2a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f4c2a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f4c2a-107">Attributes and Elements</span></span>

<span data-ttu-id="f4c2a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4c2a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f4c2a-109">Attributes</span></span>

|<span data-ttu-id="f4c2a-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="f4c2a-110">Attribute</span></span>|<span data-ttu-id="f4c2a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4c2a-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f4c2a-112">activityName</span><span class="sxs-lookup"><span data-stu-id="f4c2a-112">activityName</span></span>|<span data-ttu-id="f4c2a-113">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-113">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="f4c2a-114">L'impostazione predefinita è \* che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-114">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="f4c2a-115">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="f4c2a-115">faultHandlerActivityName</span></span>|<span data-ttu-id="f4c2a-116">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f4c2a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f4c2a-117">Child Elements</span></span>

<span data-ttu-id="f4c2a-118">No.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4c2a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f4c2a-119">Parent Elements</span></span>

|<span data-ttu-id="f4c2a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4c2a-120">Element</span></span>|<span data-ttu-id="f4c2a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4c2a-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="f4c2a-122">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4c2a-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="f4c2a-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f4c2a-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f4c2a-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f4c2a-125">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c2a-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f4c2a-126">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f4c2a-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
