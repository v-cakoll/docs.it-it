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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400662"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="8732c-102">\<add>dell' \<declaredTypes> elemento</span><span class="sxs-lookup"><span data-stu-id="8732c-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="8732c-103">Aggiunge un tipo usato dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="8732c-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="8732c-104">Ogni tipo dichiarato contiene i tipi noti che verranno restituiti come campo o come proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="8732c-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8732c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8732c-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8732c-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8732c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8732c-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8732c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8732c-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="8732c-108">Attributes</span></span>  
  
|<span data-ttu-id="8732c-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="8732c-109">Attribute</span></span>|<span data-ttu-id="8732c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8732c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8732c-111">type</span><span class="sxs-lookup"><span data-stu-id="8732c-111">type</span></span>|<span data-ttu-id="8732c-112">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8732c-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="8732c-113">Specifica il nome del tipo (compreso lo spazio dei nomi), il nome dell'assembly, il numero di versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="8732c-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8732c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8732c-114">Child Elements</span></span>  
  
|<span data-ttu-id="8732c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8732c-115">Element</span></span>|<span data-ttu-id="8732c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8732c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="8732c-117">Specifica il tipo conosciuto del tipo dichiarato da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="8732c-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="8732c-118">Se il tipo dichiarato è un tipo generico occorre aggiungere anche un elemento di parametro all'elemento `<knownType>` per specificare quale parametro generico viene usato per restituire il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="8732c-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8732c-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8732c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8732c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8732c-120">Element</span></span>|<span data-ttu-id="8732c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8732c-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="8732c-122">Contiene i tipi che richiedono tipi noti durante la deserializzazione eseguita dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8732c-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8732c-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="8732c-123">Remarks</span></span>  
 <span data-ttu-id="8732c-124">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="8732c-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8732c-125">Vedere [\<dataContractSerializer>](datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="8732c-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8732c-126">Se si aggiunge il tipo <xref:System.Object> come tipo `<declaredType>`, viene generata un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="8732c-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="8732c-127">Ciò è dovuto al fatto che il tipo <xref:System.Object> non può essere usato come tipo dichiarato in configurazione.</span><span class="sxs-lookup"><span data-stu-id="8732c-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8732c-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="8732c-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8732c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8732c-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="8732c-130">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="8732c-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="8732c-131">\<add>di\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="8732c-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
