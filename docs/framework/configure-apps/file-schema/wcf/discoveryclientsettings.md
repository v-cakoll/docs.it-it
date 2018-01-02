---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bcd70df9809288987636f7766d6d4887dec84d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="22d59-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="22d59-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="22d59-103">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="22d59-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="22d59-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="22d59-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22d59-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="22d59-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d59-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22d59-106">Syntax</span></span>  
  
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
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22d59-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22d59-107">Attributes and Elements</span></span>  
 <span data-ttu-id="22d59-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22d59-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22d59-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="22d59-109">Attributes</span></span>  
  
|<span data-ttu-id="22d59-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="22d59-110">Attribute</span></span>|<span data-ttu-id="22d59-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d59-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22d59-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="22d59-112">discoveryEndpoint</span></span>|<span data-ttu-id="22d59-113">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22d59-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22d59-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22d59-114">Child Elements</span></span>  
  
|<span data-ttu-id="22d59-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="22d59-115">Element</span></span>|<span data-ttu-id="22d59-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d59-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22d59-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="22d59-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="22d59-118">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="22d59-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="22d59-119">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="22d59-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22d59-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22d59-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22d59-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="22d59-121">Element</span></span>|<span data-ttu-id="22d59-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d59-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22d59-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="22d59-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="22d59-124">Definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22d59-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22d59-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d59-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
