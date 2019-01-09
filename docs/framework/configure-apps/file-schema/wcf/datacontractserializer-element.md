---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: c79c8e8db2a4ea4526000bcbe336d1e664f9c4c2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150955"
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="38dc1-102">&lt;DataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="38dc1-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="38dc1-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="38dc1-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="38dc1-104">Questo elemento è presente in due gerarchie diverse</span><span class="sxs-lookup"><span data-stu-id="38dc1-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="38dc1-105">e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="38dc1-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="38dc1-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="38dc1-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="38dc1-107">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="38dc1-107">\<behaviors></span></span>  
<span data-ttu-id="38dc1-108">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="38dc1-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="38dc1-109">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="38dc1-109">\<behavior></span></span>  
<span data-ttu-id="38dc1-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="38dc1-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38dc1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38dc1-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38dc1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="38dc1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="38dc1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="38dc1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38dc1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="38dc1-114">Attributes</span></span>  
  
|<span data-ttu-id="38dc1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="38dc1-115">Element</span></span>|<span data-ttu-id="38dc1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38dc1-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38dc1-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="38dc1-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="38dc1-118">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="38dc1-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="38dc1-119">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="38dc1-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="38dc1-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="38dc1-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="38dc1-121">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="38dc1-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="38dc1-122">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="38dc1-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38dc1-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="38dc1-123">Child Elements</span></span>  
 <span data-ttu-id="38dc1-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="38dc1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38dc1-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="38dc1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="38dc1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="38dc1-126">Element</span></span>|<span data-ttu-id="38dc1-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38dc1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38dc1-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="38dc1-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="38dc1-129">Raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="38dc1-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="38dc1-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="38dc1-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="38dc1-131">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="38dc1-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38dc1-132">Note</span><span class="sxs-lookup"><span data-stu-id="38dc1-132">Remarks</span></span>  
 <span data-ttu-id="38dc1-133">Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui il \<X509Extension > viene generato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="38dc1-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="38dc1-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="38dc1-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="38dc1-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="38dc1-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="38dc1-136">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="38dc1-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38dc1-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38dc1-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="38dc1-138">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="38dc1-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="38dc1-139">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="38dc1-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
