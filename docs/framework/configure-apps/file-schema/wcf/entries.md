---
title: '&lt;voci&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1bd6fd679d3f6440ff685c8cd2646b1fa0a13e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="3916b-102">&lt;voci&gt;</span><span class="sxs-lookup"><span data-stu-id="3916b-102">&lt;entries&gt;</span></span>
<span data-ttu-id="3916b-103">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="3916b-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="3916b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3916b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3916b-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="3916b-105">\<routing></span></span>  
<span data-ttu-id="3916b-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="3916b-106">\<routingTables></span></span>  
<span data-ttu-id="3916b-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="3916b-107">\<table></span></span>  
<span data-ttu-id="3916b-108">\<le voci ></span><span class="sxs-lookup"><span data-stu-id="3916b-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3916b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3916b-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3916b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3916b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3916b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3916b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3916b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3916b-112">Attributes</span></span>  
 <span data-ttu-id="3916b-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3916b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3916b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3916b-114">Child Elements</span></span>  
  
|<span data-ttu-id="3916b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3916b-115">Element</span></span>|<span data-ttu-id="3916b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3916b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3916b-117">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="3916b-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="3916b-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3916b-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="3916b-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="3916b-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3916b-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3916b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3916b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3916b-121">Element</span></span>|<span data-ttu-id="3916b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3916b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3916b-123">\<routing ></span><span class="sxs-lookup"><span data-stu-id="3916b-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="3916b-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="3916b-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3916b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3916b-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
