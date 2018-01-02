---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05c8d3f5ce5a01e5a88f37fce43f3b4f8d260812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="ae043-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="ae043-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="ae043-103">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="ae043-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="ae043-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ae043-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ae043-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="ae043-105">\<routing></span></span>  
<span data-ttu-id="ae043-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="ae043-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae043-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae043-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae043-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae043-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae043-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae043-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae043-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae043-110">Attributes</span></span>  
 <span data-ttu-id="ae043-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae043-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae043-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae043-112">Child Elements</span></span>  
  
|<span data-ttu-id="ae043-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae043-113">Element</span></span>|<span data-ttu-id="ae043-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae043-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae043-115">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="ae043-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="ae043-116">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="ae043-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae043-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae043-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ae043-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae043-118">Element</span></span>|<span data-ttu-id="ae043-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae043-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae043-120">\<routing ></span><span class="sxs-lookup"><span data-stu-id="ae043-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ae043-121">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="ae043-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae043-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae043-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
