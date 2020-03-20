---
title: <add> di <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 8fdae02b558708a9b3f4535123752dce12dd5cf5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153140"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="3f425-102">\<aggiungere> \<di baseAddressPrefixFilter></span><span class="sxs-lookup"><span data-stu-id="3f425-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="3f425-103">Rappresenta un elemento di configurazione che specifica un filtro pass-through, che fornisce un meccanismo per selezionare le associazioni di Internet Information Services (IIS) appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="3f425-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="3f425-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f425-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f425-105">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3f425-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3f425-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="3f425-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="3f425-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>baseAddressPrefixFilters**](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="3f425-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="3f425-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="3f425-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f425-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f425-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f425-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3f425-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3f425-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3f425-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f425-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="3f425-112">Attributes</span></span>  
  
|<span data-ttu-id="3f425-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3f425-113">Attribute</span></span>|<span data-ttu-id="3f425-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f425-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f425-115">prefix</span><span class="sxs-lookup"><span data-stu-id="3f425-115">prefix</span></span>|<span data-ttu-id="3f425-116">URI usato per la corrispondenza a una parte di un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="3f425-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f425-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3f425-117">Child Elements</span></span>  
 <span data-ttu-id="3f425-118">No.</span><span class="sxs-lookup"><span data-stu-id="3f425-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f425-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3f425-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3f425-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f425-120">Element</span></span>|<span data-ttu-id="3f425-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f425-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f425-122">\<>baseAddressPrefixFilters</span><span class="sxs-lookup"><span data-stu-id="3f425-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="3f425-123">Raccolta di elementi di configurazione che specificano filtri pass-through, che forniscono un meccanismo per selezionare le associazioni IIS appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="3f425-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f425-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3f425-124">Remarks</span></span>  
 <span data-ttu-id="3f425-125">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3f425-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="3f425-126">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="3f425-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="3f425-127">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="3f425-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="3f425-128">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="3f425-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="3f425-129">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="3f425-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="3f425-130">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="3f425-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="3f425-131">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="3f425-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="3f425-132">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di base per ogni schema, è possibile utilizzare la funzionalità di filtro del prefisso per selezionare l'indirizzo di base richiesto del servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="3f425-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="3f425-133">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3f425-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="3f425-134">Ad esempio, il sito può contenere i seguenti indirizzi di base:</span><span class="sxs-lookup"><span data-stu-id="3f425-134">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="3f425-135">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="3f425-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="3f425-136">In questo esempio `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono i soli indirizzi di base che è consentito attraversare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="3f425-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="3f425-137">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="3f425-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="3f425-138">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="3f425-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f425-139">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="3f425-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="3f425-140">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="3f425-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="3f425-141">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="3f425-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f425-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f425-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="3f425-143">Hosting</span><span class="sxs-lookup"><span data-stu-id="3f425-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
