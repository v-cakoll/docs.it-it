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
ms.openlocfilehash: ef9c58a9b4ecd6db8b4efe116f6fafba01c3f6f5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="93665-102">&lt;voci&gt;</span><span class="sxs-lookup"><span data-stu-id="93665-102">&lt;entries&gt;</span></span>
<span data-ttu-id="93665-103">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="93665-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="93665-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93665-104">\<system.serviceModel></span></span>  
<span data-ttu-id="93665-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="93665-105">\<routing></span></span>  
<span data-ttu-id="93665-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="93665-106">\<routingTables></span></span>  
<span data-ttu-id="93665-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="93665-107">\<table></span></span>  
<span data-ttu-id="93665-108">\<le voci ></span><span class="sxs-lookup"><span data-stu-id="93665-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93665-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93665-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93665-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93665-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93665-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93665-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93665-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="93665-112">Attributes</span></span>  
 <span data-ttu-id="93665-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="93665-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="93665-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93665-114">Child Elements</span></span>  
  
|<span data-ttu-id="93665-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="93665-115">Element</span></span>|<span data-ttu-id="93665-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93665-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93665-117">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="93665-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="93665-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="93665-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="93665-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="93665-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93665-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93665-120">Parent Elements</span></span>  
  
|<span data-ttu-id="93665-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="93665-121">Element</span></span>|<span data-ttu-id="93665-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93665-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93665-123">\<routing ></span><span class="sxs-lookup"><span data-stu-id="93665-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="93665-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="93665-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93665-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93665-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
