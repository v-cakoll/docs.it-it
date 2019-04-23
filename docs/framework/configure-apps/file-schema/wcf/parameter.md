---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230798"
---
# <a name="parameter"></a><span data-ttu-id="4b5fe-101">\<Parametro ></span><span class="sxs-lookup"><span data-stu-id="4b5fe-101">\<parameter></span></span>
<span data-ttu-id="4b5fe-102">Specifica il parametro generico quando un tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="4b5fe-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="4b5fe-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="4b5fe-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="4b5fe-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="4b5fe-105">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="4b5fe-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="4b5fe-106">\<aggiungere > (elemento) per \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="4b5fe-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="4b5fe-107">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="4b5fe-107">\<knownType> Element</span></span>  
<span data-ttu-id="4b5fe-108">\<parametro > elemento</span><span class="sxs-lookup"><span data-stu-id="4b5fe-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5fe-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b5fe-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b5fe-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b5fe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4b5fe-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b5fe-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b5fe-112">Attributes</span></span>  
  
|<span data-ttu-id="4b5fe-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4b5fe-113">Attribute</span></span>|<span data-ttu-id="4b5fe-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b5fe-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b5fe-115">indice</span><span class="sxs-lookup"><span data-stu-id="4b5fe-115">index</span></span>|<span data-ttu-id="4b5fe-116">Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="4b5fe-117">tipo</span><span class="sxs-lookup"><span data-stu-id="4b5fe-117">type</span></span>|<span data-ttu-id="4b5fe-118">Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="4b5fe-119">Attributo index</span><span class="sxs-lookup"><span data-stu-id="4b5fe-119">index Attribute</span></span>  
  
|<span data-ttu-id="4b5fe-120">Value</span><span class="sxs-lookup"><span data-stu-id="4b5fe-120">Value</span></span>|<span data-ttu-id="4b5fe-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b5fe-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b5fe-122">"0"</span><span class="sxs-lookup"><span data-stu-id="4b5fe-122">"0"</span></span>|<span data-ttu-id="4b5fe-123">Primo parametro del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-123">The first parameter in the generic type.</span></span> <span data-ttu-id="4b5fe-124">Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="4b5fe-125">Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".</span><span class="sxs-lookup"><span data-stu-id="4b5fe-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="4b5fe-126">"1"</span><span class="sxs-lookup"><span data-stu-id="4b5fe-126">"1"</span></span>|<span data-ttu-id="4b5fe-127">Secondo parametro di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-127">The second parameter in a generic type.</span></span> <span data-ttu-id="4b5fe-128">Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="4b5fe-129">Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".</span><span class="sxs-lookup"><span data-stu-id="4b5fe-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b5fe-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b5fe-130">Child Elements</span></span>  
 <span data-ttu-id="4b5fe-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b5fe-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b5fe-132">Parent Elements</span></span>  
  
|<span data-ttu-id="4b5fe-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b5fe-133">Element</span></span>|<span data-ttu-id="4b5fe-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b5fe-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b5fe-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="4b5fe-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="4b5fe-136">Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b5fe-137">Note</span><span class="sxs-lookup"><span data-stu-id="4b5fe-137">Remarks</span></span>  
 <span data-ttu-id="4b5fe-138">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="4b5fe-139">Vedere le [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="4b5fe-140">Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="4b5fe-141">Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="4b5fe-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5fe-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b5fe-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="4b5fe-143">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="4b5fe-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="4b5fe-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="4b5fe-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="4b5fe-145">\<add></span><span class="sxs-lookup"><span data-stu-id="4b5fe-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
