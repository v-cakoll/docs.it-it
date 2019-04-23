---
title: <add> di <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: a58a29e44fff3d653d04da271e3b240f2969611f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143897"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="6d964-102">\<aggiungere > di \<baseAddressPrefixFilter ></span><span class="sxs-lookup"><span data-stu-id="6d964-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="6d964-103">Rappresenta un elemento di configurazione che specifica un filtro pass-through, che fornisce un meccanismo per scegliere le associazioni di Internet Information Services (IIS) appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="6d964-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="6d964-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6d964-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6d964-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="6d964-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="6d964-106">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="6d964-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="6d964-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6d964-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d964-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d964-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d964-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d964-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6d964-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d964-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d964-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6d964-111">Attributes</span></span>  
  
|<span data-ttu-id="6d964-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="6d964-112">Attribute</span></span>|<span data-ttu-id="6d964-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d964-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d964-114">prefix</span><span class="sxs-lookup"><span data-stu-id="6d964-114">prefix</span></span>|<span data-ttu-id="6d964-115">URI usato per la corrispondenza a una parte di un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="6d964-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d964-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d964-116">Child Elements</span></span>  
 <span data-ttu-id="6d964-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6d964-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d964-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d964-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6d964-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d964-119">Element</span></span>|<span data-ttu-id="6d964-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d964-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d964-121">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="6d964-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="6d964-122">Raccolta di elementi di configurazione che specificano filtri pass-through, che forniscono un meccanismo per scegliere le associazioni di IIS appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="6d964-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d964-123">Note</span><span class="sxs-lookup"><span data-stu-id="6d964-123">Remarks</span></span>  
 <span data-ttu-id="6d964-124">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="6d964-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="6d964-125">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="6d964-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="6d964-126">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="6d964-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="6d964-127">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="6d964-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="6d964-128">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="6d964-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="6d964-129">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="6d964-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="6d964-130">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="6d964-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="6d964-131">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di base per ogni schema, è possibile utilizzare la funzionalità di filtro dei prefissi per scegliere l'indirizzo di base necessario del servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="6d964-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="6d964-132">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6d964-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="6d964-133">Un sito può ad esempio contenere gli indirizzi di base seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d964-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="6d964-134">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="6d964-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="6d964-135">In questo esempio `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono i soli indirizzi di base che è consentito attraversare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="6d964-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="6d964-136">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="6d964-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="6d964-137">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="6d964-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d964-138">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="6d964-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="6d964-139">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="6d964-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="6d964-140">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="6d964-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d964-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d964-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="6d964-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="6d964-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
