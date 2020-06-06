---
title: <dataContractSerializer>di <System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398088"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="77df8-102">\<dataContractSerializer> di \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="77df8-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="77df8-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="77df8-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="77df8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77df8-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77df8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77df8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="77df8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77df8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77df8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="77df8-107">Attributes</span></span>  
  
|<span data-ttu-id="77df8-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="77df8-108">Element</span></span>|<span data-ttu-id="77df8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77df8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77df8-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="77df8-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="77df8-111">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="77df8-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="77df8-112">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="77df8-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="77df8-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="77df8-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="77df8-114">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="77df8-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="77df8-115">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="77df8-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77df8-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77df8-116">Child Elements</span></span>  
  
|<span data-ttu-id="77df8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="77df8-117">Element</span></span>|<span data-ttu-id="77df8-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77df8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="77df8-119">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="77df8-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="77df8-120">Per ulteriori informazioni sui contratti dati e sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="77df8-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77df8-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77df8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="77df8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="77df8-122">Element</span></span>|<span data-ttu-id="77df8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77df8-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="77df8-124">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="77df8-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77df8-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="77df8-125">Remarks</span></span>  
 <span data-ttu-id="77df8-126">Per ulteriori informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="77df8-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77df8-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="77df8-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="77df8-128">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="77df8-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
