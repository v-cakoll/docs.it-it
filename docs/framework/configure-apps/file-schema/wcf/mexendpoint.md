---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75886c08d3e358d4ed6d3d3048594ef28f06a7af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="326b9-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="326b9-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="326b9-103">Questo elemento di configurazione definisce un endpoint standard con un contratto IMetadataExchange fisso.</span><span class="sxs-lookup"><span data-stu-id="326b9-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="326b9-104">Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="326b9-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="326b9-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="326b9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="326b9-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="326b9-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326b9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="326b9-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="326b9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="326b9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="326b9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="326b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="326b9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="326b9-110">Attributes</span></span>  
  
|<span data-ttu-id="326b9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="326b9-111">Attribute</span></span>|<span data-ttu-id="326b9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="326b9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="326b9-113">name</span><span class="sxs-lookup"><span data-stu-id="326b9-113">name</span></span>|<span data-ttu-id="326b9-114">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="326b9-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="326b9-115">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="326b9-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="326b9-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="326b9-116">Child Elements</span></span>  
 <span data-ttu-id="326b9-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="326b9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="326b9-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="326b9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="326b9-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="326b9-119">Element</span></span>|<span data-ttu-id="326b9-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="326b9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="326b9-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="326b9-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="326b9-122">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="326b9-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
