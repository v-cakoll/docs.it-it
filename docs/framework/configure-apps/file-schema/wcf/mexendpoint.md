---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855106"
---
# <a name="mexendpoint"></a><span data-ttu-id="59ae3-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="59ae3-101">\<mexEndpoint></span></span>
<span data-ttu-id="59ae3-102">Questo elemento di configurazione definisce un endpoint standard con un contratto IMetadataExchange fisso.</span><span class="sxs-lookup"><span data-stu-id="59ae3-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="59ae3-103">Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="59ae3-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="59ae3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59ae3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59ae3-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="59ae3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="59ae3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="59ae3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="59ae3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> mexEndpoint**</span><span class="sxs-lookup"><span data-stu-id="59ae3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ae3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59ae3-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59ae3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59ae3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59ae3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59ae3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59ae3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="59ae3-111">Attributes</span></span>  
  
|<span data-ttu-id="59ae3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="59ae3-112">Attribute</span></span>|<span data-ttu-id="59ae3-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="59ae3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59ae3-114">name</span><span class="sxs-lookup"><span data-stu-id="59ae3-114">name</span></span>|<span data-ttu-id="59ae3-115">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="59ae3-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="59ae3-116">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="59ae3-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59ae3-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59ae3-117">Child Elements</span></span>  
 <span data-ttu-id="59ae3-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="59ae3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59ae3-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59ae3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="59ae3-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="59ae3-120">Element</span></span>|<span data-ttu-id="59ae3-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59ae3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59ae3-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="59ae3-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="59ae3-123">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="59ae3-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
