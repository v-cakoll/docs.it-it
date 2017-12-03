---
title: '&lt;host&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d498190e7d7c3a6e879c50324e3b973f0f8e8fa6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="lthostgt"></a><span data-ttu-id="8aa56-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="8aa56-102">&lt;host&gt;</span></span>
<span data-ttu-id="8aa56-103">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8aa56-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="8aa56-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8aa56-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8aa56-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="8aa56-105">\<services></span></span>  
<span data-ttu-id="8aa56-106">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="8aa56-106">\<service></span></span>  
<span data-ttu-id="8aa56-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="8aa56-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa56-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8aa56-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="8aa56-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8aa56-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aa56-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8aa56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8aa56-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8aa56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aa56-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8aa56-112">Attributes</span></span>  
 <span data-ttu-id="8aa56-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8aa56-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8aa56-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8aa56-114">Child Elements</span></span>  
  
|<span data-ttu-id="8aa56-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8aa56-115">Element</span></span>|<span data-ttu-id="8aa56-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aa56-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aa56-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="8aa56-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="8aa56-118">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8aa56-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="8aa56-119">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="8aa56-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="8aa56-120">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8aa56-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8aa56-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8aa56-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8aa56-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8aa56-122">Element</span></span>|<span data-ttu-id="8aa56-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aa56-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aa56-124">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="8aa56-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="8aa56-125">Specifica le impostazioni di un servizio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aa56-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8aa56-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aa56-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="8aa56-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="8aa56-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
