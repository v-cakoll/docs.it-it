---
title: '&lt;parametro&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdbb47fcb65273d03d226e13730849170d4345c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="d2d5d-102">&lt;parametro&gt;</span><span class="sxs-lookup"><span data-stu-id="d2d5d-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="d2d5d-103">Specifica il parametro generico quando un tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="d2d5d-104">\<Serialization ></span><span class="sxs-lookup"><span data-stu-id="d2d5d-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="d2d5d-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="d2d5d-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="d2d5d-106">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="d2d5d-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="d2d5d-107">\<aggiungere > elemento per \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="d2d5d-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="d2d5d-108">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="d2d5d-108">\<knownType> Element</span></span>  
<span data-ttu-id="d2d5d-109">\<parametro > elemento</span><span class="sxs-lookup"><span data-stu-id="d2d5d-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d5d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2d5d-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2d5d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d2d5d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2d5d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2d5d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d2d5d-113">Attributes</span></span>  
  
|<span data-ttu-id="d2d5d-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d2d5d-114">Attribute</span></span>|<span data-ttu-id="d2d5d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2d5d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2d5d-116">indice</span><span class="sxs-lookup"><span data-stu-id="d2d5d-116">index</span></span>|<span data-ttu-id="d2d5d-117">Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="d2d5d-118">tipo</span><span class="sxs-lookup"><span data-stu-id="d2d5d-118">type</span></span>|<span data-ttu-id="d2d5d-119">Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="d2d5d-120">Attributo index</span><span class="sxs-lookup"><span data-stu-id="d2d5d-120">index Attribute</span></span>  
  
|<span data-ttu-id="d2d5d-121">Valore</span><span class="sxs-lookup"><span data-stu-id="d2d5d-121">Value</span></span>|<span data-ttu-id="d2d5d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2d5d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d2d5d-123">"0"</span><span class="sxs-lookup"><span data-stu-id="d2d5d-123">"0"</span></span>|<span data-ttu-id="d2d5d-124">Primo parametro del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-124">The first parameter in the generic type.</span></span> <span data-ttu-id="d2d5d-125">Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="d2d5d-126">Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".</span><span class="sxs-lookup"><span data-stu-id="d2d5d-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="d2d5d-127">"1"</span><span class="sxs-lookup"><span data-stu-id="d2d5d-127">"1"</span></span>|<span data-ttu-id="d2d5d-128">Secondo parametro di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-128">The second parameter in a generic type.</span></span> <span data-ttu-id="d2d5d-129">Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="d2d5d-130">Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".</span><span class="sxs-lookup"><span data-stu-id="d2d5d-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2d5d-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2d5d-131">Child Elements</span></span>  
 <span data-ttu-id="d2d5d-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2d5d-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d2d5d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d2d5d-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2d5d-134">Element</span></span>|<span data-ttu-id="d2d5d-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2d5d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2d5d-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="d2d5d-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="d2d5d-137">Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2d5d-138">Note</span><span class="sxs-lookup"><span data-stu-id="d2d5d-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="d2d5d-139">i tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d2d5d-140">Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="d2d5d-141">Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="d2d5d-142">Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="d2d5d-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d5d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2d5d-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="d2d5d-144">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="d2d5d-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="d2d5d-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="d2d5d-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="d2d5d-146">\<add></span><span class="sxs-lookup"><span data-stu-id="d2d5d-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
