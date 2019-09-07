---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400107"
---
# <a name="parameter"></a><span data-ttu-id="f51e2-101">\<> parametro</span><span class="sxs-lookup"><span data-stu-id="f51e2-101">\<parameter></span></span>
<span data-ttu-id="f51e2-102">Specifica il parametro generico quando un tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="f51e2-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="f51e2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f51e2-104">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="f51e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="f51e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="f51e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="f51e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> knownType**](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="f51e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="f51e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> parametro**</span><span class="sxs-lookup"><span data-stu-id="f51e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51e2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f51e2-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f51e2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f51e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f51e2-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f51e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f51e2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f51e2-113">Attributes</span></span>  
  
|<span data-ttu-id="f51e2-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f51e2-114">Attribute</span></span>|<span data-ttu-id="f51e2-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f51e2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f51e2-116">index</span><span class="sxs-lookup"><span data-stu-id="f51e2-116">index</span></span>|<span data-ttu-id="f51e2-117">Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="f51e2-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="f51e2-118">type</span><span class="sxs-lookup"><span data-stu-id="f51e2-118">type</span></span>|<span data-ttu-id="f51e2-119">Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f51e2-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="f51e2-120">Attributo index</span><span class="sxs-lookup"><span data-stu-id="f51e2-120">index Attribute</span></span>  
  
|<span data-ttu-id="f51e2-121">Valore</span><span class="sxs-lookup"><span data-stu-id="f51e2-121">Value</span></span>|<span data-ttu-id="f51e2-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f51e2-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f51e2-123">"0"</span><span class="sxs-lookup"><span data-stu-id="f51e2-123">"0"</span></span>|<span data-ttu-id="f51e2-124">Primo parametro del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="f51e2-124">The first parameter in the generic type.</span></span> <span data-ttu-id="f51e2-125">Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="f51e2-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="f51e2-126">Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".</span><span class="sxs-lookup"><span data-stu-id="f51e2-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="f51e2-127">"1"</span><span class="sxs-lookup"><span data-stu-id="f51e2-127">"1"</span></span>|<span data-ttu-id="f51e2-128">Secondo parametro di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="f51e2-128">The second parameter in a generic type.</span></span> <span data-ttu-id="f51e2-129">Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri.</span><span class="sxs-lookup"><span data-stu-id="f51e2-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="f51e2-130">Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".</span><span class="sxs-lookup"><span data-stu-id="f51e2-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f51e2-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f51e2-131">Child Elements</span></span>  
 <span data-ttu-id="f51e2-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f51e2-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f51e2-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f51e2-133">Parent Elements</span></span>  
  
|<span data-ttu-id="f51e2-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="f51e2-134">Element</span></span>|<span data-ttu-id="f51e2-135">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f51e2-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f51e2-136">\<knownType></span><span class="sxs-lookup"><span data-stu-id="f51e2-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="f51e2-137">Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="f51e2-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f51e2-138">Note</span><span class="sxs-lookup"><span data-stu-id="f51e2-138">Remarks</span></span>  
 <span data-ttu-id="f51e2-139">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f51e2-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f51e2-140">Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="f51e2-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="f51e2-141">Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi.</span><span class="sxs-lookup"><span data-stu-id="f51e2-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="f51e2-142">Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="f51e2-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51e2-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f51e2-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="f51e2-144">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="f51e2-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="f51e2-145">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="f51e2-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="f51e2-146">\<add></span><span class="sxs-lookup"><span data-stu-id="f51e2-146">\<add></span></span>](add-of-declaredtypes-element.md)
