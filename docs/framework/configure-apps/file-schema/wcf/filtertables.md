---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: d73a3c25dbb4d2de41007149ef5864fcf37ad883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573059"
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="0a306-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="0a306-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="0a306-103">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="0a306-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="0a306-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0a306-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0a306-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="0a306-105">\<routing></span></span>  
<span data-ttu-id="0a306-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="0a306-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a306-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a306-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a306-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0a306-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0a306-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0a306-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a306-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0a306-110">Attributes</span></span>  
 <span data-ttu-id="0a306-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0a306-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a306-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0a306-112">Child Elements</span></span>  
  
|<span data-ttu-id="0a306-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a306-113">Element</span></span>|<span data-ttu-id="0a306-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a306-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a306-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="0a306-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="0a306-116">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="0a306-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a306-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0a306-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0a306-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a306-118">Element</span></span>|<span data-ttu-id="0a306-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a306-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a306-120">\<routing></span><span class="sxs-lookup"><span data-stu-id="0a306-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="0a306-121">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="0a306-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a306-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a306-122">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
