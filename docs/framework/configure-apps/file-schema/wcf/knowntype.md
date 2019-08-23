---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928860"
---
# <a name="knowntype"></a><span data-ttu-id="6feeb-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="6feeb-101">\<knownType></span></span>
<span data-ttu-id="6feeb-102">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="6feeb-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="6feeb-103">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="6feeb-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="6feeb-104">Per ulteriori informazioni, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="6feeb-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="6feeb-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="6feeb-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="6feeb-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="6feeb-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="6feeb-107">\<Elemento > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="6feeb-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="6feeb-108">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="6feeb-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="6feeb-109">\<Elemento > knownType</span><span class="sxs-lookup"><span data-stu-id="6feeb-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6feeb-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6feeb-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="6feeb-111">Type</span><span class="sxs-lookup"><span data-stu-id="6feeb-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6feeb-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6feeb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6feeb-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6feeb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6feeb-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="6feeb-114">Attributes</span></span>  
  
|<span data-ttu-id="6feeb-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="6feeb-115">Attribute</span></span>|<span data-ttu-id="6feeb-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6feeb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6feeb-117">type</span><span class="sxs-lookup"><span data-stu-id="6feeb-117">type</span></span>|<span data-ttu-id="6feeb-118">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6feeb-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6feeb-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6feeb-119">Child Elements</span></span>  
  
|<span data-ttu-id="6feeb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6feeb-120">Element</span></span>|<span data-ttu-id="6feeb-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6feeb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6feeb-122">\<> parametro</span><span class="sxs-lookup"><span data-stu-id="6feeb-122">\<parameter></span></span>](parameter.md)|<span data-ttu-id="6feeb-123">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="6feeb-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6feeb-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6feeb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6feeb-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6feeb-125">Element</span></span>|<span data-ttu-id="6feeb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6feeb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6feeb-127">\<add></span><span class="sxs-lookup"><span data-stu-id="6feeb-127">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="6feeb-128">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="6feeb-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6feeb-129">Note</span><span class="sxs-lookup"><span data-stu-id="6feeb-129">Remarks</span></span>  
 <span data-ttu-id="6feeb-130">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6feeb-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6feeb-131">Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="6feeb-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6feeb-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6feeb-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="6feeb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6feeb-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="6feeb-134">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="6feeb-134">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="6feeb-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="6feeb-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="6feeb-136">\<add></span><span class="sxs-lookup"><span data-stu-id="6feeb-136">\<add></span></span>](add-of-declaredtypes-element.md)
