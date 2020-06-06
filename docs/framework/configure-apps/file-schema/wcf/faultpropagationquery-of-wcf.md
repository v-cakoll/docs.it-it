---
title: <faultPropagationQuery>di WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855338"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="8cd50-102">\<faultPropagationQuery>di WCF</span><span class="sxs-lookup"><span data-stu-id="8cd50-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="8cd50-103">Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8cd50-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8cd50-104">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="8cd50-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="8cd50-105">È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8cd50-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="8cd50-106">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="8cd50-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="8cd50-107">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8cd50-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="8cd50-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cd50-108">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cd50-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8cd50-109">Attributes and elements</span></span>

<span data-ttu-id="8cd50-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8cd50-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8cd50-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8cd50-111">Attributes</span></span>

|<span data-ttu-id="8cd50-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8cd50-112">Attribute</span></span>|<span data-ttu-id="8cd50-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cd50-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="8cd50-114">Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore.</span><span class="sxs-lookup"><span data-stu-id="8cd50-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="8cd50-115">Il valore predefinito è \* , che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="8cd50-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="8cd50-116">Stringa che specifica il nome dell'attività che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="8cd50-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8cd50-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8cd50-117">Child elements</span></span>

<span data-ttu-id="8cd50-118">No.</span><span class="sxs-lookup"><span data-stu-id="8cd50-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8cd50-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8cd50-119">Parent elements</span></span>

|<span data-ttu-id="8cd50-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8cd50-120">Element</span></span>|<span data-ttu-id="8cd50-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cd50-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="8cd50-122">Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8cd50-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8cd50-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="8cd50-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8cd50-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8cd50-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8cd50-125">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8cd50-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8cd50-126">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8cd50-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
