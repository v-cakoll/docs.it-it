---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 0673507b72690c3a5c7dcc35442c05e378dba43c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153035"
---
# \<baseAddressPrefixFilters>
<span data-ttu-id="8731d-101">Rappresenta una raccolta di elementi di configurazione che specificano filtri pass-through che forniscono un meccanismo per scegliere le associazioni Internet Information Services (IIS) appropriate quando ospitano l'applicazione Windows Communication Foundation (WCF) in IIS.</span><span class="sxs-lookup"><span data-stu-id="8731d-101">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="8731d-102">\<baseAddressPrefixFilters>non riconosce "localhost"; usare invece il nome completo del computer.</span><span class="sxs-lookup"><span data-stu-id="8731d-102">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**  
  
## <a name="syntax"></a><span data-ttu-id="8731d-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8731d-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8731d-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8731d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8731d-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8731d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8731d-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="8731d-106">Attributes</span></span>  
 <span data-ttu-id="8731d-107">No.</span><span class="sxs-lookup"><span data-stu-id="8731d-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8731d-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8731d-108">Child Elements</span></span>  
  
|<span data-ttu-id="8731d-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="8731d-109">Element</span></span>|<span data-ttu-id="8731d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8731d-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="8731d-111">Aggiunge un elemento di configurazione che specifica un filtro di prefisso per gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8731d-111">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8731d-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8731d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8731d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="8731d-113">Element</span></span>|<span data-ttu-id="8731d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8731d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="8731d-115">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="8731d-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8731d-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="8731d-116">Remarks</span></span>  
 <span data-ttu-id="8731d-117">Un filtro dei prefissi fornisce ai provider di hosting condiviso una modalità per specificare quali URI devono essere usati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="8731d-117">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="8731d-118">Consente agli host condivisi di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="8731d-118">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="8731d-119">I siti Web IIS sono contenitori di applicazioni virtuali che contengono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="8731d-119">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="8731d-120">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="8731d-120">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="8731d-121">Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="8731d-121">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="8731d-122">Il protocollo di associazione, ad esempio HTTP, definisce lo schema in base al quale viene stabilita la comunicazione, mentre le informazioni di associazione, ad esempio l'indirizzo IP, la porta, l'intestazione host, contengono i dati usati per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="8731d-122">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="8731d-123">IIS supporta la definizione di più associazioni IIS per ogni sito, che si traduce in più indirizzi di base per ogni schema.</span><span class="sxs-lookup"><span data-stu-id="8731d-123">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="8731d-124">Poiché un servizio WCF ospitato in un sito consente l'associazione a un solo indirizzo di base per ogni schema, è possibile utilizzare la funzionalità filtro prefisso per selezionare l'indirizzo di base necessario per il servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="8731d-124">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="8731d-125">Gli indirizzi di base in ingresso forniti da IIS sono filtrati in base all'elenco di prefissi facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8731d-125">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="8731d-126">Ad esempio, il sito può contenere gli indirizzi di base seguenti:</span><span class="sxs-lookup"><span data-stu-id="8731d-126">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="8731d-127">È possibile usare il file di configurazione seguente per specificare un filtro dei prefissi a livello di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="8731d-127">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="8731d-128">In questo esempio, `net.tcp://test1.fabrikam.com:8000` e `http://test2.fabrikam.com:9000` sono gli unici indirizzi di base che è consentito passare per i rispettivi schemi.</span><span class="sxs-lookup"><span data-stu-id="8731d-128">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="8731d-129">Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="8731d-129">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="8731d-130">La definizione del prefisso fa in modo che venga passato solo l'indirizzo di base corrispondente allo schema specifico.</span><span class="sxs-lookup"><span data-stu-id="8731d-130">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8731d-131">Il filtro non supporta caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="8731d-131">The filter does not support any wildcards.</span></span> <span data-ttu-id="8731d-132">Gli indirizzi di base forniti da IIS possono inoltre disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="8731d-132">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="8731d-133">Questi indirizzi non vengono filtrati.</span><span class="sxs-lookup"><span data-stu-id="8731d-133">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8731d-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8731d-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="8731d-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="8731d-135">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
