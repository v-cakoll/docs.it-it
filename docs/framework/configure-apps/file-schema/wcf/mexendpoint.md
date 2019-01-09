---
title: '&lt;mexEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 4e2fb4946ee68b3cbd5bd6bfbafe6bb5e9c9106f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149150"
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="6b098-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="6b098-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="6b098-103">Questo elemento di configurazione definisce un endpoint standard con un contratto IMetadataExchange fisso.</span><span class="sxs-lookup"><span data-stu-id="6b098-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="6b098-104">Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6b098-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="6b098-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6b098-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b098-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6b098-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b098-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b098-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b098-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6b098-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b098-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6b098-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b098-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6b098-110">Attributes</span></span>  
  
|<span data-ttu-id="6b098-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6b098-111">Attribute</span></span>|<span data-ttu-id="6b098-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b098-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b098-113">name</span><span class="sxs-lookup"><span data-stu-id="6b098-113">name</span></span>|<span data-ttu-id="6b098-114">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="6b098-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="6b098-115">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="6b098-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b098-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6b098-116">Child Elements</span></span>  
 <span data-ttu-id="6b098-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6b098-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b098-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6b098-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6b098-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b098-119">Element</span></span>|<span data-ttu-id="6b098-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b098-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b098-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6b098-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6b098-122">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="6b098-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
