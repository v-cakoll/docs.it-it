---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e2a2e26099f2d31116e4a89297fc1ac984c480d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920070"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="84630-102">\<aggiungere > di \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="84630-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="84630-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="84630-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="84630-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="84630-104">\<system.serviceModel></span></span>  
<span data-ttu-id="84630-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="84630-105">\<routing></span></span>  
<span data-ttu-id="84630-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="84630-106">\<namespaceTable></span></span>  
<span data-ttu-id="84630-107">\<add></span><span class="sxs-lookup"><span data-stu-id="84630-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84630-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84630-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84630-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="84630-109">Attributes and Elements</span></span>  
 <span data-ttu-id="84630-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="84630-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84630-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="84630-111">Attributes</span></span>  
  
|<span data-ttu-id="84630-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="84630-112">Attribute</span></span>|<span data-ttu-id="84630-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84630-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84630-114">namespace</span><span class="sxs-lookup"><span data-stu-id="84630-114">namespace</span></span>|<span data-ttu-id="84630-115">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="84630-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="84630-116">prefix</span><span class="sxs-lookup"><span data-stu-id="84630-116">prefix</span></span>|<span data-ttu-id="84630-117">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="84630-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84630-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="84630-118">Child Elements</span></span>  
 <span data-ttu-id="84630-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="84630-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84630-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="84630-120">Parent Elements</span></span>  
  
|<span data-ttu-id="84630-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="84630-121">Element</span></span>|<span data-ttu-id="84630-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84630-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84630-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="84630-123">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="84630-124">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="84630-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84630-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84630-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
