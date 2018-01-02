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
ms.workload: dotnet
ms.openlocfilehash: 46fb4f1f4688aede484b177e30b8bc8dfff1ece2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="51184-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="51184-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="51184-103">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51184-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="51184-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="51184-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="51184-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="51184-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51184-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51184-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51184-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="51184-107">Attributes and Elements</span></span>  
 <span data-ttu-id="51184-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="51184-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51184-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="51184-109">Attributes</span></span>  
 <span data-ttu-id="51184-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="51184-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51184-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="51184-111">Child Elements</span></span>  
  
|<span data-ttu-id="51184-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="51184-112">Element</span></span>|<span data-ttu-id="51184-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51184-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51184-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="51184-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="51184-115">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="51184-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51184-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="51184-116">Parent Elements</span></span>  
  
|<span data-ttu-id="51184-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="51184-117">Element</span></span>|<span data-ttu-id="51184-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51184-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51184-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="51184-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="51184-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="51184-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51184-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51184-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
