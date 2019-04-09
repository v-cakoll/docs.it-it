---
title: <dataContractSerializer> of <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115362"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="91709-102">\<dataContractSerializer> of \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="91709-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="91709-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="91709-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="91709-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="91709-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="91709-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="91709-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91709-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91709-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91709-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91709-107">Attributes and Elements</span></span>  
 <span data-ttu-id="91709-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91709-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91709-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="91709-109">Attributes</span></span>  
  
|<span data-ttu-id="91709-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="91709-110">Element</span></span>|<span data-ttu-id="91709-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91709-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91709-112">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="91709-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="91709-113">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="91709-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="91709-114">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="91709-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="91709-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="91709-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="91709-116">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="91709-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="91709-117">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="91709-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91709-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91709-118">Child Elements</span></span>  
  
|<span data-ttu-id="91709-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="91709-119">Element</span></span>|<span data-ttu-id="91709-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91709-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91709-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="91709-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="91709-122">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="91709-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="91709-123">Per altre informazioni sui contratti dati e i tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="91709-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91709-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91709-124">Parent Elements</span></span>  
  
|<span data-ttu-id="91709-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="91709-125">Element</span></span>|<span data-ttu-id="91709-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91709-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91709-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="91709-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="91709-128">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="91709-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91709-129">Note</span><span class="sxs-lookup"><span data-stu-id="91709-129">Remarks</span></span>  
 <span data-ttu-id="91709-130">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="91709-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91709-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91709-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="91709-132">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="91709-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
