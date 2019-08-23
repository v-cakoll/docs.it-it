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
ms.openlocfilehash: cef34a8836c7b17fe9a85cac190090f42653df14
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919243"
---
# <a name="declaredtypes"></a><span data-ttu-id="ad01b-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="ad01b-101">\<declaredTypes></span></span>
<span data-ttu-id="ad01b-102">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="ad01b-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="ad01b-103">Per ulteriori informazioni sui contratti dati e sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ad01b-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="ad01b-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="ad01b-104">system.runtime.serialization</span></span>  
<span data-ttu-id="ad01b-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ad01b-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="ad01b-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="ad01b-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad01b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad01b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad01b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad01b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ad01b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad01b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad01b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad01b-110">Attributes</span></span>  
 <span data-ttu-id="ad01b-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ad01b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad01b-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad01b-112">Child Elements</span></span>  
  
|<span data-ttu-id="ad01b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad01b-113">Element</span></span>|<span data-ttu-id="ad01b-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ad01b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad01b-115">\<add></span><span class="sxs-lookup"><span data-stu-id="ad01b-115">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="ad01b-116">Aggiunge tipi che richiedono tipi noti.</span><span class="sxs-lookup"><span data-stu-id="ad01b-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad01b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad01b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ad01b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad01b-118">Element</span></span>|<span data-ttu-id="ad01b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad01b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad01b-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ad01b-120">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ad01b-121">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ad01b-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad01b-122">Note</span><span class="sxs-lookup"><span data-stu-id="ad01b-122">Remarks</span></span>  
 <span data-ttu-id="ad01b-123">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ad01b-123">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad01b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad01b-124">Example</span></span>  
 <span data-ttu-id="ad01b-125">Il codice XML seguente mostra i tipi dichiarati e i tipi `DataContractSerializer` noti aggiunti a un elemento.</span><span class="sxs-lookup"><span data-stu-id="ad01b-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="ad01b-126">In particolare, l'esempio illustra l'aggiunta di tre tipi.</span><span class="sxs-lookup"><span data-stu-id="ad01b-126">The example shows three types being added.</span></span> <span data-ttu-id="ad01b-127">Il primo è un tipo personalizzato denominato "Orders" che usa un tipo conosciuto denominato "Item".</span><span class="sxs-lookup"><span data-stu-id="ad01b-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="ad01b-128">Il secondo tipo dichiarato è un elenco <xref:System.Collections.Generic.List%601> che usa `Item` come tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="ad01b-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="ad01b-129">Infine, il terzo tipo dichiarato è un dizionario <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="ad01b-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="ad01b-130">Il tipo della classe <xref:System.Collections.Generic.Dictionary%602> è un tipo generico, con due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="ad01b-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="ad01b-131">Il primo rappresenta la chiave e il secondo rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="ad01b-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="ad01b-132">Nell'esempio seguente viene aggiunto un elenco <xref:System.Collections.Generic.List%601> del secondo tipo (ovvero il valore) all'elenco dei tipi noti.</span><span class="sxs-lookup"><span data-stu-id="ad01b-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="ad01b-133">È necessario usare l'attributo `index` per specificare quale parametro di tipo usare nel tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="ad01b-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="ad01b-134">In questo caso, il tipo di valore viene indicato impostando l'attributo index su "1", in quanto la raccolta è in base zero.</span><span class="sxs-lookup"><span data-stu-id="ad01b-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad01b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad01b-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="ad01b-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ad01b-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="ad01b-137">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="ad01b-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="ad01b-138">\<add></span><span class="sxs-lookup"><span data-stu-id="ad01b-138">\<add></span></span>](add-of-declaredtypes-element.md)
