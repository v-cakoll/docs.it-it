---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 4dc425fa97eaf99664f0d9bbbbc851c462cbf373
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274963"
---
# <a name="services"></a><span data-ttu-id="bfa3e-101">\<services></span><span class="sxs-lookup"><span data-stu-id="bfa3e-101">\<services></span></span>
<span data-ttu-id="bfa3e-102">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bfa3e-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="bfa3e-103">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="bfa3e-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="bfa3e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bfa3e-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa3e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfa3e-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfa3e-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bfa3e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="bfa3e-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bfa3e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfa3e-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="bfa3e-108">Attributes</span></span>  
 <span data-ttu-id="bfa3e-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="bfa3e-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfa3e-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bfa3e-110">Child Elements</span></span>  
  
|<span data-ttu-id="bfa3e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfa3e-111">Element</span></span>|<span data-ttu-id="bfa3e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa3e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfa3e-113">\<service></span><span class="sxs-lookup"><span data-stu-id="bfa3e-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="bfa3e-114">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="bfa3e-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfa3e-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bfa3e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bfa3e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfa3e-116">Element</span></span>|<span data-ttu-id="bfa3e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa3e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfa3e-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bfa3e-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="bfa3e-119">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bfa3e-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfa3e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa3e-120">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServicesSection>
