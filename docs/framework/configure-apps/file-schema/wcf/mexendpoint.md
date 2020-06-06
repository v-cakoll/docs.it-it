---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855106"
---
# \<mexEndpoint>
<span data-ttu-id="575cd-101">Questo elemento di configurazione definisce un endpoint standard con un contratto IMetadataExchange fisso.</span><span class="sxs-lookup"><span data-stu-id="575cd-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="575cd-102">Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="575cd-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="575cd-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575cd-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="575cd-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="575cd-104">Attributes and Elements</span></span>  
 <span data-ttu-id="575cd-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="575cd-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="575cd-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="575cd-106">Attributes</span></span>  
  
|<span data-ttu-id="575cd-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="575cd-107">Attribute</span></span>|<span data-ttu-id="575cd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575cd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="575cd-109">name</span><span class="sxs-lookup"><span data-stu-id="575cd-109">name</span></span>|<span data-ttu-id="575cd-110">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="575cd-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="575cd-111">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="575cd-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="575cd-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="575cd-112">Child Elements</span></span>  
 <span data-ttu-id="575cd-113">No.</span><span class="sxs-lookup"><span data-stu-id="575cd-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="575cd-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="575cd-114">Parent Elements</span></span>  
  
|<span data-ttu-id="575cd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="575cd-115">Element</span></span>|<span data-ttu-id="575cd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575cd-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="575cd-117">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="575cd-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
