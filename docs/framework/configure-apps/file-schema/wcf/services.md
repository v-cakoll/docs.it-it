---
title: '&lt;servizi&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca55770da8da0fe91a12aeb5fa72e61d6dcd67ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="23c35-102">&lt;servizi&gt;</span><span class="sxs-lookup"><span data-stu-id="23c35-102">&lt;services&gt;</span></span>
<span data-ttu-id="23c35-103">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23c35-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="23c35-104">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="23c35-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="23c35-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="23c35-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c35-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23c35-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23c35-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="23c35-107">Attributes and Elements</span></span>  
 <span data-ttu-id="23c35-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="23c35-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23c35-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="23c35-109">Attributes</span></span>  
 <span data-ttu-id="23c35-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="23c35-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23c35-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="23c35-111">Child Elements</span></span>  
  
|<span data-ttu-id="23c35-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="23c35-112">Element</span></span>|<span data-ttu-id="23c35-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c35-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23c35-114">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="23c35-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="23c35-115">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="23c35-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23c35-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="23c35-116">Parent Elements</span></span>  
  
|<span data-ttu-id="23c35-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="23c35-117">Element</span></span>|<span data-ttu-id="23c35-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c35-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23c35-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="23c35-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="23c35-120">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="23c35-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23c35-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23c35-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
