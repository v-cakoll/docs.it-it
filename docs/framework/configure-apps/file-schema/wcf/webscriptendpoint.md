---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105651"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="dce44-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="dce44-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="dce44-102">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="dce44-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="dce44-103">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dce44-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="dce44-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dce44-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dce44-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dce44-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce44-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dce44-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dce44-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dce44-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dce44-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dce44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dce44-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="dce44-109">Attributes</span></span>  
  
|<span data-ttu-id="dce44-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="dce44-110">Attribute</span></span>|<span data-ttu-id="dce44-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dce44-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dce44-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="dce44-112">webEndpointType</span></span>|<span data-ttu-id="dce44-113">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dce44-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dce44-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dce44-114">Child Elements</span></span>  
 <span data-ttu-id="dce44-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dce44-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dce44-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dce44-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dce44-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dce44-117">Element</span></span>|<span data-ttu-id="dce44-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dce44-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dce44-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dce44-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="dce44-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="dce44-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dce44-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce44-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
