---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854983"
---
# \<services>
<span data-ttu-id="d40cc-101">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d40cc-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d40cc-102">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="d40cc-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="d40cc-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d40cc-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d40cc-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d40cc-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d40cc-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d40cc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d40cc-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="d40cc-106">Attributes</span></span>  
 <span data-ttu-id="d40cc-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="d40cc-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d40cc-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d40cc-108">Child Elements</span></span>  
  
|<span data-ttu-id="d40cc-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="d40cc-109">Element</span></span>|<span data-ttu-id="d40cc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d40cc-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="d40cc-111">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="d40cc-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d40cc-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d40cc-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d40cc-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d40cc-113">Element</span></span>|<span data-ttu-id="d40cc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d40cc-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="d40cc-115">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d40cc-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d40cc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d40cc-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
