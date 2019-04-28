---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e65b66170465a8b3bb60754feebb7730b959d9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673667"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="2a391-102">\<aggiungere > di \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="2a391-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="2a391-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="2a391-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="2a391-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a391-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2a391-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="2a391-105">\<routing></span></span>  
<span data-ttu-id="2a391-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="2a391-106">\<namespaceTable></span></span>  
<span data-ttu-id="2a391-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2a391-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a391-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a391-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a391-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2a391-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2a391-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2a391-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a391-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="2a391-111">Attributes</span></span>  
  
|<span data-ttu-id="2a391-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="2a391-112">Attribute</span></span>|<span data-ttu-id="2a391-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a391-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a391-114">namespace</span><span class="sxs-lookup"><span data-stu-id="2a391-114">namespace</span></span>|<span data-ttu-id="2a391-115">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2a391-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="2a391-116">prefix</span><span class="sxs-lookup"><span data-stu-id="2a391-116">prefix</span></span>|<span data-ttu-id="2a391-117">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2a391-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a391-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2a391-118">Child Elements</span></span>  
 <span data-ttu-id="2a391-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2a391-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a391-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2a391-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2a391-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a391-121">Element</span></span>|<span data-ttu-id="2a391-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a391-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a391-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="2a391-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="2a391-124">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="2a391-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a391-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a391-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
