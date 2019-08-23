---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940412"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="970e6-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="970e6-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="970e6-102">Questo elemento di configurazione definisce un endpoint standard con un'associazione di [ \<> WebHttpBinding](webhttpbinding.md) fissa che aggiunge automaticamente il [ \<comportamento di > enableWebScript](enablewebscript.md) .</span><span class="sxs-lookup"><span data-stu-id="970e6-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="970e6-103">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="970e6-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="970e6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="970e6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="970e6-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="970e6-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970e6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="970e6-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="970e6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="970e6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="970e6-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="970e6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="970e6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="970e6-109">Attributes</span></span>  
  
|<span data-ttu-id="970e6-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="970e6-110">Attribute</span></span>|<span data-ttu-id="970e6-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="970e6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="970e6-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="970e6-112">webEndpointType</span></span>|<span data-ttu-id="970e6-113">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="970e6-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="970e6-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="970e6-114">Child Elements</span></span>  
 <span data-ttu-id="970e6-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="970e6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="970e6-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="970e6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="970e6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="970e6-117">Element</span></span>|<span data-ttu-id="970e6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="970e6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="970e6-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="970e6-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="970e6-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="970e6-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="970e6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970e6-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
