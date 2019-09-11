---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854809"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="d238e-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="d238e-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="d238e-102">Questo elemento di configurazione definisce un endpoint standard con un'associazione di [ \<> WebHttpBinding](webhttpbinding.md) fissa che aggiunge automaticamente il [ \<comportamento di > enableWebScript](enablewebscript.md) .</span><span class="sxs-lookup"><span data-stu-id="d238e-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="d238e-103">Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d238e-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="d238e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d238e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d238e-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d238e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d238e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="d238e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="d238e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webScriptEndpoint**</span><span class="sxs-lookup"><span data-stu-id="d238e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d238e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d238e-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d238e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d238e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d238e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d238e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d238e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d238e-111">Attributes</span></span>  
  
|<span data-ttu-id="d238e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d238e-112">Attribute</span></span>|<span data-ttu-id="d238e-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d238e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d238e-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="d238e-114">webEndpointType</span></span>|<span data-ttu-id="d238e-115">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d238e-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d238e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d238e-116">Child Elements</span></span>  
 <span data-ttu-id="d238e-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d238e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d238e-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d238e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d238e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d238e-119">Element</span></span>|<span data-ttu-id="d238e-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d238e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d238e-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d238e-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d238e-122">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="d238e-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d238e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d238e-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
