---
title: '&lt;faultPropagationQuery&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 330413b676025020924dc15f54170c4dc19e616a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="6293c-102">&lt;faultPropagationQuery&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="6293c-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="6293c-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="6293c-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6293c-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="6293c-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="6293c-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="6293c-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="6293c-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="6293c-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="6293c-107">Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6293c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="6293c-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6293c-108">\<system.serviceModel></span></span>  
<span data-ttu-id="6293c-109">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="6293c-109">\<tracking></span></span>  
<span data-ttu-id="6293c-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6293c-110">\<trackingProfile></span></span>  
<span data-ttu-id="6293c-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="6293c-111">\<workflow></span></span>  
<span data-ttu-id="6293c-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="6293c-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="6293c-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="6293c-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6293c-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6293c-114">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6293c-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6293c-115">Attributes and Elements</span></span>  
 <span data-ttu-id="6293c-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6293c-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6293c-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="6293c-117">Attributes</span></span>  
  
|<span data-ttu-id="6293c-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="6293c-118">Attribute</span></span>|<span data-ttu-id="6293c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6293c-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6293c-120">activityName</span><span class="sxs-lookup"><span data-stu-id="6293c-120">activityName</span></span>|<span data-ttu-id="6293c-121">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6293c-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="6293c-122">L'impostazione predefinita è * che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="6293c-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="6293c-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="6293c-123">faultHandlerActivityName</span></span>|<span data-ttu-id="6293c-124">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6293c-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6293c-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6293c-125">Child Elements</span></span>  
 <span data-ttu-id="6293c-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6293c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6293c-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6293c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6293c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="6293c-128">Element</span></span>|<span data-ttu-id="6293c-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6293c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6293c-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="6293c-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="6293c-131">Rappresenta un elenco di elementi di configurazione usati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="6293c-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6293c-132">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="6293c-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6293c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6293c-133">See Also</span></span>  
 <span data-ttu-id="6293c-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6293c-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="6293c-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6293c-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="6293c-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6293c-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6293c-137">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6293c-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
