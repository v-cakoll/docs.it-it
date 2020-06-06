---
title: <workflowInstanceQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854734"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="b93cc-102">\<workflowInstanceQuery>di WCF</span><span class="sxs-lookup"><span data-stu-id="b93cc-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="b93cc-103">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="b93cc-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="b93cc-104">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b93cc-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="b93cc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b93cc-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b93cc-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b93cc-106">Attributes and elements</span></span>  

<span data-ttu-id="b93cc-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b93cc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b93cc-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b93cc-108">Attributes</span></span>  

<span data-ttu-id="b93cc-109">No.</span><span class="sxs-lookup"><span data-stu-id="b93cc-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b93cc-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b93cc-110">Child elements</span></span>  
  
|<span data-ttu-id="b93cc-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b93cc-111">Element</span></span>|<span data-ttu-id="b93cc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93cc-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="b93cc-113">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b93cc-113">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b93cc-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b93cc-114">Parent elements</span></span>  
  
|<span data-ttu-id="b93cc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b93cc-115">Element</span></span>|<span data-ttu-id="b93cc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93cc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQueries>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="b93cc-117">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="b93cc-117">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b93cc-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="b93cc-118">Remarks</span></span>  

<span data-ttu-id="b93cc-119">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93cc-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b93cc-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b93cc-120">Example</span></span>  

<span data-ttu-id="b93cc-121">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="b93cc-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="b93cc-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b93cc-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b93cc-123">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b93cc-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b93cc-124">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b93cc-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
