---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 83339eebef9a4f1b7f69e0bd1dd16b8278a68258
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534605"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="ea26e-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="ea26e-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="ea26e-103">Rappresenta una tabella di routing contenente un elenco di filtri per valutare i messaggi da e per indirizzare messaggi agli endpoint client se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="ea26e-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="ea26e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ea26e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ea26e-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="ea26e-105">\<routing></span></span>  
<span data-ttu-id="ea26e-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="ea26e-106">\<routingTables></span></span>  
<span data-ttu-id="ea26e-107">\<tabella ></span><span class="sxs-lookup"><span data-stu-id="ea26e-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea26e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea26e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea26e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea26e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea26e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea26e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea26e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea26e-111">Attributes</span></span>  
  
|<span data-ttu-id="ea26e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea26e-112">Element</span></span>|<span data-ttu-id="ea26e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea26e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea26e-114">name</span><span class="sxs-lookup"><span data-stu-id="ea26e-114">name</span></span>|<span data-ttu-id="ea26e-115">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ea26e-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea26e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea26e-116">Child Elements</span></span>  
  
|<span data-ttu-id="ea26e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea26e-117">Element</span></span>|<span data-ttu-id="ea26e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea26e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea26e-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="ea26e-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="ea26e-120">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="ea26e-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea26e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea26e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ea26e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea26e-122">Element</span></span>|<span data-ttu-id="ea26e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea26e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea26e-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="ea26e-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ea26e-125">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="ea26e-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea26e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea26e-126">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
