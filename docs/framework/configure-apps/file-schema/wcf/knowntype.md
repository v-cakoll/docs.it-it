---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397877"
---
# <a name="knowntype"></a><span data-ttu-id="119b2-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="119b2-101">\<knownType></span></span>
<span data-ttu-id="119b2-102">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="119b2-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="119b2-103">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="119b2-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="119b2-104">Per ulteriori informazioni, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="119b2-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="119b2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="119b2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="119b2-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="119b2-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="119b2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="119b2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="119b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="119b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="119b2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="119b2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="119b2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> knownType**</span><span class="sxs-lookup"><span data-stu-id="119b2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119b2-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="119b2-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="119b2-112">Type</span><span class="sxs-lookup"><span data-stu-id="119b2-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="119b2-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="119b2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="119b2-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="119b2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="119b2-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="119b2-115">Attributes</span></span>  
  
|<span data-ttu-id="119b2-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="119b2-116">Attribute</span></span>|<span data-ttu-id="119b2-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="119b2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="119b2-118">type</span><span class="sxs-lookup"><span data-stu-id="119b2-118">type</span></span>|<span data-ttu-id="119b2-119">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="119b2-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="119b2-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="119b2-120">Child Elements</span></span>  
  
|<span data-ttu-id="119b2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="119b2-121">Element</span></span>|<span data-ttu-id="119b2-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="119b2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="119b2-123">\<> parametro</span><span class="sxs-lookup"><span data-stu-id="119b2-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="119b2-124">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="119b2-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="119b2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="119b2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="119b2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="119b2-126">Element</span></span>|<span data-ttu-id="119b2-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="119b2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="119b2-128">\<add></span><span class="sxs-lookup"><span data-stu-id="119b2-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="119b2-129">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="119b2-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="119b2-130">Note</span><span class="sxs-lookup"><span data-stu-id="119b2-130">Remarks</span></span>  
 <span data-ttu-id="119b2-131">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="119b2-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="119b2-132">Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="119b2-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="119b2-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="119b2-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="119b2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="119b2-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="119b2-135">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="119b2-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="119b2-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="119b2-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="119b2-137">\<add></span><span class="sxs-lookup"><span data-stu-id="119b2-137">\<add></span></span>](add-of-declaredtypes-element.md)
