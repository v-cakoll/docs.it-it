---
title: '&lt;Servizi&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 789fc52f628174ef61a9c7169cb0cae0f1ba8e31
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicesgt"></a><span data-ttu-id="4f20c-102">&lt;Servizi&gt;</span><span class="sxs-lookup"><span data-stu-id="4f20c-102">&lt;services&gt;</span></span>
<span data-ttu-id="4f20c-103">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f20c-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="4f20c-104">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="4f20c-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="4f20c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4f20c-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f20c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f20c-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f20c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f20c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4f20c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f20c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f20c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f20c-109">Attributes</span></span>  
 <span data-ttu-id="4f20c-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="4f20c-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f20c-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f20c-111">Child Elements</span></span>  
  
|<span data-ttu-id="4f20c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f20c-112">Element</span></span>|<span data-ttu-id="4f20c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f20c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f20c-114">\<service></span><span class="sxs-lookup"><span data-stu-id="4f20c-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="4f20c-115">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="4f20c-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f20c-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f20c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4f20c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f20c-117">Element</span></span>|<span data-ttu-id="4f20c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f20c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f20c-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f20c-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="4f20c-120">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4f20c-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f20c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f20c-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
