---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148837"
---
# <a name="knowntype"></a><span data-ttu-id="7fbc1-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="7fbc1-101">\<knownType></span></span>
<span data-ttu-id="7fbc1-102">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7fbc1-103">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="7fbc1-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="7fbc1-104">Per altre informazioni, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="7fbc1-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="7fbc1-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7fbc1-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="7fbc1-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7fbc1-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="7fbc1-107">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="7fbc1-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="7fbc1-108">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="7fbc1-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="7fbc1-109">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="7fbc1-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbc1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fbc1-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="7fbc1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7fbc1-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fbc1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7fbc1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7fbc1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fbc1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7fbc1-114">Attributes</span></span>  
  
|<span data-ttu-id="7fbc1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="7fbc1-115">Attribute</span></span>|<span data-ttu-id="7fbc1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbc1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fbc1-117">tipo</span><span class="sxs-lookup"><span data-stu-id="7fbc1-117">type</span></span>|<span data-ttu-id="7fbc1-118">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fbc1-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7fbc1-119">Child Elements</span></span>  
  
|<span data-ttu-id="7fbc1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fbc1-120">Element</span></span>|<span data-ttu-id="7fbc1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbc1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fbc1-122">\<Parametro ></span><span class="sxs-lookup"><span data-stu-id="7fbc1-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="7fbc1-123">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7fbc1-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7fbc1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7fbc1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fbc1-125">Element</span></span>|<span data-ttu-id="7fbc1-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbc1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fbc1-127">\<add></span><span class="sxs-lookup"><span data-stu-id="7fbc1-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="7fbc1-128">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fbc1-129">Note</span><span class="sxs-lookup"><span data-stu-id="7fbc1-129">Remarks</span></span>  
 <span data-ttu-id="7fbc1-130">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7fbc1-131">Vedere le [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="7fbc1-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fbc1-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fbc1-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7fbc1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbc1-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7fbc1-134">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="7fbc1-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7fbc1-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7fbc1-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="7fbc1-136">\<add></span><span class="sxs-lookup"><span data-stu-id="7fbc1-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
