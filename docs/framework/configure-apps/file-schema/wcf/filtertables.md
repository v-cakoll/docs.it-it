---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: a54386de369a11a1958e4d81ab01f053a0bc5b36
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55253977"
---
# <a name="filtertables"></a><span data-ttu-id="5c4f9-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="5c4f9-101">\<filterTables></span></span>
<span data-ttu-id="5c4f9-102">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="5c4f9-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="5c4f9-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5c4f9-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5c4f9-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="5c4f9-104">\<routing></span></span>  
<span data-ttu-id="5c4f9-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="5c4f9-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4f9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c4f9-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c4f9-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5c4f9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5c4f9-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5c4f9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c4f9-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="5c4f9-109">Attributes</span></span>  
 <span data-ttu-id="5c4f9-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5c4f9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c4f9-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5c4f9-111">Child Elements</span></span>  
  
|<span data-ttu-id="5c4f9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c4f9-112">Element</span></span>|<span data-ttu-id="5c4f9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c4f9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c4f9-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="5c4f9-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="5c4f9-115">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="5c4f9-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c4f9-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5c4f9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5c4f9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c4f9-117">Element</span></span>|<span data-ttu-id="5c4f9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c4f9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c4f9-119">\<routing></span><span class="sxs-lookup"><span data-stu-id="5c4f9-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="5c4f9-120">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="5c4f9-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c4f9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c4f9-121">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
