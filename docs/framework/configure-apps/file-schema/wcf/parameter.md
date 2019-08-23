---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: c3f2179835ad1232e115cad0decdd3d41bbdc160
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932840"
---
# <a name="parameter"></a><span data-ttu-id="dbd58-101">\<> parametro</span><span class="sxs-lookup"><span data-stu-id="dbd58-101">\<parameter></span></span>
<span data-ttu-id="dbd58-102">Specifica il parametro generico quando un tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="dbd58-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="dbd58-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="dbd58-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="dbd58-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="dbd58-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="dbd58-105">\<Elemento > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="dbd58-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="dbd58-106">\<aggiungere > elemento per \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="dbd58-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="dbd58-107">\<Elemento > knownType</span><span class="sxs-lookup"><span data-stu-id="dbd58-107">\<knownType> Element</span></span>  
<span data-ttu-id="dbd58-108">\<Parameter > elemento</span><span class="sxs-lookup"><span data-stu-id="dbd58-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd58-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbd58-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbd58-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbd58-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dbd58-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbd58-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbd58-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbd58-112">Attributes</span></span>  
  
|<span data-ttu-id="dbd58-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="dbd58-113">Attribute</span></span>|<span data-ttu-id="dbd58-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd58-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbd58-115">index</span><span class="sxs-lookup"><span data-stu-id="dbd58-115">index</span></span>|<span data-ttu-id="dbd58-116">Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="dbd58-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="dbd58-117">type</span><span class="sxs-lookup"><span data-stu-id="dbd58-117">type</span></span>|<span data-ttu-id="dbd58-118">Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dbd58-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="dbd58-119">Attributo index</span><span class="sxs-lookup"><span data-stu-id="dbd58-119">index Attribute</span></span>  
  
|<span data-ttu-id="dbd58-120">Value</span><span class="sxs-lookup"><span data-stu-id="dbd58-120">Value</span></span>|<span data-ttu-id="dbd58-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dbd58-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dbd58-122">"0"</span><span class="sxs-lookup"><span data-stu-id="dbd58-122">"0"</span></span>|<span data-ttu-id="dbd58-123">Primo parametro del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="dbd58-123">The first parameter in the generic type.</span></span> <span data-ttu-id="dbd58-124">Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="dbd58-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="dbd58-125">Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".</span><span class="sxs-lookup"><span data-stu-id="dbd58-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="dbd58-126">"1"</span><span class="sxs-lookup"><span data-stu-id="dbd58-126">"1"</span></span>|<span data-ttu-id="dbd58-127">Secondo parametro di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="dbd58-127">The second parameter in a generic type.</span></span> <span data-ttu-id="dbd58-128">Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri.</span><span class="sxs-lookup"><span data-stu-id="dbd58-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="dbd58-129">Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".</span><span class="sxs-lookup"><span data-stu-id="dbd58-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbd58-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbd58-130">Child Elements</span></span>  
 <span data-ttu-id="dbd58-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dbd58-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbd58-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbd58-132">Parent Elements</span></span>  
  
|<span data-ttu-id="dbd58-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbd58-133">Element</span></span>|<span data-ttu-id="dbd58-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbd58-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbd58-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="dbd58-135">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="dbd58-136">Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="dbd58-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd58-137">Note</span><span class="sxs-lookup"><span data-stu-id="dbd58-137">Remarks</span></span>  
 <span data-ttu-id="dbd58-138">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dbd58-138">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="dbd58-139">Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="dbd58-139">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="dbd58-140">Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi.</span><span class="sxs-lookup"><span data-stu-id="dbd58-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="dbd58-141">Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="dbd58-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd58-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbd58-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="dbd58-143">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="dbd58-143">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="dbd58-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="dbd58-144">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="dbd58-145">\<add></span><span class="sxs-lookup"><span data-stu-id="dbd58-145">\<add></span></span>](add-of-declaredtypes-element.md)
