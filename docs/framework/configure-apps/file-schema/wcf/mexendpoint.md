---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772476"
---
# <a name="mexendpoint"></a><span data-ttu-id="16f4c-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="16f4c-101">\<mexEndpoint></span></span>
<span data-ttu-id="16f4c-102">Questo elemento di configurazione definisce un endpoint standard con un contratto IMetadataExchange fisso.</span><span class="sxs-lookup"><span data-stu-id="16f4c-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="16f4c-103">Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="16f4c-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="16f4c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16f4c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="16f4c-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="16f4c-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f4c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16f4c-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16f4c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="16f4c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="16f4c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="16f4c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16f4c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="16f4c-109">Attributes</span></span>  
  
|<span data-ttu-id="16f4c-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="16f4c-110">Attribute</span></span>|<span data-ttu-id="16f4c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16f4c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16f4c-112">name</span><span class="sxs-lookup"><span data-stu-id="16f4c-112">name</span></span>|<span data-ttu-id="16f4c-113">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="16f4c-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="16f4c-114">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="16f4c-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16f4c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="16f4c-115">Child Elements</span></span>  
 <span data-ttu-id="16f4c-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="16f4c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16f4c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="16f4c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="16f4c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="16f4c-118">Element</span></span>|<span data-ttu-id="16f4c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16f4c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16f4c-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="16f4c-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="16f4c-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="16f4c-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
