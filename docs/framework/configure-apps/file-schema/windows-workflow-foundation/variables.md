---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3e48256ab1127d45e95c557aa9c2434419d9ea59
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397586"
---
# \<variables>
<span data-ttu-id="0fbbb-101">Rappresenta una raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-101">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="0fbbb-102">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0fbbb-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variables>**  
  
## <a name="syntax"></a><span data-ttu-id="0fbbb-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fbbb-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fbbb-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0fbbb-104">Attributes and Elements</span></span>  
 <span data-ttu-id="0fbbb-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fbbb-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="0fbbb-106">Attributes</span></span>  
 <span data-ttu-id="0fbbb-107">No.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0fbbb-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0fbbb-108">Child Elements</span></span>  
  
|<span data-ttu-id="0fbbb-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="0fbbb-109">Element</span></span>|<span data-ttu-id="0fbbb-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fbbb-110">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="0fbbb-111">Variabile associata a una query sullo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-111">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0fbbb-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0fbbb-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0fbbb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0fbbb-113">Element</span></span>|<span data-ttu-id="0fbbb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fbbb-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="0fbbb-115">Rappresenta un elemento di configurazione utilizzato per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-115">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0fbbb-116">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-116">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fbbb-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="0fbbb-117">Remarks</span></span>  
 <span data-ttu-id="0fbbb-118">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0fbbb-119">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0fbbb-120">È possibile utilizzare gli [\<arguments>](arguments.md) [\<states>](states.md) elementi, e [\<states>](states.md) per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0fbbb-121">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0fbbb-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0fbbb-122">Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno di un profilo di rilevamento utilizzando [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="0fbbb-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fbbb-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0fbbb-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0fbbb-124">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0fbbb-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0fbbb-125">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0fbbb-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
