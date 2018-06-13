---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 9ac0c756f611c877ca689f12e5fe365026924f1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358541"
---
# <a name="ltbaseaddressprefixfiltersgt"></a><span data-ttu-id="f140e-102">&lt;baseAddressPrefixFilters&gt;</span><span class="sxs-lookup"><span data-stu-id="f140e-102">&lt;baseAddressPrefixFilters&gt;</span></span>
<span data-ttu-id="f140e-103">Rappresenta una raccolta di configurazione che specificano pass-through filtri, che forniscono un meccanismo per scegliere le associazioni di Internet Information Services (IIS) appropriate quando si ospita l'applicazione di Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="f140e-103">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f140e-104">\<baseAddressPrefixFilters > non riconosce "localhost", in alternativa, usare il nome completo del computer.</span><span class="sxs-lookup"><span data-stu-id="f140e-104">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="f140e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f140e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f140e-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="f140e-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f140e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f140e-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f140e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f140e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f140e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f140e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f140e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f140e-110">Attributes</span></span>  
 <span data-ttu-id="f140e-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f140e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f140e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f140e-112">Child Elements</span></span>  
  
|<span data-ttu-id="f140e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f140e-113">Element</span></span>|<span data-ttu-id="f140e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f140e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f140e-115">\<add></span><span class="sxs-lookup"><span data-stu-id="f140e-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="f140e-116">Aggiunge un elemento di configurazione che specifica un filtro di prefisso per gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f140e-116">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f140e-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f140e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f140e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f140e-118">Element</span></span>|<span data-ttu-id="f140e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f140e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f140e-120">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="f140e-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="f140e-121">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="f140e-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f140e-122">Note</span><span class="sxs-lookup"><span data-stu-id="f140e-122">Remarks</span></span>  
 <span data-ttu-id="f140e-123">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f140e-123">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="f140e-124">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="f140e-124">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="f140e-125">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="f140e-125">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="f140e-126">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="f140e-126">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="f140e-127">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="f140e-127">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="f140e-128">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="f140e-128">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="f140e-129">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="f140e-129">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="f140e-130">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di basa per ogni schema, è possibile utilizzare la funzionalità di filtro dei prefissi per scegliere l'indirizzo di basa necessario del servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="f140e-130">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="f140e-131">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f140e-131">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="f140e-132">Un sito può ad esempio contenere gli indirizzi di base seguenti.</span><span class="sxs-lookup"><span data-stu-id="f140e-132">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="f140e-133">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="f140e-133">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="f140e-134">In questo esempio, `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono gli unici indirizzi di base che è consentito passare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="f140e-134">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="f140e-135">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="f140e-135">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="f140e-136">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="f140e-136">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f140e-137">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="f140e-137">The filter does not support any wildcards.</span></span> <span data-ttu-id="f140e-138">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="f140e-138">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="f140e-139">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="f140e-139">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f140e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f140e-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="f140e-141">Hosting</span><span class="sxs-lookup"><span data-stu-id="f140e-141">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
