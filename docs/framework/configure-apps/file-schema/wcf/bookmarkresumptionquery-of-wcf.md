---
title: <bookmarkResumptionQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71833999"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="298ca-102">\<bookmarkResumptionQuery>di WCF</span><span class="sxs-lookup"><span data-stu-id="298ca-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="298ca-103">Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="298ca-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="298ca-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="298ca-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="298ca-105">Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="298ca-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="298ca-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="298ca-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="298ca-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="298ca-107">Attributes and elements</span></span>

<span data-ttu-id="298ca-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="298ca-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="298ca-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="298ca-109">Attributes</span></span>  
  
|<span data-ttu-id="298ca-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="298ca-110">Attribute</span></span>|<span data-ttu-id="298ca-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="298ca-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="298ca-112">Stringa che specifica il nome del record di segnalibro da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="298ca-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="298ca-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="298ca-113">Child elements</span></span>

<span data-ttu-id="298ca-114">No.</span><span class="sxs-lookup"><span data-stu-id="298ca-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="298ca-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="298ca-115">Parent elements</span></span>  
  
|<span data-ttu-id="298ca-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="298ca-116">Element</span></span>|<span data-ttu-id="298ca-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="298ca-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="298ca-118">Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="298ca-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="298ca-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="298ca-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="298ca-120">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="298ca-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="298ca-121">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="298ca-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
