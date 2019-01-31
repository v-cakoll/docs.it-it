---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 9c4c7fa4f778642d549deebce6e7476f4da13a0d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283686"
---
# <a name="entries"></a><span data-ttu-id="6fb67-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="6fb67-101">\<entries></span></span>
<span data-ttu-id="6fb67-102">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="6fb67-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="6fb67-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6fb67-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6fb67-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="6fb67-104">\<routing></span></span>  
<span data-ttu-id="6fb67-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="6fb67-105">\<routingTables></span></span>  
<span data-ttu-id="6fb67-106">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="6fb67-106">\<table></span></span>  
<span data-ttu-id="6fb67-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="6fb67-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb67-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fb67-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fb67-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6fb67-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6fb67-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6fb67-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fb67-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6fb67-111">Attributes</span></span>  
 <span data-ttu-id="6fb67-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6fb67-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6fb67-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6fb67-113">Child Elements</span></span>  
  
|<span data-ttu-id="6fb67-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6fb67-114">Element</span></span>|<span data-ttu-id="6fb67-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fb67-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fb67-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="6fb67-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="6fb67-117">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6fb67-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="6fb67-118">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="6fb67-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6fb67-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6fb67-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6fb67-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6fb67-120">Element</span></span>|<span data-ttu-id="6fb67-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fb67-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fb67-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="6fb67-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6fb67-123">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="6fb67-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fb67-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fb67-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
