---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: beb17d4ccc39bcca30e97d4f0df47c797cde6216
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148773"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="4e8f9-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="4e8f9-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="4e8f9-103">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="4e8f9-104">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="4e8f9-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e8f9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e8f9-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4e8f9-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8f9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e8f9-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e8f9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e8f9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4e8f9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e8f9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4e8f9-110">Attributes</span></span>  
  
|<span data-ttu-id="4e8f9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4e8f9-111">Attribute</span></span>|<span data-ttu-id="4e8f9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e8f9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e8f9-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="4e8f9-113">webEndpointType</span></span>|<span data-ttu-id="4e8f9-114">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e8f9-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e8f9-115">Child Elements</span></span>  
 <span data-ttu-id="4e8f9-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e8f9-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e8f9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4e8f9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e8f9-118">Element</span></span>|<span data-ttu-id="4e8f9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e8f9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e8f9-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4e8f9-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="4e8f9-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="4e8f9-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e8f9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e8f9-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
