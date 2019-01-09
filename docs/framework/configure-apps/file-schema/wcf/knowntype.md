---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6156f102573333ec0d5533b8f1a8506d91215f47
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151930"
---
# <a name="ltknowntypegt"></a><span data-ttu-id="5d02d-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="5d02d-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="5d02d-103">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="5d02d-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="5d02d-104">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="5d02d-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="5d02d-105">Per altre informazioni, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5d02d-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="5d02d-106">\<Serialization ></span><span class="sxs-lookup"><span data-stu-id="5d02d-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="5d02d-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5d02d-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="5d02d-108">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="5d02d-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="5d02d-109">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5d02d-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="5d02d-110">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="5d02d-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d02d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d02d-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="5d02d-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d02d-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d02d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d02d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5d02d-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d02d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d02d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d02d-115">Attributes</span></span>  
  
|<span data-ttu-id="5d02d-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="5d02d-116">Attribute</span></span>|<span data-ttu-id="5d02d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d02d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d02d-118">tipo</span><span class="sxs-lookup"><span data-stu-id="5d02d-118">type</span></span>|<span data-ttu-id="5d02d-119">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5d02d-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d02d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d02d-120">Child Elements</span></span>  
  
|<span data-ttu-id="5d02d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d02d-121">Element</span></span>|<span data-ttu-id="5d02d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d02d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d02d-123">\<Parametro ></span><span class="sxs-lookup"><span data-stu-id="5d02d-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="5d02d-124">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5d02d-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d02d-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d02d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5d02d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d02d-126">Element</span></span>|<span data-ttu-id="5d02d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d02d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d02d-128">\<add></span><span class="sxs-lookup"><span data-stu-id="5d02d-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="5d02d-129">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="5d02d-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d02d-130">Note</span><span class="sxs-lookup"><span data-stu-id="5d02d-130">Remarks</span></span>  
 <span data-ttu-id="5d02d-131">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5d02d-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5d02d-132">Vedere le [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5d02d-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d02d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d02d-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d02d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d02d-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="5d02d-135">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="5d02d-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="5d02d-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5d02d-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="5d02d-137">\<add></span><span class="sxs-lookup"><span data-stu-id="5d02d-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
