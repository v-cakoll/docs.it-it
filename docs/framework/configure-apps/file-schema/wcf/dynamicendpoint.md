---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e780e1975aecc80ea458ec6a86fca61e4ad22448
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="7c1e1-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="7c1e1-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="7c1e1-103">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c1e1-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="7c1e1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7c1e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7c1e1-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7c1e1-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1e1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c1e1-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
      <discoveryClientSettings discoveryEndpoint="String">
        <findCriteria duration="TimeSpan" 
                      maxResults="Integer" 
                      scopeMatchBy="Uri">
          <contractTypeNames>
            <add name="String" namespace="String" />
          <contractTypeNames>
          <extensions />
          <scopes>
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c1e1-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7c1e1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7c1e1-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7c1e1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c1e1-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="7c1e1-109">Attributes</span></span>  
 <span data-ttu-id="7c1e1-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7c1e1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7c1e1-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7c1e1-111">Child Elements</span></span>  
  
|<span data-ttu-id="7c1e1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c1e1-112">Element</span></span>|<span data-ttu-id="7c1e1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1e1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c1e1-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="7c1e1-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="7c1e1-115">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="7c1e1-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c1e1-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7c1e1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7c1e1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c1e1-117">Element</span></span>|<span data-ttu-id="7c1e1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1e1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c1e1-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7c1e1-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7c1e1-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="7c1e1-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c1e1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c1e1-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
