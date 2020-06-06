---
title: <add> di <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 8fdae02b558708a9b3f4535123752dce12dd5cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153140"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="fd417-102">\<add> di \<baseAddressPrefixFilter></span><span class="sxs-lookup"><span data-stu-id="fd417-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="fd417-103">Rappresenta un elemento di configurazione che specifica un filtro pass-through, che fornisce un meccanismo per scegliere le associazioni di Internet Information Services (IIS) appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="fd417-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fd417-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd417-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd417-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fd417-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fd417-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fd417-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd417-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="fd417-107">Attributes</span></span>  
  
|<span data-ttu-id="fd417-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="fd417-108">Attribute</span></span>|<span data-ttu-id="fd417-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd417-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd417-110">prefix</span><span class="sxs-lookup"><span data-stu-id="fd417-110">prefix</span></span>|<span data-ttu-id="fd417-111">URI usato per la corrispondenza a una parte di un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="fd417-111">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd417-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fd417-112">Child Elements</span></span>  
 <span data-ttu-id="fd417-113">No.</span><span class="sxs-lookup"><span data-stu-id="fd417-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd417-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fd417-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fd417-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd417-115">Element</span></span>|<span data-ttu-id="fd417-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd417-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="fd417-117">Raccolta di elementi di configurazione che specificano filtri pass-through che forniscono un meccanismo per scegliere le associazioni IIS appropriate quando si ospita un'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="fd417-117">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd417-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="fd417-118">Remarks</span></span>  
 <span data-ttu-id="fd417-119">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="fd417-119">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="fd417-120">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="fd417-120">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="fd417-121">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="fd417-121">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="fd417-122">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="fd417-122">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="fd417-123">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="fd417-123">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="fd417-124">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="fd417-124">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="fd417-125">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="fd417-125">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="fd417-126">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di base per ogni schema, è possibile utilizzare la funzionalità filtro prefisso per selezionare l'indirizzo di base necessario per il servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="fd417-126">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="fd417-127">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd417-127">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="fd417-128">Ad esempio, il sito può contenere gli indirizzi di base seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd417-128">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="fd417-129">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="fd417-129">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="fd417-130">In questo esempio `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono i soli indirizzi di base che è consentito attraversare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="fd417-130">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="fd417-131">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="fd417-131">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="fd417-132">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="fd417-132">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd417-133">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="fd417-133">The filter does not support any wildcards.</span></span> <span data-ttu-id="fd417-134">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="fd417-134">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="fd417-135">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="fd417-135">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd417-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fd417-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="fd417-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="fd417-137">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
