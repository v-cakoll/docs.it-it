---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eaa3998d3d0b1642c0c92380ec1228eea69d4da8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700891"
---
# <a name="findcriteria"></a><span data-ttu-id="df116-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="df116-101">\<findCriteria></span></span>
<span data-ttu-id="df116-102">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="df116-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="df116-103">I criteri possono essere raggruppati in Criteri di ricerca (specificando i servizi desiderati) e trovare i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="df116-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="df116-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="df116-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="df116-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="df116-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df116-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df116-106">Syntax</span></span>  
  
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
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df116-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="df116-107">Attributes and Elements</span></span>  
 <span data-ttu-id="df116-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="df116-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df116-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="df116-109">Attributes</span></span>  
  
|<span data-ttu-id="df116-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="df116-110">Attribute</span></span>|<span data-ttu-id="df116-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df116-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df116-112">duration</span><span class="sxs-lookup"><span data-stu-id="df116-112">duration</span></span>|<span data-ttu-id="df116-113">Valore Timespan che specifica il tempo massimo di attesa per le risposte dai servizi in una rete.</span><span class="sxs-lookup"><span data-stu-id="df116-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="df116-114">La durata predefinita è 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="df116-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="df116-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="df116-115">maxResults</span></span>|<span data-ttu-id="df116-116">Integer che specifica il numero massimo di risposte da attendere dai servizi in una rete o su Internet.</span><span class="sxs-lookup"><span data-stu-id="df116-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="df116-117">Se il numero massimo di risposte viene ricevuto prima della scadenza del valore specificato nell'attributo `duration`, l'operazione di ricerca termina.</span><span class="sxs-lookup"><span data-stu-id="df116-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="df116-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="df116-118">scopeMatchBy</span></span>|<span data-ttu-id="df116-119">URI che specifica l'algoritmo di corrispondenza da usare per trovare la corrispondenza tra l'ambito nel messaggio del Probe e quello dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="df116-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="df116-120">Sono supportate cinque regole di corrispondenza degli ambiti.</span><span class="sxs-lookup"><span data-stu-id="df116-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="df116-121">Se non si specifica una regola di corrispondenza degli ambiti, verrà usato `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="df116-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="df116-122">Per altre informazioni in merito, vedere <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="df116-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df116-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="df116-123">Child Elements</span></span>  
  
|<span data-ttu-id="df116-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="df116-124">Element</span></span>|<span data-ttu-id="df116-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df116-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df116-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="df116-126">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="df116-127">Raccolta di elementi di configurazione che contengono i nomi dei tipi di contratto di servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="df116-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="df116-128">\<le estensioni > di \<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="df116-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="df116-129">Raccolta di oggetti di elementi XML che forniscono estensioni.</span><span class="sxs-lookup"><span data-stu-id="df116-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="df116-130">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="df116-130">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="df116-131">Raccolta di oggetti contenenti URI assoluti usati durante un'operazione di ricerca per l'individuazione di uno o più servizi specifici.</span><span class="sxs-lookup"><span data-stu-id="df116-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="df116-132">Se il servizio specifico viene trovato, significa che è stata trovata una corrispondenza esatta tra l'URI del servizio e l'URI dell'ambito, talvolta con il supporto di regole di ambito che gestiscono i problemi di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="df116-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df116-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="df116-133">Parent Elements</span></span>  
  
|<span data-ttu-id="df116-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="df116-134">Element</span></span>|<span data-ttu-id="df116-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df116-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df116-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="df116-136">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="df116-137">Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.</span><span class="sxs-lookup"><span data-stu-id="df116-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df116-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df116-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
