---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f790e294b832f43a595d0636c60a8a67da5ad56a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147889"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="23d22-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="23d22-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="23d22-103">Rappresenta una tabella di routing contenente un elenco di filtri per valutare i messaggi da e per indirizzare messaggi agli endpoint client se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="23d22-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="23d22-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="23d22-104">\<system.serviceModel></span></span>  
<span data-ttu-id="23d22-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="23d22-105">\<routing></span></span>  
<span data-ttu-id="23d22-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="23d22-106">\<routingTables></span></span>  
<span data-ttu-id="23d22-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="23d22-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d22-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23d22-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23d22-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="23d22-109">Attributes and Elements</span></span>  
 <span data-ttu-id="23d22-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="23d22-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23d22-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="23d22-111">Attributes</span></span>  
  
|<span data-ttu-id="23d22-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="23d22-112">Element</span></span>|<span data-ttu-id="23d22-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23d22-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23d22-114">name</span><span class="sxs-lookup"><span data-stu-id="23d22-114">name</span></span>|<span data-ttu-id="23d22-115">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23d22-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23d22-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="23d22-116">Child Elements</span></span>  
  
|<span data-ttu-id="23d22-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="23d22-117">Element</span></span>|<span data-ttu-id="23d22-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23d22-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23d22-119">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="23d22-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="23d22-120">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="23d22-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23d22-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="23d22-121">Parent Elements</span></span>  
  
|<span data-ttu-id="23d22-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="23d22-122">Element</span></span>|<span data-ttu-id="23d22-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23d22-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23d22-124">\<routing ></span><span class="sxs-lookup"><span data-stu-id="23d22-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="23d22-125">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="23d22-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23d22-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23d22-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
