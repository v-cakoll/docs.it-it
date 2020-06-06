---
title: <faultPropagationQueries>di WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855273"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="4c555-102">\<faultPropagationQueries>di WCF</span><span class="sxs-lookup"><span data-stu-id="4c555-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="4c555-103">Rappresenta una raccolta di query usate per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4c555-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4c555-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="4c555-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="4c555-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4c555-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4c555-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="4c555-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="4c555-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4c555-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="4c555-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c555-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c555-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4c555-109">Attributes and elements</span></span>

<span data-ttu-id="4c555-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4c555-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4c555-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c555-111">Attributes</span></span>

<span data-ttu-id="4c555-112">No.</span><span class="sxs-lookup"><span data-stu-id="4c555-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4c555-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c555-113">Child elements</span></span>

|<span data-ttu-id="4c555-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c555-114">Element</span></span>|<span data-ttu-id="4c555-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c555-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="4c555-116">Query utilizzata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="4c555-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4c555-117">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="4c555-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c555-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4c555-118">Parent elements</span></span>  
  
|<span data-ttu-id="4c555-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c555-119">Element</span></span>|<span data-ttu-id="4c555-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c555-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="4c555-121">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="4c555-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c555-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4c555-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4c555-123">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4c555-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4c555-124">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4c555-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
