---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 0673507b72690c3a5c7dcc35442c05e378dba43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153035"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="329c4-101">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="329c4-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="329c4-102">Rappresenta una raccolta di elementi di configurazione che specificano filtri pass-through, che forniscono un meccanismo per selezionare le associazioni di Internet Information Services (IIS) appropriate quando si ospita l'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="329c4-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="329c4-103">\<baseAddressPrefixFilters> non riconosce "localhost"; utilizzare invece il nome completo del computer.</span><span class="sxs-lookup"><span data-stu-id="329c4-103">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
<span data-ttu-id="329c4-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="329c4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="329c4-105">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="329c4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="329c4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="329c4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="329c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>baseAddressPrefixFilters**</span><span class="sxs-lookup"><span data-stu-id="329c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329c4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="329c4-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="329c4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="329c4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="329c4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="329c4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="329c4-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="329c4-111">Attributes</span></span>  
 <span data-ttu-id="329c4-112">No.</span><span class="sxs-lookup"><span data-stu-id="329c4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="329c4-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="329c4-113">Child Elements</span></span>  
  
|<span data-ttu-id="329c4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="329c4-114">Element</span></span>|<span data-ttu-id="329c4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329c4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="329c4-116">\<aggiungere></span><span class="sxs-lookup"><span data-stu-id="329c4-116">\<add></span></span>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="329c4-117">Aggiunge un elemento di configurazione che specifica un filtro di prefisso per gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="329c4-117">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="329c4-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="329c4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="329c4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="329c4-119">Element</span></span>|<span data-ttu-id="329c4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329c4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="329c4-121">\<>serviceHostingEnvironment</span><span class="sxs-lookup"><span data-stu-id="329c4-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="329c4-122">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="329c4-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="329c4-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="329c4-123">Remarks</span></span>  
 <span data-ttu-id="329c4-124">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="329c4-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="329c4-125">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="329c4-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="329c4-126">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="329c4-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="329c4-127">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="329c4-127">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="329c4-128">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="329c4-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="329c4-129">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="329c4-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="329c4-130">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="329c4-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="329c4-131">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di base per ogni schema, è possibile utilizzare la funzionalità di filtro del prefisso per selezionare l'indirizzo di base richiesto del servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="329c4-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="329c4-132">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="329c4-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="329c4-133">Ad esempio, il sito può contenere i seguenti indirizzi di base:</span><span class="sxs-lookup"><span data-stu-id="329c4-133">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="329c4-134">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="329c4-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="329c4-135">In questo esempio, `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono gli unici indirizzi di base che è consentito passare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="329c4-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="329c4-136">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="329c4-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="329c4-137">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="329c4-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="329c4-138">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="329c4-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="329c4-139">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="329c4-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="329c4-140">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="329c4-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329c4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="329c4-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="329c4-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="329c4-142">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
