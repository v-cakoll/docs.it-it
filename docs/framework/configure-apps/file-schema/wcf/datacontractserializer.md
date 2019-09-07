---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400439"
---
# <a name="datacontractserializer"></a><span data-ttu-id="4f2ae-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="4f2ae-102">dataContractSerializer</span></span>
<span data-ttu-id="4f2ae-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="4f2ae-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f2ae-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f2ae-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f2ae-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4f2ae-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4f2ae-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4f2ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4f2ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4f2ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4f2ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4f2ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="4f2ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f2ae-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f2ae-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f2ae-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f2ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f2ae-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f2ae-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f2ae-113">Attributes</span></span>  
  
|<span data-ttu-id="4f2ae-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f2ae-114">Element</span></span>|<span data-ttu-id="4f2ae-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4f2ae-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f2ae-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="4f2ae-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="4f2ae-117">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="4f2ae-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="4f2ae-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="4f2ae-119">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f2ae-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f2ae-120">Child Elements</span></span>  
 <span data-ttu-id="4f2ae-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f2ae-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f2ae-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4f2ae-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f2ae-123">Element</span></span>|<span data-ttu-id="4f2ae-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f2ae-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f2ae-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4f2ae-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4f2ae-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f2ae-127">Note</span><span class="sxs-lookup"><span data-stu-id="4f2ae-127">Remarks</span></span>  
 <span data-ttu-id="4f2ae-128">Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="4f2ae-129">L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="4f2ae-130">In caso contrario, il comportamento risultante è indefinito.</span><span class="sxs-lookup"><span data-stu-id="4f2ae-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2ae-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f2ae-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="4f2ae-132">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="4f2ae-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="4f2ae-133">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="4f2ae-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
