---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a64f5ae4573efbd8c0f7d622e6b94b7786585bb1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="ae199-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="ae199-102">dataContractSerializer</span></span>
<span data-ttu-id="ae199-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ae199-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ae199-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ae199-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae199-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ae199-105">\<behaviors></span></span>  
<span data-ttu-id="ae199-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ae199-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ae199-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ae199-107">\<behavior></span></span>  
<span data-ttu-id="ae199-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="ae199-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae199-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae199-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae199-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae199-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ae199-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae199-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae199-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae199-112">Attributes</span></span>  
  
|<span data-ttu-id="ae199-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae199-113">Element</span></span>|<span data-ttu-id="ae199-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae199-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae199-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="ae199-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="ae199-116">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.</span><span class="sxs-lookup"><span data-stu-id="ae199-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="ae199-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="ae199-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="ae199-118">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="ae199-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae199-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae199-119">Child Elements</span></span>  
 <span data-ttu-id="ae199-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae199-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae199-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae199-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ae199-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae199-122">Element</span></span>|<span data-ttu-id="ae199-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae199-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae199-124">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ae199-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ae199-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ae199-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae199-126">Note</span><span class="sxs-lookup"><span data-stu-id="ae199-126">Remarks</span></span>  
 <span data-ttu-id="ae199-127">Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ae199-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ae199-128">L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ae199-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="ae199-129">In caso contrario, il comportamento risultante è indefinito.</span><span class="sxs-lookup"><span data-stu-id="ae199-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae199-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae199-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="ae199-131">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="ae199-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="ae199-132">Trasferimento dei dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="ae199-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
