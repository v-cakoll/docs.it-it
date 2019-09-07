---
title: <dataContractSerializer>di < System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398088"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="604a2-102">\<> DataContractSerializer di \<System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="604a2-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="604a2-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="604a2-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="604a2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="604a2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="604a2-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="604a2-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="604a2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="604a2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604a2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="604a2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="604a2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="604a2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="604a2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="604a2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="604a2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="604a2-110">Attributes</span></span>  
  
|<span data-ttu-id="604a2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="604a2-111">Element</span></span>|<span data-ttu-id="604a2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="604a2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="604a2-113">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="604a2-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="604a2-114">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="604a2-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="604a2-115">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="604a2-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="604a2-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="604a2-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="604a2-117">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="604a2-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="604a2-118">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="604a2-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="604a2-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="604a2-119">Child Elements</span></span>  
  
|<span data-ttu-id="604a2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="604a2-120">Element</span></span>|<span data-ttu-id="604a2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="604a2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="604a2-122">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="604a2-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="604a2-123">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="604a2-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="604a2-124">Per ulteriori informazioni sui contratti dati e sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="604a2-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="604a2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="604a2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="604a2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="604a2-126">Element</span></span>|<span data-ttu-id="604a2-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="604a2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="604a2-128">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="604a2-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="604a2-129">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="604a2-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="604a2-130">Note</span><span class="sxs-lookup"><span data-stu-id="604a2-130">Remarks</span></span>  
 <span data-ttu-id="604a2-131">Per ulteriori informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="604a2-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604a2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="604a2-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="604a2-133">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="604a2-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
