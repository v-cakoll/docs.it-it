---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400439"
---
# <a name="datacontractserializer"></a><span data-ttu-id="107b4-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="107b4-102">dataContractSerializer</span></span>
<span data-ttu-id="107b4-103">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="107b4-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="107b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="107b4-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="107b4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="107b4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="107b4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="107b4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="107b4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="107b4-107">Attributes</span></span>  
  
|<span data-ttu-id="107b4-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="107b4-108">Element</span></span>|<span data-ttu-id="107b4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107b4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="107b4-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="107b4-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="107b4-111">Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.</span><span class="sxs-lookup"><span data-stu-id="107b4-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="107b4-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="107b4-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="107b4-113">Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="107b4-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="107b4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="107b4-114">Child Elements</span></span>  
 <span data-ttu-id="107b4-115">No.</span><span class="sxs-lookup"><span data-stu-id="107b4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="107b4-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="107b4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="107b4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="107b4-117">Element</span></span>|<span data-ttu-id="107b4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107b4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="107b4-119">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="107b4-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="107b4-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="107b4-120">Remarks</span></span>  
 <span data-ttu-id="107b4-121">Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="107b4-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="107b4-122">L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="107b4-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="107b4-123">In caso contrario, il comportamento risultante è indefinito.</span><span class="sxs-lookup"><span data-stu-id="107b4-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107b4-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="107b4-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="107b4-125">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="107b4-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="107b4-126">Trasferimento dati e serializzazione</span><span class="sxs-lookup"><span data-stu-id="107b4-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
