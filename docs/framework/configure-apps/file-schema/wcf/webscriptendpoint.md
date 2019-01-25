---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: acafb5b6a5c4911dcf21a55cfb9e93883067e5ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566385"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="3fdc5-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="3fdc5-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="3fdc5-103">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="3fdc5-104">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="3fdc5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3fdc5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3fdc5-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3fdc5-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdc5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fdc5-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fdc5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3fdc5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3fdc5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fdc5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3fdc5-110">Attributes</span></span>  
  
|<span data-ttu-id="3fdc5-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3fdc5-111">Attribute</span></span>|<span data-ttu-id="3fdc5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fdc5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fdc5-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="3fdc5-113">webEndpointType</span></span>|<span data-ttu-id="3fdc5-114">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fdc5-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3fdc5-115">Child Elements</span></span>  
 <span data-ttu-id="3fdc5-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fdc5-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3fdc5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3fdc5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fdc5-118">Element</span></span>|<span data-ttu-id="3fdc5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fdc5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fdc5-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3fdc5-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3fdc5-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fdc5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fdc5-122">See also</span></span>
- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
