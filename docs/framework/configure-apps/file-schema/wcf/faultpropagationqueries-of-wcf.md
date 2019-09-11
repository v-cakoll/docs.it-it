---
title: <faultPropagationQueries>di WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855273"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="47e6e-102">\<> faultPropagationQueries di WCF</span><span class="sxs-lookup"><span data-stu-id="47e6e-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="47e6e-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="47e6e-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="47e6e-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="47e6e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="47e6e-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="47e6e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="47e6e-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="47e6e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="47e6e-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="47e6e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="47e6e-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47e6e-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47e6e-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="47e6e-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="47e6e-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="47e6e-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="47e6e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** </span><span class="sxs-lookup"><span data-stu-id="47e6e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="47e6e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="47e6e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="47e6e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="47e6e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="47e6e-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQueries**</span><span class="sxs-lookup"><span data-stu-id="47e6e-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47e6e-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47e6e-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47e6e-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47e6e-116">Attributes and elements</span></span>

<span data-ttu-id="47e6e-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47e6e-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="47e6e-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="47e6e-118">Attributes</span></span>

<span data-ttu-id="47e6e-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="47e6e-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="47e6e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47e6e-120">Child elements</span></span>

|<span data-ttu-id="47e6e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="47e6e-121">Element</span></span>|<span data-ttu-id="47e6e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47e6e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47e6e-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="47e6e-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="47e6e-124">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="47e6e-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="47e6e-125">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="47e6e-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47e6e-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47e6e-126">Parent elements</span></span>  
  
|<span data-ttu-id="47e6e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="47e6e-127">Element</span></span>|<span data-ttu-id="47e6e-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47e6e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47e6e-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="47e6e-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="47e6e-130">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="47e6e-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47e6e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47e6e-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="47e6e-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="47e6e-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="47e6e-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="47e6e-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
