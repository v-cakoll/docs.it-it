---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: b2445f12f1eaac03b3f3ab66f3d13a5f465a1133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753326"
---
# <a name="ltknowntypegt"></a><span data-ttu-id="64e65-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="64e65-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="64e65-103">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="64e65-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="64e65-104">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="64e65-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="64e65-105">Per ulteriori informazioni, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="64e65-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="64e65-106">\<Serialization ></span><span class="sxs-lookup"><span data-stu-id="64e65-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="64e65-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="64e65-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="64e65-108">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="64e65-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="64e65-109">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="64e65-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="64e65-110">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="64e65-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e65-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64e65-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="64e65-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="64e65-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64e65-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64e65-113">Attributes and Elements</span></span>  
 <span data-ttu-id="64e65-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64e65-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64e65-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="64e65-115">Attributes</span></span>  
  
|<span data-ttu-id="64e65-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="64e65-116">Attribute</span></span>|<span data-ttu-id="64e65-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64e65-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64e65-118">tipo</span><span class="sxs-lookup"><span data-stu-id="64e65-118">type</span></span>|<span data-ttu-id="64e65-119">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="64e65-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64e65-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64e65-120">Child Elements</span></span>  
  
|<span data-ttu-id="64e65-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="64e65-121">Element</span></span>|<span data-ttu-id="64e65-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64e65-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64e65-123">\<parametro ></span><span class="sxs-lookup"><span data-stu-id="64e65-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="64e65-124">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="64e65-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64e65-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64e65-125">Parent Elements</span></span>  
  
|<span data-ttu-id="64e65-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="64e65-126">Element</span></span>|<span data-ttu-id="64e65-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64e65-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64e65-128">\<add></span><span class="sxs-lookup"><span data-stu-id="64e65-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="64e65-129">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="64e65-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64e65-130">Note</span><span class="sxs-lookup"><span data-stu-id="64e65-130">Remarks</span></span>  
 <span data-ttu-id="64e65-131">Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="64e65-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="64e65-132">Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="64e65-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64e65-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="64e65-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64e65-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64e65-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="64e65-135">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="64e65-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="64e65-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="64e65-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="64e65-137">\<add></span><span class="sxs-lookup"><span data-stu-id="64e65-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
