---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855347"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="4a3e0-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="4a3e0-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="4a3e0-102">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="4a3e0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a3e0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a3e0-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4a3e0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4a3e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="4a3e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="4a3e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dynamicEndpoint**</span><span class="sxs-lookup"><span data-stu-id="4a3e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a3e0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a3e0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a3e0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4a3e0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4a3e0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a3e0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4a3e0-110">Attributes</span></span>  
 <span data-ttu-id="4a3e0-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4a3e0-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4a3e0-112">Child Elements</span></span>  
  
|<span data-ttu-id="4a3e0-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a3e0-113">Element</span></span>|<span data-ttu-id="4a3e0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a3e0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a3e0-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="4a3e0-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="4a3e0-116">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a3e0-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4a3e0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4a3e0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a3e0-118">Element</span></span>|<span data-ttu-id="4a3e0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a3e0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a3e0-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4a3e0-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="4a3e0-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a3e0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a3e0-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
