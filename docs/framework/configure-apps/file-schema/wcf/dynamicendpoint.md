---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187746"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="62af0-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="62af0-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="62af0-102">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62af0-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="62af0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62af0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="62af0-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="62af0-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62af0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62af0-105">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62af0-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="62af0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="62af0-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="62af0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62af0-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="62af0-108">Attributes</span></span>  
 <span data-ttu-id="62af0-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="62af0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62af0-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62af0-110">Child Elements</span></span>  
  
|<span data-ttu-id="62af0-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="62af0-111">Element</span></span>|<span data-ttu-id="62af0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62af0-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62af0-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="62af0-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="62af0-114">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="62af0-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62af0-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="62af0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="62af0-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="62af0-116">Element</span></span>|<span data-ttu-id="62af0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62af0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62af0-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="62af0-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="62af0-119">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="62af0-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62af0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62af0-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
