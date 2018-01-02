---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8cf87cc74c7bb5d495584407c803dacc7b94f195
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="c02ef-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="c02ef-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="c02ef-103">Rappresenta una tabella di routing contenente un elenco di filtri per valutare i messaggi di base e per indirizzare messaggi agli endpoint client se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="c02ef-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="c02ef-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c02ef-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c02ef-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="c02ef-105">\<routing></span></span>  
<span data-ttu-id="c02ef-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="c02ef-106">\<routingTables></span></span>  
<span data-ttu-id="c02ef-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="c02ef-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02ef-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c02ef-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c02ef-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c02ef-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c02ef-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c02ef-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c02ef-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c02ef-111">Attributes</span></span>  
  
|<span data-ttu-id="c02ef-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c02ef-112">Element</span></span>|<span data-ttu-id="c02ef-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c02ef-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c02ef-114">name</span><span class="sxs-lookup"><span data-stu-id="c02ef-114">name</span></span>|<span data-ttu-id="c02ef-115">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c02ef-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c02ef-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c02ef-116">Child Elements</span></span>  
  
|<span data-ttu-id="c02ef-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c02ef-117">Element</span></span>|<span data-ttu-id="c02ef-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c02ef-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c02ef-119">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="c02ef-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="c02ef-120">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="c02ef-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c02ef-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c02ef-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c02ef-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c02ef-122">Element</span></span>|<span data-ttu-id="c02ef-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c02ef-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c02ef-124">\<routing ></span><span class="sxs-lookup"><span data-stu-id="c02ef-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="c02ef-125">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="c02ef-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c02ef-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c02ef-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
