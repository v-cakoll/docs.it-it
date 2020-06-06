---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850390"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="5a636-102">\<add> di \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="5a636-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="5a636-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="5a636-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5a636-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a636-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a636-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5a636-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5a636-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5a636-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a636-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a636-107">Attributes</span></span>  
  
|<span data-ttu-id="5a636-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5a636-108">Attribute</span></span>|<span data-ttu-id="5a636-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a636-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a636-110">namespace</span><span class="sxs-lookup"><span data-stu-id="5a636-110">namespace</span></span>|<span data-ttu-id="5a636-111">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5a636-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="5a636-112">prefix</span><span class="sxs-lookup"><span data-stu-id="5a636-112">prefix</span></span>|<span data-ttu-id="5a636-113">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5a636-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a636-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a636-114">Child Elements</span></span>  
 <span data-ttu-id="5a636-115">No.</span><span class="sxs-lookup"><span data-stu-id="5a636-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a636-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5a636-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5a636-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a636-117">Element</span></span>|<span data-ttu-id="5a636-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a636-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="5a636-119">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="5a636-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a636-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a636-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
