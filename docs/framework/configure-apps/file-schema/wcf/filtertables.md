---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075730"
---
# <a name="filtertables"></a><span data-ttu-id="8c76c-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="8c76c-101">\<filterTables></span></span>
<span data-ttu-id="8c76c-102">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="8c76c-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="8c76c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c76c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8c76c-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="8c76c-104">\<routing></span></span>  
<span data-ttu-id="8c76c-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="8c76c-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c76c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c76c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c76c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c76c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8c76c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c76c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c76c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c76c-109">Attributes</span></span>  
 <span data-ttu-id="8c76c-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8c76c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c76c-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c76c-111">Child Elements</span></span>  
  
|<span data-ttu-id="8c76c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c76c-112">Element</span></span>|<span data-ttu-id="8c76c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c76c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c76c-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="8c76c-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="8c76c-115">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="8c76c-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c76c-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c76c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8c76c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c76c-117">Element</span></span>|<span data-ttu-id="8c76c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c76c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c76c-119">\<routing></span><span class="sxs-lookup"><span data-stu-id="8c76c-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8c76c-120">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="8c76c-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c76c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c76c-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
