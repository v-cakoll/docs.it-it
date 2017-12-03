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
ms.openlocfilehash: 96425604fab8f70456ea1e0d97efb2c3bf843224
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="8440c-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="8440c-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="8440c-103">Rappresenta una tabella di routing contenente un elenco di filtri per valutare i messaggi di base e per indirizzare messaggi agli endpoint client se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="8440c-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="8440c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8440c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8440c-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="8440c-105">\<routing></span></span>  
<span data-ttu-id="8440c-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="8440c-106">\<routingTables></span></span>  
<span data-ttu-id="8440c-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="8440c-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8440c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8440c-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8440c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8440c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8440c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8440c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8440c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8440c-111">Attributes</span></span>  
  
|<span data-ttu-id="8440c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8440c-112">Element</span></span>|<span data-ttu-id="8440c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8440c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8440c-114">name</span><span class="sxs-lookup"><span data-stu-id="8440c-114">name</span></span>|<span data-ttu-id="8440c-115">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8440c-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8440c-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8440c-116">Child Elements</span></span>  
  
|<span data-ttu-id="8440c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8440c-117">Element</span></span>|<span data-ttu-id="8440c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8440c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8440c-119">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="8440c-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="8440c-120">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="8440c-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8440c-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8440c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8440c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8440c-122">Element</span></span>|<span data-ttu-id="8440c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8440c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8440c-124">\<routing ></span><span class="sxs-lookup"><span data-stu-id="8440c-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8440c-125">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="8440c-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8440c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8440c-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
