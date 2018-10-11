---
title: '&lt;faultPropagationQuery&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: df7119363e94a070bb898c984c12cf82755c3407
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087700"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="880e1-102">&lt;faultPropagationQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="880e1-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="880e1-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="880e1-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="880e1-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="880e1-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="880e1-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="880e1-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="880e1-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="880e1-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="880e1-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="880e1-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="880e1-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="880e1-108">\<system.serviceModel></span></span>  
<span data-ttu-id="880e1-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="880e1-109">\<tracking></span></span>  
<span data-ttu-id="880e1-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="880e1-110">\<trackingProfile></span></span>  
<span data-ttu-id="880e1-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="880e1-111">\<workflow></span></span>  
<span data-ttu-id="880e1-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="880e1-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="880e1-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="880e1-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="880e1-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="880e1-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String"/>
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="880e1-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="880e1-115">Attributes and Elements</span></span>  
 <span data-ttu-id="880e1-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="880e1-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="880e1-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="880e1-117">Attributes</span></span>  
  
|<span data-ttu-id="880e1-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="880e1-118">Attribute</span></span>|<span data-ttu-id="880e1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="880e1-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="880e1-120">activityName</span><span class="sxs-lookup"><span data-stu-id="880e1-120">activityName</span></span>|<span data-ttu-id="880e1-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="880e1-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="880e1-122">L'impostazione predefinita è \* che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="880e1-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="880e1-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="880e1-123">faultHandlerActivityName</span></span>|<span data-ttu-id="880e1-124">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="880e1-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="880e1-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="880e1-125">Child Elements</span></span>  
 <span data-ttu-id="880e1-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="880e1-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="880e1-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="880e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="880e1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="880e1-128">Element</span></span>|<span data-ttu-id="880e1-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="880e1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="880e1-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="880e1-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="880e1-131">Rappresenta un elenco di elementi di configurazione usati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="880e1-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="880e1-132">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="880e1-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="880e1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="880e1-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="880e1-134">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="880e1-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="880e1-135">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="880e1-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
