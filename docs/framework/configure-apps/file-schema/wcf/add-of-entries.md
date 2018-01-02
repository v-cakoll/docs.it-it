---
title: '&lt;add&gt; di &lt;entries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1583ec3cab3ed43556dc066c1e4753ddf9845ef5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="dbed0-102">&lt;add&gt; di &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="dbed0-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="dbed0-103">Rappresenta una voce di routing che esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dbed0-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="dbed0-104">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbed0-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="dbed0-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dbed0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dbed0-106">\<routing ></span><span class="sxs-lookup"><span data-stu-id="dbed0-106">\<routing></span></span>  
<span data-ttu-id="dbed0-107">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="dbed0-107">\<routingTables></span></span>  
<span data-ttu-id="dbed0-108">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="dbed0-108">\<table></span></span>  
<span data-ttu-id="dbed0-109">\<le voci ></span><span class="sxs-lookup"><span data-stu-id="dbed0-109">\<entries></span></span>  
<span data-ttu-id="dbed0-110">\<add></span><span class="sxs-lookup"><span data-stu-id="dbed0-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbed0-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbed0-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbed0-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbed0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dbed0-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbed0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbed0-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbed0-114">Attributes</span></span>  
  
|<span data-ttu-id="dbed0-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="dbed0-115">Attribute</span></span>|<span data-ttu-id="dbed0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbed0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbed0-117">backupList</span><span class="sxs-lookup"><span data-stu-id="dbed0-117">backupList</span></span>|<span data-ttu-id="dbed0-118">Stringa che specifica un riferimento a un elenco di backup di endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbed0-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="dbed0-119">endpoint</span><span class="sxs-lookup"><span data-stu-id="dbed0-119">endpoint</span></span>|<span data-ttu-id="dbed0-120">Stringa che specifica un riferimento a un endpoint client che riceverà i messaggi corrispondenti al filtro specificato dall'attributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="dbed0-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="dbed0-121">filterName</span><span class="sxs-lookup"><span data-stu-id="dbed0-121">filterName</span></span>|<span data-ttu-id="dbed0-122">Stringa che specifica un riferimento a un elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="dbed0-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="dbed0-123">priority</span><span class="sxs-lookup"><span data-stu-id="dbed0-123">priority</span></span>|<span data-ttu-id="dbed0-124">Integer che specifica la priorità di questa voce.</span><span class="sxs-lookup"><span data-stu-id="dbed0-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="dbed0-125">Le voci nella tabella di routing verranno valutate in base alla priorità, con 0 come priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="dbed0-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="dbed0-126">Tutte le voci per una priorità specifica vengono valutate simultaneamente. Se non viene trovata alcuna voce corrispondente per la priorità corrente, verrà valutato il livello di priorità successivo.</span><span class="sxs-lookup"><span data-stu-id="dbed0-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="dbed0-127">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dbed0-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbed0-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbed0-128">Child Elements</span></span>  
 <span data-ttu-id="dbed0-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dbed0-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbed0-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbed0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="dbed0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbed0-131">Element</span></span>|<span data-ttu-id="dbed0-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbed0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbed0-133">\<routing ></span><span class="sxs-lookup"><span data-stu-id="dbed0-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="dbed0-134">Sezione di configurazione contenente voci di mapping di routing.</span><span class="sxs-lookup"><span data-stu-id="dbed0-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbed0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbed0-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
