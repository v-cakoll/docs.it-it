---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397877"
---
# \<knownType>
<span data-ttu-id="187a5-101">Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="187a5-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="187a5-102">L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato".</span><span class="sxs-lookup"><span data-stu-id="187a5-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="187a5-103">Per ulteriori informazioni, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="187a5-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="187a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="187a5-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="187a5-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="187a5-105">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="187a5-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="187a5-106">Attributes and Elements</span></span>  
 <span data-ttu-id="187a5-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="187a5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="187a5-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="187a5-108">Attributes</span></span>  
  
|<span data-ttu-id="187a5-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="187a5-109">Attribute</span></span>|<span data-ttu-id="187a5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="187a5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="187a5-111">type</span><span class="sxs-lookup"><span data-stu-id="187a5-111">type</span></span>|<span data-ttu-id="187a5-112">Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="187a5-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="187a5-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="187a5-113">Child Elements</span></span>  
  
|<span data-ttu-id="187a5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="187a5-114">Element</span></span>|<span data-ttu-id="187a5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="187a5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="187a5-116">Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="187a5-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="187a5-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="187a5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="187a5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="187a5-118">Element</span></span>|<span data-ttu-id="187a5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="187a5-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="187a5-120">Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.</span><span class="sxs-lookup"><span data-stu-id="187a5-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="187a5-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="187a5-121">Remarks</span></span>  
 <span data-ttu-id="187a5-122">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="187a5-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="187a5-123">Vedere [\<dataContractSerializer>](datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="187a5-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="187a5-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="187a5-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="187a5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="187a5-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="187a5-126">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="187a5-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
