---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: a024ca89bd766681f25b992f1d2c66a92e3b31b7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150201"
---
# <a name="datacontractserializer"></a><span data-ttu-id="d3183-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="d3183-102">dataContractSerializer</span></span>
<span data-ttu-id="d3183-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d3183-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d3183-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d3183-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3183-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d3183-105">\<behaviors></span></span>  
<span data-ttu-id="d3183-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d3183-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d3183-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="d3183-107">\<behavior></span></span>  
<span data-ttu-id="d3183-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="d3183-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3183-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3183-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3183-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d3183-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d3183-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d3183-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3183-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d3183-112">Attributes</span></span>  
  
|<span data-ttu-id="d3183-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3183-113">Element</span></span>|<span data-ttu-id="d3183-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3183-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3183-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d3183-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d3183-116">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.</span><span class="sxs-lookup"><span data-stu-id="d3183-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="d3183-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d3183-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d3183-118">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="d3183-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3183-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d3183-119">Child Elements</span></span>  
 <span data-ttu-id="d3183-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d3183-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3183-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d3183-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d3183-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3183-122">Element</span></span>|<span data-ttu-id="d3183-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3183-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3183-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d3183-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d3183-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d3183-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3183-126">Note</span><span class="sxs-lookup"><span data-stu-id="d3183-126">Remarks</span></span>  
 <span data-ttu-id="d3183-127">Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d3183-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d3183-128">L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3183-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="d3183-129">In caso contrario, il comportamento risultante è indefinito.</span><span class="sxs-lookup"><span data-stu-id="d3183-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3183-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3183-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="d3183-131">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="d3183-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="d3183-132">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d3183-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
