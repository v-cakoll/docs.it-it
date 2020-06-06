---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855408"
---
# \<discoveryClientSettings>
<span data-ttu-id="2236b-101">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="2236b-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="2236b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2236b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2236b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2236b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2236b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2236b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2236b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="2236b-105">Attributes</span></span>  
  
|<span data-ttu-id="2236b-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="2236b-106">Attribute</span></span>|<span data-ttu-id="2236b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2236b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2236b-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="2236b-108">discoveryEndpoint</span></span>|<span data-ttu-id="2236b-109">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2236b-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2236b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2236b-110">Child Elements</span></span>  
  
|<span data-ttu-id="2236b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2236b-111">Element</span></span>|<span data-ttu-id="2236b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2236b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2236b-113">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="2236b-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2236b-114">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e nei criteri di terminazione della ricerca (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="2236b-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2236b-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2236b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2236b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2236b-116">Element</span></span>|<span data-ttu-id="2236b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2236b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2236b-118">Definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2236b-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2236b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2236b-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
