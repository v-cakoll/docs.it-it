---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: dcb52143c874b14c9241940f9b326a07b3fa6a82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540252"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="e2c41-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e2c41-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="e2c41-103">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2c41-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="e2c41-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e2c41-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2c41-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e2c41-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c41-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2c41-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2c41-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2c41-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e2c41-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2c41-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2c41-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="e2c41-109">Attributes</span></span>  
 <span data-ttu-id="e2c41-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e2c41-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2c41-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2c41-111">Child Elements</span></span>  
  
|<span data-ttu-id="e2c41-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2c41-112">Element</span></span>|<span data-ttu-id="e2c41-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c41-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2c41-114">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="e2c41-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="e2c41-115">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="e2c41-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2c41-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2c41-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e2c41-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2c41-117">Element</span></span>|<span data-ttu-id="e2c41-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c41-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2c41-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e2c41-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e2c41-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="e2c41-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2c41-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2c41-121">See also</span></span>
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
