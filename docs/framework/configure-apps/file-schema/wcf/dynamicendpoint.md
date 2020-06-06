---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855347"
---
# \<dynamicEndpoint>
<span data-ttu-id="5a23b-101">Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a23b-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="5a23b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a23b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a23b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5a23b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5a23b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5a23b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a23b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a23b-105">Attributes</span></span>  
 <span data-ttu-id="5a23b-106">No.</span><span class="sxs-lookup"><span data-stu-id="5a23b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a23b-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a23b-107">Child Elements</span></span>  
  
|<span data-ttu-id="5a23b-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a23b-108">Element</span></span>|<span data-ttu-id="5a23b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a23b-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="5a23b-110">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="5a23b-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a23b-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5a23b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5a23b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a23b-112">Element</span></span>|<span data-ttu-id="5a23b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a23b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="5a23b-114">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="5a23b-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a23b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a23b-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
