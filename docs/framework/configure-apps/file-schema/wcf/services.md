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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb292a62c2b042c387799164ff4cec88bd2ca482
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="2b07e-102">&lt;servizi&gt;</span><span class="sxs-lookup"><span data-stu-id="2b07e-102">&lt;services&gt;</span></span>
<span data-ttu-id="2b07e-103">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2b07e-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="2b07e-104">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="2b07e-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="2b07e-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2b07e-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b07e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b07e-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b07e-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b07e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2b07e-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b07e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b07e-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b07e-109">Attributes</span></span>  
 <span data-ttu-id="2b07e-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2b07e-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b07e-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b07e-111">Child Elements</span></span>  
  
|<span data-ttu-id="2b07e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b07e-112">Element</span></span>|<span data-ttu-id="2b07e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b07e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b07e-114">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="2b07e-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="2b07e-115">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="2b07e-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b07e-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b07e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2b07e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b07e-117">Element</span></span>|<span data-ttu-id="2b07e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b07e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b07e-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2b07e-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="2b07e-120">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2b07e-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b07e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b07e-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
