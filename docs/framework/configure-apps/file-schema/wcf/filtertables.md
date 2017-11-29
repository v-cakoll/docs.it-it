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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75e06b0258f2e4f65d441c25b5081cf7a6627518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="89988-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="89988-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="89988-103">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="89988-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="89988-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="89988-104">\<system.serviceModel></span></span>  
<span data-ttu-id="89988-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="89988-105">\<routing></span></span>  
<span data-ttu-id="89988-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="89988-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89988-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89988-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89988-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89988-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89988-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89988-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89988-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="89988-110">Attributes</span></span>  
 <span data-ttu-id="89988-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="89988-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89988-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89988-112">Child Elements</span></span>  
  
|<span data-ttu-id="89988-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="89988-113">Element</span></span>|<span data-ttu-id="89988-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89988-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89988-115">\<i filtri ></span><span class="sxs-lookup"><span data-stu-id="89988-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="89988-116">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="89988-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89988-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89988-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89988-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="89988-118">Element</span></span>|<span data-ttu-id="89988-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89988-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89988-120">\<routing ></span><span class="sxs-lookup"><span data-stu-id="89988-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="89988-121">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="89988-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89988-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89988-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
