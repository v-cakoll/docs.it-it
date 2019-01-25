---
title: '&lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 7b26224f1217e7f73a529c082c2c9272ec189a5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573257"
---
# <a name="ltservicesgt"></a><span data-ttu-id="6c3fe-102">&lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="6c3fe-102">&lt;services&gt;</span></span>
<span data-ttu-id="6c3fe-103">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6c3fe-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="6c3fe-104">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="6c3fe-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="6c3fe-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6c3fe-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3fe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c3fe-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c3fe-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6c3fe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6c3fe-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6c3fe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c3fe-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="6c3fe-109">Attributes</span></span>  
 <span data-ttu-id="6c3fe-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="6c3fe-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c3fe-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6c3fe-111">Child Elements</span></span>  
  
|<span data-ttu-id="6c3fe-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c3fe-112">Element</span></span>|<span data-ttu-id="6c3fe-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c3fe-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c3fe-114">\<service></span><span class="sxs-lookup"><span data-stu-id="6c3fe-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="6c3fe-115">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="6c3fe-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c3fe-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6c3fe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6c3fe-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c3fe-117">Element</span></span>|<span data-ttu-id="6c3fe-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c3fe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c3fe-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c3fe-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="6c3fe-120">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6c3fe-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c3fe-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c3fe-121">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServicesSection>
