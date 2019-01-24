---
title: '&lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 33f98cb4b138307622a14463ce5a3008058b6e31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587060"
---
# <a name="ltentriesgt"></a><span data-ttu-id="2d606-102">&lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="2d606-102">&lt;entries&gt;</span></span>
<span data-ttu-id="2d606-103">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="2d606-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="2d606-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d606-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2d606-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="2d606-105">\<routing></span></span>  
<span data-ttu-id="2d606-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="2d606-106">\<routingTables></span></span>  
<span data-ttu-id="2d606-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="2d606-107">\<table></span></span>  
<span data-ttu-id="2d606-108">\<entries></span><span class="sxs-lookup"><span data-stu-id="2d606-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d606-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d606-109">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d606-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2d606-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d606-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2d606-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d606-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2d606-112">Attributes</span></span>  
 <span data-ttu-id="2d606-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2d606-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d606-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2d606-114">Child Elements</span></span>  
  
|<span data-ttu-id="2d606-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d606-115">Element</span></span>|<span data-ttu-id="2d606-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d606-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d606-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="2d606-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="2d606-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d606-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="2d606-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="2d606-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d606-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2d606-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2d606-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d606-121">Element</span></span>|<span data-ttu-id="2d606-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d606-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d606-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="2d606-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="2d606-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="2d606-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d606-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d606-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
