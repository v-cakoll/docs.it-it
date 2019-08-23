---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925659"
---
# <a name="entries"></a><span data-ttu-id="bd42d-101">\<voci ></span><span class="sxs-lookup"><span data-stu-id="bd42d-101">\<entries></span></span>
<span data-ttu-id="bd42d-102">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="bd42d-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="bd42d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bd42d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="bd42d-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="bd42d-104">\<routing></span></span>  
<span data-ttu-id="bd42d-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="bd42d-105">\<routingTables></span></span>  
<span data-ttu-id="bd42d-106">\<> tabella</span><span class="sxs-lookup"><span data-stu-id="bd42d-106">\<table></span></span>  
<span data-ttu-id="bd42d-107">\<voci ></span><span class="sxs-lookup"><span data-stu-id="bd42d-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd42d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd42d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd42d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bd42d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bd42d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bd42d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd42d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="bd42d-111">Attributes</span></span>  
 <span data-ttu-id="bd42d-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bd42d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd42d-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bd42d-113">Child Elements</span></span>  
  
|<span data-ttu-id="bd42d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd42d-114">Element</span></span>|<span data-ttu-id="bd42d-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="bd42d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd42d-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="bd42d-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="bd42d-117">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bd42d-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="bd42d-118">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="bd42d-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd42d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bd42d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bd42d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd42d-120">Element</span></span>|<span data-ttu-id="bd42d-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="bd42d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd42d-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="bd42d-122">\<routing></span></span>](routing.md)|<span data-ttu-id="bd42d-123">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="bd42d-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd42d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd42d-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
