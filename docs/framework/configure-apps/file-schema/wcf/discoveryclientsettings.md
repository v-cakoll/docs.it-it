---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855408"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="78901-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="78901-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="78901-102">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="78901-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="78901-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78901-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78901-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="78901-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="78901-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="78901-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="78901-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="78901-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="78901-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="78901-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="78901-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> discoveryClientSettings**</span><span class="sxs-lookup"><span data-stu-id="78901-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78901-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78901-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78901-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78901-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78901-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78901-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78901-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="78901-112">Attributes</span></span>  
  
|<span data-ttu-id="78901-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="78901-113">Attribute</span></span>|<span data-ttu-id="78901-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78901-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78901-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="78901-115">discoveryEndpoint</span></span>|<span data-ttu-id="78901-116">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="78901-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78901-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78901-117">Child Elements</span></span>  
  
|<span data-ttu-id="78901-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="78901-118">Element</span></span>|<span data-ttu-id="78901-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="78901-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78901-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="78901-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="78901-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="78901-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="78901-122">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="78901-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78901-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78901-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78901-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="78901-124">Element</span></span>|<span data-ttu-id="78901-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78901-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78901-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="78901-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="78901-127">Definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="78901-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78901-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78901-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
