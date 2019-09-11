---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850390"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="75729-102">\<aggiungere > di \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="75729-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="75729-103">Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="75729-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="75729-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75729-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75729-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="75729-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="75729-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="75729-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="75729-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> namespaceTable**](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="75729-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="75729-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="75729-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75729-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75729-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75729-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75729-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75729-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75729-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75729-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="75729-112">Attributes</span></span>  
  
|<span data-ttu-id="75729-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="75729-113">Attribute</span></span>|<span data-ttu-id="75729-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75729-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75729-115">namespace</span><span class="sxs-lookup"><span data-stu-id="75729-115">namespace</span></span>|<span data-ttu-id="75729-116">Stringa contenente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="75729-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="75729-117">prefix</span><span class="sxs-lookup"><span data-stu-id="75729-117">prefix</span></span>|<span data-ttu-id="75729-118">Stringa contenente il prefisso per questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="75729-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75729-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75729-119">Child Elements</span></span>  
 <span data-ttu-id="75729-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="75729-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75729-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75729-121">Parent Elements</span></span>  
  
|<span data-ttu-id="75729-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="75729-122">Element</span></span>|<span data-ttu-id="75729-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75729-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75729-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="75729-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="75729-125">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="75729-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75729-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75729-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
