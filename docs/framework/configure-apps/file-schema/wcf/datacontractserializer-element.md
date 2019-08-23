---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925917"
---
# <a name="datacontractserializer"></a><span data-ttu-id="d515d-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="d515d-101">\<dataContractSerializer></span></span>
<span data-ttu-id="d515d-102">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d515d-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="d515d-103">Questo elemento è presente in due gerarchie diverse</span><span class="sxs-lookup"><span data-stu-id="d515d-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="d515d-104">e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="d515d-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="d515d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d515d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d515d-106">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d515d-106">\<behaviors></span></span>  
<span data-ttu-id="d515d-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d515d-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="d515d-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="d515d-108">\<behavior></span></span>  
<span data-ttu-id="d515d-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="d515d-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d515d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d515d-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d515d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d515d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d515d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d515d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d515d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d515d-113">Attributes</span></span>  
  
|<span data-ttu-id="d515d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d515d-114">Element</span></span>|<span data-ttu-id="d515d-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d515d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d515d-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d515d-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d515d-117">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="d515d-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="d515d-118">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="d515d-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="d515d-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d515d-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d515d-120">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="d515d-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="d515d-121">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="d515d-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d515d-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d515d-122">Child Elements</span></span>  
 <span data-ttu-id="d515d-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d515d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d515d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d515d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d515d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d515d-125">Element</span></span>|<span data-ttu-id="d515d-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d515d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d515d-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d515d-127">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="d515d-128">Raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="d515d-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="d515d-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d515d-129">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="d515d-130">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d515d-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d515d-131">Note</span><span class="sxs-lookup"><span data-stu-id="d515d-131">Remarks</span></span>  
 <span data-ttu-id="d515d-132">Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui si verifica \<l'elemento X509Extension >.</span><span class="sxs-lookup"><span data-stu-id="d515d-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="d515d-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d515d-133">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="d515d-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="d515d-134">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="d515d-135">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d515d-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d515d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d515d-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="d515d-137">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="d515d-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="d515d-138">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d515d-138">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
