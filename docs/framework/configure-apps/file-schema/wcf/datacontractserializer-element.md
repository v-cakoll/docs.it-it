---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400443"
---
# <a name="datacontractserializer"></a><span data-ttu-id="75398-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="75398-101">\<dataContractSerializer></span></span>
<span data-ttu-id="75398-102">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="75398-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="75398-103">Questo elemento è presente in due gerarchie diverse</span><span class="sxs-lookup"><span data-stu-id="75398-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="75398-104">e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="75398-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="75398-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75398-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75398-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="75398-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="75398-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="75398-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="75398-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="75398-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="75398-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="75398-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="75398-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="75398-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75398-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75398-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75398-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75398-112">Attributes and Elements</span></span>  
 <span data-ttu-id="75398-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75398-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75398-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="75398-114">Attributes</span></span>  
  
|<span data-ttu-id="75398-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="75398-115">Element</span></span>|<span data-ttu-id="75398-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75398-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75398-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="75398-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="75398-118">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati.</span><span class="sxs-lookup"><span data-stu-id="75398-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="75398-119">Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="75398-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="75398-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="75398-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="75398-121">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="75398-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="75398-122">Questo attributo è pari a 65.536.</span><span class="sxs-lookup"><span data-stu-id="75398-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75398-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75398-123">Child Elements</span></span>  
 <span data-ttu-id="75398-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="75398-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75398-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75398-125">Parent Elements</span></span>  
  
|<span data-ttu-id="75398-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="75398-126">Element</span></span>|<span data-ttu-id="75398-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="75398-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75398-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="75398-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="75398-129">Raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="75398-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="75398-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="75398-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="75398-131">Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="75398-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75398-132">Note</span><span class="sxs-lookup"><span data-stu-id="75398-132">Remarks</span></span>  
 <span data-ttu-id="75398-133">Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui si verifica \<l'elemento X509Extension >.</span><span class="sxs-lookup"><span data-stu-id="75398-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="75398-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="75398-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="75398-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="75398-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="75398-136">Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="75398-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75398-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75398-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="75398-138">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="75398-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="75398-139">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="75398-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
