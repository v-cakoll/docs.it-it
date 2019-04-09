---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8ba16d9cc30b07d3e6b0924e6013ec01443867d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139048"
---
# <a name="datacontractserializer"></a><span data-ttu-id="62284-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="62284-102">dataContractSerializer</span></span>
<span data-ttu-id="62284-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="62284-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="62284-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62284-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62284-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="62284-105">\<behaviors></span></span>  
<span data-ttu-id="62284-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="62284-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="62284-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="62284-107">\<behavior></span></span>  
<span data-ttu-id="62284-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="62284-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62284-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62284-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62284-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="62284-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62284-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="62284-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62284-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="62284-112">Attributes</span></span>  
  
|<span data-ttu-id="62284-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="62284-113">Element</span></span>|<span data-ttu-id="62284-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62284-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62284-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="62284-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="62284-116">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.</span><span class="sxs-lookup"><span data-stu-id="62284-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="62284-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="62284-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="62284-118">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="62284-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62284-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62284-119">Child Elements</span></span>  
 <span data-ttu-id="62284-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="62284-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62284-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="62284-121">Parent Elements</span></span>  
  
|<span data-ttu-id="62284-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="62284-122">Element</span></span>|<span data-ttu-id="62284-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62284-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62284-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="62284-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="62284-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="62284-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62284-126">Note</span><span class="sxs-lookup"><span data-stu-id="62284-126">Remarks</span></span>  
 <span data-ttu-id="62284-127">Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="62284-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="62284-128">L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="62284-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="62284-129">In caso contrario, il comportamento risultante è indefinito.</span><span class="sxs-lookup"><span data-stu-id="62284-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62284-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62284-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="62284-131">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="62284-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="62284-132">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="62284-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
