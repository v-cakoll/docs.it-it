---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739043"
---
# \<discoveryClient>
<span data-ttu-id="f70b4-101">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f70b4-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="f70b4-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f70b4-102">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f70b4-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f70b4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f70b4-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f70b4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f70b4-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="f70b4-105">Attributes</span></span>  
  
|<span data-ttu-id="f70b4-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="f70b4-106">Attribute</span></span>|<span data-ttu-id="f70b4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f70b4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f70b4-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="f70b4-108">discoveryEndpoint</span></span>|<span data-ttu-id="f70b4-109">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f70b4-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f70b4-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f70b4-110">Child Elements</span></span>  
  
|<span data-ttu-id="f70b4-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f70b4-111">Element</span></span>|<span data-ttu-id="f70b4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f70b4-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="f70b4-113">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f70b4-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="f70b4-114">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e nei criteri di terminazione della ricerca (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="f70b4-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f70b4-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f70b4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f70b4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f70b4-116">Element</span></span>|<span data-ttu-id="f70b4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f70b4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f70b4-118">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f70b4-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f70b4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f70b4-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
