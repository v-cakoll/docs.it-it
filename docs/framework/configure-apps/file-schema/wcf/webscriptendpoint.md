---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b53b7cc3ce812b72830c0ad83c5cc2b42bfc25a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755305"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="f5ea2-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="f5ea2-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="f5ea2-103">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="f5ea2-104">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="f5ea2-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f5ea2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f5ea2-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="f5ea2-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ea2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5ea2-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5ea2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5ea2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f5ea2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5ea2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5ea2-110">Attributes</span></span>  
  
|<span data-ttu-id="f5ea2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f5ea2-111">Attribute</span></span>|<span data-ttu-id="f5ea2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5ea2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5ea2-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f5ea2-113">webEndpointType</span></span>|<span data-ttu-id="f5ea2-114">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5ea2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5ea2-115">Child Elements</span></span>  
 <span data-ttu-id="f5ea2-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5ea2-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5ea2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f5ea2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5ea2-118">Element</span></span>|<span data-ttu-id="f5ea2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5ea2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5ea2-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="f5ea2-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f5ea2-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="f5ea2-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5ea2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ea2-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
