---
title: '&lt;knownType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ccb7152197a021821936e178e0de77b9dfabce45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltknowntypegt"></a><span data-ttu-id="194ec-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="194ec-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="194ec-103">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="194ec-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="194ec-104">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="194ec-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="194ec-105">Per ulteriori informazioni, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="194ec-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="194ec-106">\<Serialization ></span><span class="sxs-lookup"><span data-stu-id="194ec-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="194ec-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="194ec-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="194ec-108">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="194ec-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="194ec-109">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="194ec-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="194ec-110">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="194ec-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194ec-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="194ec-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="194ec-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="194ec-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="194ec-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="194ec-113">Attributes and Elements</span></span>  
 <span data-ttu-id="194ec-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="194ec-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="194ec-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="194ec-115">Attributes</span></span>  
  
|<span data-ttu-id="194ec-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="194ec-116">Attribute</span></span>|<span data-ttu-id="194ec-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="194ec-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="194ec-118">tipo</span><span class="sxs-lookup"><span data-stu-id="194ec-118">type</span></span>|<span data-ttu-id="194ec-119">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="194ec-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="194ec-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="194ec-120">Child Elements</span></span>  
  
|<span data-ttu-id="194ec-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="194ec-121">Element</span></span>|<span data-ttu-id="194ec-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="194ec-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="194ec-123">\<parametro ></span><span class="sxs-lookup"><span data-stu-id="194ec-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="194ec-124">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="194ec-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="194ec-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="194ec-125">Parent Elements</span></span>  
  
|<span data-ttu-id="194ec-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="194ec-126">Element</span></span>|<span data-ttu-id="194ec-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="194ec-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="194ec-128">\<add></span><span class="sxs-lookup"><span data-stu-id="194ec-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="194ec-129">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="194ec-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="194ec-130">Note</span><span class="sxs-lookup"><span data-stu-id="194ec-130">Remarks</span></span>  
 <span data-ttu-id="194ec-131">Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="194ec-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="194ec-132">Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="194ec-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="194ec-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="194ec-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="194ec-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="194ec-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="194ec-135">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="194ec-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="194ec-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="194ec-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="194ec-137">\<add></span><span class="sxs-lookup"><span data-stu-id="194ec-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
