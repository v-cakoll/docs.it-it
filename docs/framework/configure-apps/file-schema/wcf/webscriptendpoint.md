---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854809"
---
# \<webScriptEndpoint>
<span data-ttu-id="1b2d5-101">Questo elemento di configurazione definisce un endpoint standard con un' [\<webHttpBinding>](webhttpbinding.md) associazione fissa che aggiunge automaticamente il [\<enableWebScript>](enablewebscript.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="1b2d5-102">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="1b2d5-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b2d5-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b2d5-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b2d5-104">Attributes and Elements</span></span>  
 <span data-ttu-id="1b2d5-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b2d5-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b2d5-106">Attributes</span></span>  
  
|<span data-ttu-id="1b2d5-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b2d5-107">Attribute</span></span>|<span data-ttu-id="1b2d5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2d5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b2d5-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="1b2d5-109">webEndpointType</span></span>|<span data-ttu-id="1b2d5-110">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b2d5-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b2d5-111">Child Elements</span></span>  
 <span data-ttu-id="1b2d5-112">No.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b2d5-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b2d5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1b2d5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b2d5-114">Element</span></span>|<span data-ttu-id="1b2d5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2d5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="1b2d5-116">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="1b2d5-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b2d5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b2d5-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
