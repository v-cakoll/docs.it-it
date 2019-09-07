---
title: <add>dell' <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400662"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="8f099-102">\<Aggiungi > dell' \<elemento > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="8f099-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="8f099-103">Aggiunge un tipo usato dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="8f099-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="8f099-104">Ogni tipo dichiarato contiene i tipi noti che verranno restituiti come campo o come proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="8f099-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="8f099-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f099-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f099-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="8f099-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="8f099-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="8f099-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="8f099-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="8f099-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="8f099-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="8f099-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f099-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f099-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f099-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8f099-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8f099-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8f099-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f099-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8f099-113">Attributes</span></span>  
  
|<span data-ttu-id="8f099-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8f099-114">Attribute</span></span>|<span data-ttu-id="8f099-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8f099-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f099-116">type</span><span class="sxs-lookup"><span data-stu-id="8f099-116">type</span></span>|<span data-ttu-id="8f099-117">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8f099-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="8f099-118">Specifica il nome del tipo (compreso lo spazio dei nomi), il nome dell'assembly, il numero di versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="8f099-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f099-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8f099-119">Child Elements</span></span>  
  
|<span data-ttu-id="8f099-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f099-120">Element</span></span>|<span data-ttu-id="8f099-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8f099-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f099-122">\<knownType></span><span class="sxs-lookup"><span data-stu-id="8f099-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="8f099-123">Specifica il tipo conosciuto del tipo dichiarato da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="8f099-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="8f099-124">Se il tipo dichiarato è un tipo generico occorre aggiungere anche un elemento di parametro all'elemento `<knownType>` per specificare quale parametro generico viene usato per restituire il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="8f099-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f099-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8f099-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8f099-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f099-126">Element</span></span>|<span data-ttu-id="8f099-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f099-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f099-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="8f099-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="8f099-129">Contiene i tipi che richiedono tipi noti durante la deserializzazione eseguita dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f099-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f099-130">Note</span><span class="sxs-lookup"><span data-stu-id="8f099-130">Remarks</span></span>  
 <span data-ttu-id="8f099-131">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f099-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8f099-132">Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="8f099-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f099-133">Se si aggiunge il tipo <xref:System.Object> come tipo `<declaredType>`, viene generata un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="8f099-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="8f099-134">Ciò è dovuto al fatto che il tipo <xref:System.Object> non può essere usato come tipo dichiarato in configurazione.</span><span class="sxs-lookup"><span data-stu-id="8f099-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f099-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f099-135">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="8f099-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f099-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="8f099-137">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="8f099-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="8f099-138">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="8f099-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="8f099-139">\<aggiungere > di \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="8f099-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
