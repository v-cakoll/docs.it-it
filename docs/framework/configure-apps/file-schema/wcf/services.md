---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168077"
---
# <a name="services"></a><span data-ttu-id="93fab-101">\<services></span><span class="sxs-lookup"><span data-stu-id="93fab-101">\<services></span></span>
<span data-ttu-id="93fab-102">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="93fab-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="93fab-103">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="93fab-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="93fab-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93fab-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93fab-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93fab-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93fab-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93fab-106">Attributes and Elements</span></span>  
 <span data-ttu-id="93fab-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93fab-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93fab-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="93fab-108">Attributes</span></span>  
 <span data-ttu-id="93fab-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="93fab-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="93fab-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93fab-110">Child Elements</span></span>  
  
|<span data-ttu-id="93fab-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="93fab-111">Element</span></span>|<span data-ttu-id="93fab-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93fab-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93fab-113">\<service></span><span class="sxs-lookup"><span data-stu-id="93fab-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="93fab-114">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="93fab-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93fab-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93fab-115">Parent Elements</span></span>  
  
|<span data-ttu-id="93fab-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="93fab-116">Element</span></span>|<span data-ttu-id="93fab-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93fab-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93fab-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="93fab-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="93fab-119">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="93fab-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93fab-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93fab-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
