---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925596"
---
# <a name="filtertable"></a><span data-ttu-id="d24b2-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="d24b2-101">\<filterTable></span></span>
<span data-ttu-id="d24b2-102">Rappresenta una tabella di routing contenente un elenco di filtri in base ai quali valutare i messaggi e l'endpoint client a cui indirizzare i messaggi se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="d24b2-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="d24b2-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d24b2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d24b2-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="d24b2-104">\<routing></span></span>  
<span data-ttu-id="d24b2-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="d24b2-105">\<routingTables></span></span>  
<span data-ttu-id="d24b2-106">\<> tabella</span><span class="sxs-lookup"><span data-stu-id="d24b2-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d24b2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d24b2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d24b2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d24b2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d24b2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d24b2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d24b2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d24b2-110">Attributes</span></span>  
  
|<span data-ttu-id="d24b2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="d24b2-111">Element</span></span>|<span data-ttu-id="d24b2-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d24b2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d24b2-113">name</span><span class="sxs-lookup"><span data-stu-id="d24b2-113">name</span></span>|<span data-ttu-id="d24b2-114">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d24b2-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d24b2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d24b2-115">Child Elements</span></span>  
  
|<span data-ttu-id="d24b2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d24b2-116">Element</span></span>|<span data-ttu-id="d24b2-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d24b2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d24b2-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="d24b2-118">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="d24b2-119">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="d24b2-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d24b2-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d24b2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d24b2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d24b2-121">Element</span></span>|<span data-ttu-id="d24b2-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d24b2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d24b2-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="d24b2-123">\<routing></span></span>](routing.md)|<span data-ttu-id="d24b2-124">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="d24b2-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d24b2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d24b2-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
