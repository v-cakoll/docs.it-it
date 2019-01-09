---
title: '&lt;dataContractSerializer&gt; di &lt;system.runtime.serialization&gt;'
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: f31dd8479f3bd6b36915b3ff00ff53babe3c0248
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150175"
---
# <a name="ltdatacontractserializergt-of-ltsystemruntimeserializationgt"></a><span data-ttu-id="efeb6-102">&lt;dataContractSerializer&gt; di &lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="efeb6-102">&lt;dataContractSerializer&gt; of &lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="efeb6-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="efeb6-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="efeb6-104">\<Serialization ></span><span class="sxs-lookup"><span data-stu-id="efeb6-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="efeb6-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="efeb6-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efeb6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efeb6-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efeb6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="efeb6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="efeb6-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="efeb6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efeb6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="efeb6-109">Attributes</span></span>  
  
|<span data-ttu-id="efeb6-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="efeb6-110">Element</span></span>|<span data-ttu-id="efeb6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efeb6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efeb6-112">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="efeb6-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="efeb6-113">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="efeb6-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="efeb6-114">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="efeb6-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="efeb6-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="efeb6-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="efeb6-116">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="efeb6-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="efeb6-117">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="efeb6-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efeb6-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="efeb6-118">Child Elements</span></span>  
  
|<span data-ttu-id="efeb6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="efeb6-119">Element</span></span>|<span data-ttu-id="efeb6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efeb6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efeb6-121">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="efeb6-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="efeb6-122">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="efeb6-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="efeb6-123">Per altre informazioni sui contratti dati e i tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="efeb6-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efeb6-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="efeb6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="efeb6-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="efeb6-125">Element</span></span>|<span data-ttu-id="efeb6-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efeb6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efeb6-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="efeb6-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="efeb6-128">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="efeb6-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efeb6-129">Note</span><span class="sxs-lookup"><span data-stu-id="efeb6-129">Remarks</span></span>  
 <span data-ttu-id="efeb6-130">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="efeb6-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efeb6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efeb6-131">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 [<span data-ttu-id="efeb6-132">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="efeb6-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
