---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 2783796166d56be3d4983ab09a60d62491699fe3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925856"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="80822-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="80822-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="80822-102">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="80822-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="80822-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="80822-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="80822-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="80822-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80822-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80822-105">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80822-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="80822-106">Attributes and Elements</span></span>  
 <span data-ttu-id="80822-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="80822-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80822-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="80822-108">Attributes</span></span>  
  
|<span data-ttu-id="80822-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="80822-109">Attribute</span></span>|<span data-ttu-id="80822-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="80822-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80822-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="80822-111">discoveryEndpoint</span></span>|<span data-ttu-id="80822-112">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="80822-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80822-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="80822-113">Child Elements</span></span>  
  
|<span data-ttu-id="80822-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="80822-114">Element</span></span>|<span data-ttu-id="80822-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="80822-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80822-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="80822-116">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="80822-117">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="80822-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="80822-118">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="80822-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80822-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="80822-119">Parent Elements</span></span>  
  
|<span data-ttu-id="80822-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="80822-120">Element</span></span>|<span data-ttu-id="80822-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="80822-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80822-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="80822-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="80822-123">Definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="80822-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80822-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80822-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
