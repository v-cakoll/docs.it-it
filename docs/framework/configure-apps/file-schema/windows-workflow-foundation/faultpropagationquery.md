---
title: '&lt;faultPropagationQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 3c8038c133eb7f7a8d47c950037332fa68aa065e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756072"
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="10ed6-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="10ed6-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="10ed6-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10ed6-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="10ed6-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="10ed6-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="10ed6-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10ed6-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="10ed6-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="10ed6-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="10ed6-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="10ed6-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="10ed6-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="10ed6-108">\<system.serviceModel></span></span>  
<span data-ttu-id="10ed6-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="10ed6-109">\<tracking></span></span>  
<span data-ttu-id="10ed6-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="10ed6-110">\<trackingProfile></span></span>  
<span data-ttu-id="10ed6-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="10ed6-111">\<workflow></span></span>  
<span data-ttu-id="10ed6-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="10ed6-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="10ed6-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="10ed6-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ed6-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10ed6-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10ed6-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="10ed6-115">Attributes and Elements</span></span>  
 <span data-ttu-id="10ed6-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="10ed6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10ed6-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="10ed6-117">Attributes</span></span>  
  
|<span data-ttu-id="10ed6-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="10ed6-118">Attribute</span></span>|<span data-ttu-id="10ed6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ed6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10ed6-120">activityName</span><span class="sxs-lookup"><span data-stu-id="10ed6-120">activityName</span></span>|<span data-ttu-id="10ed6-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="10ed6-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="10ed6-122">L'impostazione predefinita è \* che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="10ed6-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="10ed6-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="10ed6-123">faultHandlerActivityName</span></span>|<span data-ttu-id="10ed6-124">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="10ed6-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10ed6-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="10ed6-125">Child Elements</span></span>  
 <span data-ttu-id="10ed6-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="10ed6-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10ed6-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="10ed6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="10ed6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="10ed6-128">Element</span></span>|<span data-ttu-id="10ed6-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ed6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10ed6-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="10ed6-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="10ed6-131">Rappresenta un elenco di elementi di configurazione usati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="10ed6-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="10ed6-132">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="10ed6-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10ed6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ed6-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="10ed6-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="10ed6-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="10ed6-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="10ed6-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
