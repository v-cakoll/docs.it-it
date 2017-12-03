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
ms.openlocfilehash: 028681acffcd93633807bdb1c6fa78aab98011c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="74991-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="74991-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="74991-103">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="74991-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="74991-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="74991-104">\<system.serviceModel></span></span>  
<span data-ttu-id="74991-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="74991-105">\<routing></span></span>  
<span data-ttu-id="74991-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="74991-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74991-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74991-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74991-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="74991-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74991-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="74991-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74991-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="74991-110">Attributes</span></span>  
 <span data-ttu-id="74991-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="74991-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74991-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74991-112">Child Elements</span></span>  
  
|<span data-ttu-id="74991-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="74991-113">Element</span></span>|<span data-ttu-id="74991-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74991-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74991-115">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="74991-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="74991-116">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="74991-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74991-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="74991-117">Parent Elements</span></span>  
  
|<span data-ttu-id="74991-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="74991-118">Element</span></span>|<span data-ttu-id="74991-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74991-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74991-120">\<routing ></span><span class="sxs-lookup"><span data-stu-id="74991-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="74991-121">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="74991-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74991-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74991-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
