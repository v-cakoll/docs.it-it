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
ms.workload: dotnet
ms.openlocfilehash: 7177c62af8501258ad8709bff88cb85488b56727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lthostgt"></a><span data-ttu-id="b707b-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="b707b-102">&lt;host&gt;</span></span>
<span data-ttu-id="b707b-103">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="b707b-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="b707b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b707b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b707b-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="b707b-105">\<services></span></span>  
<span data-ttu-id="b707b-106">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="b707b-106">\<service></span></span>  
<span data-ttu-id="b707b-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="b707b-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b707b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b707b-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="b707b-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b707b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b707b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b707b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b707b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b707b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b707b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b707b-112">Attributes</span></span>  
 <span data-ttu-id="b707b-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b707b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b707b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b707b-114">Child Elements</span></span>  
  
|<span data-ttu-id="b707b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b707b-115">Element</span></span>|<span data-ttu-id="b707b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b707b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b707b-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="b707b-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="b707b-118">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="b707b-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="b707b-119">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="b707b-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="b707b-120">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="b707b-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b707b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b707b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b707b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b707b-122">Element</span></span>|<span data-ttu-id="b707b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b707b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b707b-124">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="b707b-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="b707b-125">Specifica le impostazioni di un servizio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b707b-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b707b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b707b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="b707b-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="b707b-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
