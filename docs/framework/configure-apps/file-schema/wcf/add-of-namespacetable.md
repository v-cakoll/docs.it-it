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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f08f4b46c6e6290602fc78a2f06954b9cf0b07d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="8b9b8-102">&lt;add&gt; di &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="8b9b8-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="8b9b8-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="8b9b8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8b9b8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8b9b8-105">\<routing ></span><span class="sxs-lookup"><span data-stu-id="8b9b8-105">\<routing></span></span>  
<span data-ttu-id="8b9b8-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="8b9b8-106">\<namespaceTable></span></span>  
<span data-ttu-id="8b9b8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8b9b8-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b9b8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b9b8-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b9b8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8b9b8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8b9b8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b9b8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8b9b8-111">Attributes</span></span>  
  
|<span data-ttu-id="8b9b8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8b9b8-112">Attribute</span></span>|<span data-ttu-id="8b9b8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b9b8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b9b8-114">namespace</span><span class="sxs-lookup"><span data-stu-id="8b9b8-114">namespace</span></span>|<span data-ttu-id="8b9b8-115">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="8b9b8-116">prefix</span><span class="sxs-lookup"><span data-stu-id="8b9b8-116">prefix</span></span>|<span data-ttu-id="8b9b8-117">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b9b8-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8b9b8-118">Child Elements</span></span>  
 <span data-ttu-id="8b9b8-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b9b8-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8b9b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8b9b8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b9b8-121">Element</span></span>|<span data-ttu-id="8b9b8-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b9b8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b9b8-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="8b9b8-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="8b9b8-124">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="8b9b8-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b9b8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b9b8-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
