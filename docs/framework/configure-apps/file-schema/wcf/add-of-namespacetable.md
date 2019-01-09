---
title: '&lt;add&gt; di &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: ef4f1c46a0ee3b94e5548b752e4e0a6a759fd45b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149514"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="01dec-102">&lt;add&gt; di &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="01dec-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="01dec-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="01dec-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="01dec-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="01dec-104">\<system.serviceModel></span></span>  
<span data-ttu-id="01dec-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="01dec-105">\<routing></span></span>  
<span data-ttu-id="01dec-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="01dec-106">\<namespaceTable></span></span>  
<span data-ttu-id="01dec-107">\<add></span><span class="sxs-lookup"><span data-stu-id="01dec-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01dec-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01dec-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01dec-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01dec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01dec-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01dec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01dec-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="01dec-111">Attributes</span></span>  
  
|<span data-ttu-id="01dec-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="01dec-112">Attribute</span></span>|<span data-ttu-id="01dec-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01dec-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01dec-114">namespace</span><span class="sxs-lookup"><span data-stu-id="01dec-114">namespace</span></span>|<span data-ttu-id="01dec-115">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="01dec-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="01dec-116">prefix</span><span class="sxs-lookup"><span data-stu-id="01dec-116">prefix</span></span>|<span data-ttu-id="01dec-117">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="01dec-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01dec-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01dec-118">Child Elements</span></span>  
 <span data-ttu-id="01dec-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="01dec-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01dec-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01dec-120">Parent Elements</span></span>  
  
|<span data-ttu-id="01dec-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="01dec-121">Element</span></span>|<span data-ttu-id="01dec-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01dec-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01dec-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="01dec-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="01dec-124">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="01dec-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01dec-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01dec-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
