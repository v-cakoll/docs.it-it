---
title: '&lt;Voci&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746709"
---
# <a name="ltentriesgt"></a><span data-ttu-id="d4f0b-102">&lt;Voci&gt;</span><span class="sxs-lookup"><span data-stu-id="d4f0b-102">&lt;entries&gt;</span></span>
<span data-ttu-id="d4f0b-103">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="d4f0b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4f0b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d4f0b-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-105">\<routing></span></span>  
<span data-ttu-id="d4f0b-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-106">\<routingTables></span></span>  
<span data-ttu-id="d4f0b-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-107">\<table></span></span>  
<span data-ttu-id="d4f0b-108">\<le voci ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f0b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4f0b-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4f0b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d4f0b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d4f0b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4f0b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d4f0b-112">Attributes</span></span>  
 <span data-ttu-id="d4f0b-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4f0b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d4f0b-114">Child Elements</span></span>  
  
|<span data-ttu-id="d4f0b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4f0b-115">Element</span></span>|<span data-ttu-id="d4f0b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4f0b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4f0b-117">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="d4f0b-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="d4f0b-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4f0b-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d4f0b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d4f0b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4f0b-121">Element</span></span>|<span data-ttu-id="d4f0b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4f0b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4f0b-123">\<routing ></span><span class="sxs-lookup"><span data-stu-id="d4f0b-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="d4f0b-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="d4f0b-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4f0b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4f0b-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
