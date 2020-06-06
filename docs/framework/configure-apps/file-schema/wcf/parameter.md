---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400107"
---
# \<parameter>
<span data-ttu-id="20a30-101">Specifica il parametro generico quando un tipo dichiarato è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="20a30-101">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="20a30-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20a30-102">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20a30-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="20a30-103">Attributes and Elements</span></span>  
 <span data-ttu-id="20a30-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="20a30-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20a30-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="20a30-105">Attributes</span></span>  
  
|<span data-ttu-id="20a30-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="20a30-106">Attribute</span></span>|<span data-ttu-id="20a30-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20a30-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20a30-108">indice</span><span class="sxs-lookup"><span data-stu-id="20a30-108">index</span></span>|<span data-ttu-id="20a30-109">Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="20a30-109">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="20a30-110">tipo</span><span class="sxs-lookup"><span data-stu-id="20a30-110">type</span></span>|<span data-ttu-id="20a30-111">Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="20a30-111">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="20a30-112">Attributo index</span><span class="sxs-lookup"><span data-stu-id="20a30-112">index Attribute</span></span>  
  
|<span data-ttu-id="20a30-113">Valore</span><span class="sxs-lookup"><span data-stu-id="20a30-113">Value</span></span>|<span data-ttu-id="20a30-114">Description</span><span class="sxs-lookup"><span data-stu-id="20a30-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="20a30-115">"0"</span><span class="sxs-lookup"><span data-stu-id="20a30-115">"0"</span></span>|<span data-ttu-id="20a30-116">Primo parametro del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="20a30-116">The first parameter in the generic type.</span></span> <span data-ttu-id="20a30-117">Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="20a30-117">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="20a30-118">Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".</span><span class="sxs-lookup"><span data-stu-id="20a30-118">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="20a30-119">"1"</span><span class="sxs-lookup"><span data-stu-id="20a30-119">"1"</span></span>|<span data-ttu-id="20a30-120">Secondo parametro di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="20a30-120">The second parameter in a generic type.</span></span> <span data-ttu-id="20a30-121">Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri.</span><span class="sxs-lookup"><span data-stu-id="20a30-121">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="20a30-122">Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".</span><span class="sxs-lookup"><span data-stu-id="20a30-122">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20a30-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="20a30-123">Child Elements</span></span>  
 <span data-ttu-id="20a30-124">No.</span><span class="sxs-lookup"><span data-stu-id="20a30-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20a30-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="20a30-125">Parent Elements</span></span>  
  
|<span data-ttu-id="20a30-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="20a30-126">Element</span></span>|<span data-ttu-id="20a30-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20a30-127">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="20a30-128">Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="20a30-128">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20a30-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="20a30-129">Remarks</span></span>  
 <span data-ttu-id="20a30-130">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="20a30-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="20a30-131">Vedere [\<dataContractSerializer>](datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="20a30-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="20a30-132">Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi.</span><span class="sxs-lookup"><span data-stu-id="20a30-132">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="20a30-133">Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="20a30-133">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a30-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="20a30-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="20a30-135">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="20a30-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
