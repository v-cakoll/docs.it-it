---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 8919ee717012f8badcf7015bf8d850ed431c5943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090277"
---
# <a name="declaredtypes"></a><span data-ttu-id="15dc5-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="15dc5-101">\<declaredTypes></span></span>
<span data-ttu-id="15dc5-102">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="15dc5-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="15dc5-103">Per altre informazioni sui contratti dati e i tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="15dc5-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="15dc5-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="15dc5-104">system.runtime.serialization</span></span>  
<span data-ttu-id="15dc5-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15dc5-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="15dc5-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="15dc5-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15dc5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15dc5-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15dc5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="15dc5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15dc5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="15dc5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15dc5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="15dc5-110">Attributes</span></span>  
 <span data-ttu-id="15dc5-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="15dc5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15dc5-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="15dc5-112">Child Elements</span></span>  
  
|<span data-ttu-id="15dc5-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="15dc5-113">Element</span></span>|<span data-ttu-id="15dc5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15dc5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15dc5-115">\<add></span><span class="sxs-lookup"><span data-stu-id="15dc5-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="15dc5-116">Aggiunge tipi che richiedono tipi noti.</span><span class="sxs-lookup"><span data-stu-id="15dc5-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15dc5-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="15dc5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="15dc5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="15dc5-118">Element</span></span>|<span data-ttu-id="15dc5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15dc5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15dc5-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15dc5-120">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="15dc5-121">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="15dc5-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15dc5-122">Note</span><span class="sxs-lookup"><span data-stu-id="15dc5-122">Remarks</span></span>  
 <span data-ttu-id="15dc5-123">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="15dc5-123">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15dc5-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="15dc5-124">Example</span></span>  
 <span data-ttu-id="15dc5-125">Il codice XML seguente mostra i tipi dichiarati e i tipi noti aggiunti a un `DataContractSerializer` elemento.</span><span class="sxs-lookup"><span data-stu-id="15dc5-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="15dc5-126">In particolare, l'esempio illustra l'aggiunta di tre tipi.</span><span class="sxs-lookup"><span data-stu-id="15dc5-126">The example shows three types being added.</span></span> <span data-ttu-id="15dc5-127">Il primo è un tipo personalizzato denominato "Orders" che usa un tipo conosciuto denominato "Item".</span><span class="sxs-lookup"><span data-stu-id="15dc5-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="15dc5-128">Il secondo tipo dichiarato è un elenco <xref:System.Collections.Generic.List%601> che usa `Item` come tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="15dc5-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="15dc5-129">Infine, il terzo tipo dichiarato è un dizionario <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="15dc5-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="15dc5-130">Il tipo della classe <xref:System.Collections.Generic.Dictionary%602> è un tipo generico, con due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="15dc5-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="15dc5-131">Il primo rappresenta la chiave e il secondo rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="15dc5-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="15dc5-132">Nell'esempio seguente viene aggiunto un elenco <xref:System.Collections.Generic.List%601> del secondo tipo (ovvero il valore) all'elenco dei tipi noti.</span><span class="sxs-lookup"><span data-stu-id="15dc5-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="15dc5-133">È necessario usare l'attributo `index` per specificare quale parametro di tipo usare nel tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="15dc5-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="15dc5-134">In questo caso, il tipo di valore viene indicato impostando l'attributo index su "1", in quanto la raccolta è in base zero.</span><span class="sxs-lookup"><span data-stu-id="15dc5-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="15dc5-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15dc5-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="15dc5-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15dc5-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="15dc5-137">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="15dc5-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="15dc5-138">\<add></span><span class="sxs-lookup"><span data-stu-id="15dc5-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
