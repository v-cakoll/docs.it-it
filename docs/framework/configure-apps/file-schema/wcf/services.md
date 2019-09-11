---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854983"
---
# <a name="services"></a><span data-ttu-id="9efa3-101">\<> dei servizi</span><span class="sxs-lookup"><span data-stu-id="9efa3-101">\<services></span></span>
<span data-ttu-id="9efa3-102">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9efa3-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="9efa3-103">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="9efa3-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="9efa3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9efa3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9efa3-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9efa3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9efa3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> dei servizi**</span><span class="sxs-lookup"><span data-stu-id="9efa3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efa3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9efa3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9efa3-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9efa3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9efa3-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9efa3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9efa3-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9efa3-110">Attributes</span></span>  
 <span data-ttu-id="9efa3-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="9efa3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9efa3-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9efa3-112">Child Elements</span></span>  
  
|<span data-ttu-id="9efa3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9efa3-113">Element</span></span>|<span data-ttu-id="9efa3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9efa3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9efa3-115">\<service></span><span class="sxs-lookup"><span data-stu-id="9efa3-115">\<service></span></span>](service.md)|<span data-ttu-id="9efa3-116">Definisce il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="9efa3-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9efa3-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9efa3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9efa3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9efa3-118">Element</span></span>|<span data-ttu-id="9efa3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9efa3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9efa3-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9efa3-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="9efa3-121">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9efa3-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9efa3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9efa3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
