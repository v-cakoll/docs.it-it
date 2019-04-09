---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116389"
---
# <a name="datacontractserializer"></a><span data-ttu-id="ae69d-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ae69d-101">\<dataContractSerializer></span></span>
<span data-ttu-id="ae69d-102">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ae69d-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="ae69d-103">Questo elemento è presente in due gerarchie diverse</span><span class="sxs-lookup"><span data-stu-id="ae69d-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="ae69d-104">e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="ae69d-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="ae69d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae69d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae69d-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ae69d-106">\<behaviors></span></span>  
<span data-ttu-id="ae69d-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ae69d-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="ae69d-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ae69d-108">\<behavior></span></span>  
<span data-ttu-id="ae69d-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ae69d-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae69d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae69d-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae69d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae69d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ae69d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae69d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae69d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae69d-113">Attributes</span></span>  
  
|<span data-ttu-id="ae69d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae69d-114">Element</span></span>|<span data-ttu-id="ae69d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae69d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae69d-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="ae69d-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="ae69d-117">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="ae69d-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="ae69d-118">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="ae69d-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="ae69d-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="ae69d-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="ae69d-120">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="ae69d-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="ae69d-121">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="ae69d-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae69d-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae69d-122">Child Elements</span></span>  
 <span data-ttu-id="ae69d-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae69d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae69d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae69d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ae69d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae69d-125">Element</span></span>|<span data-ttu-id="ae69d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae69d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae69d-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ae69d-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="ae69d-128">Raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="ae69d-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="ae69d-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ae69d-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="ae69d-130">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ae69d-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae69d-131">Note</span><span class="sxs-lookup"><span data-stu-id="ae69d-131">Remarks</span></span>  
 <span data-ttu-id="ae69d-132">Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui il \<X509Extension > viene generato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="ae69d-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="ae69d-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ae69d-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="ae69d-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ae69d-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="ae69d-135">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ae69d-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae69d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae69d-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="ae69d-137">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="ae69d-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="ae69d-138">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="ae69d-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
