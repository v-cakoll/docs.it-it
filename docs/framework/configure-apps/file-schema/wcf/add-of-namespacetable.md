---
title: '&lt;add&gt; di &lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 394657abcebb42192fb7a8b57b0402bcacf37693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="7828b-102">&lt;add&gt; di &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="7828b-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="7828b-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="7828b-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="7828b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7828b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7828b-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="7828b-105">\<routing></span></span>  
<span data-ttu-id="7828b-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="7828b-106">\<namespaceTable></span></span>  
<span data-ttu-id="7828b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7828b-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7828b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7828b-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7828b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7828b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7828b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7828b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7828b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7828b-111">Attributes</span></span>  
  
|<span data-ttu-id="7828b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7828b-112">Attribute</span></span>|<span data-ttu-id="7828b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7828b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7828b-114">namespace</span><span class="sxs-lookup"><span data-stu-id="7828b-114">namespace</span></span>|<span data-ttu-id="7828b-115">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7828b-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="7828b-116">prefix</span><span class="sxs-lookup"><span data-stu-id="7828b-116">prefix</span></span>|<span data-ttu-id="7828b-117">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7828b-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7828b-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7828b-118">Child Elements</span></span>  
 <span data-ttu-id="7828b-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7828b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7828b-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7828b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7828b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7828b-121">Element</span></span>|<span data-ttu-id="7828b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7828b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7828b-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="7828b-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="7828b-124">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="7828b-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7828b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7828b-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
