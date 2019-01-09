---
title: '&lt;Voci&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 8c442990ee736c17b71b625e06d961230a8ceed2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146433"
---
# <a name="ltentriesgt"></a><span data-ttu-id="f04aa-102">&lt;Voci&gt;</span><span class="sxs-lookup"><span data-stu-id="f04aa-102">&lt;entries&gt;</span></span>
<span data-ttu-id="f04aa-103">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="f04aa-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="f04aa-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f04aa-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f04aa-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="f04aa-105">\<routing></span></span>  
<span data-ttu-id="f04aa-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="f04aa-106">\<routingTables></span></span>  
<span data-ttu-id="f04aa-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="f04aa-107">\<table></span></span>  
<span data-ttu-id="f04aa-108">\<le voci ></span><span class="sxs-lookup"><span data-stu-id="f04aa-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04aa-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f04aa-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f04aa-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f04aa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f04aa-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f04aa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f04aa-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f04aa-112">Attributes</span></span>  
 <span data-ttu-id="f04aa-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f04aa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f04aa-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f04aa-114">Child Elements</span></span>  
  
|<span data-ttu-id="f04aa-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f04aa-115">Element</span></span>|<span data-ttu-id="f04aa-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f04aa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f04aa-117">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="f04aa-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="f04aa-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f04aa-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="f04aa-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="f04aa-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f04aa-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f04aa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f04aa-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f04aa-121">Element</span></span>|<span data-ttu-id="f04aa-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f04aa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f04aa-123">\<routing ></span><span class="sxs-lookup"><span data-stu-id="f04aa-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="f04aa-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="f04aa-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f04aa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04aa-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
