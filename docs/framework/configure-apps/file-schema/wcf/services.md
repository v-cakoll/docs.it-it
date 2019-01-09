---
title: '&lt;Servizi&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: a48bd0ac30c1a85602122b2fd9213c2aa5159e91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148097"
---
# <a name="ltservicesgt"></a><span data-ttu-id="1a6a0-102">&lt;Servizi&gt;</span><span class="sxs-lookup"><span data-stu-id="1a6a0-102">&lt;services&gt;</span></span>
<span data-ttu-id="1a6a0-103">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="1a6a0-104">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="1a6a0-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1a6a0-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a6a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a6a0-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a6a0-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1a6a0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1a6a0-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a6a0-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="1a6a0-109">Attributes</span></span>  
 <span data-ttu-id="1a6a0-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="1a6a0-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a6a0-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1a6a0-111">Child Elements</span></span>  
  
|<span data-ttu-id="1a6a0-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a6a0-112">Element</span></span>|<span data-ttu-id="1a6a0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a6a0-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a6a0-114">\<service></span><span class="sxs-lookup"><span data-stu-id="1a6a0-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="1a6a0-115">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a6a0-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1a6a0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1a6a0-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a6a0-117">Element</span></span>|<span data-ttu-id="1a6a0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a6a0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a6a0-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a6a0-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="1a6a0-120">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1a6a0-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a6a0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a6a0-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
