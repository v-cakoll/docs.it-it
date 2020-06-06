---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399448"
---
# \<system.serviceModel>
<span data-ttu-id="82b84-102">Questa sezione di configurazione contiene tutti gli elementi di configurazione ServiceModel di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="82b84-102">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="82b84-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82b84-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82b84-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="82b84-104">Attributes and Elements</span></span>  
 <span data-ttu-id="82b84-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="82b84-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82b84-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="82b84-106">Attributes</span></span>  
 <span data-ttu-id="82b84-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="82b84-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82b84-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="82b84-108">Child Elements</span></span>  
  
|<span data-ttu-id="82b84-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="82b84-109">Element</span></span>|<span data-ttu-id="82b84-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82b84-110">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|<span data-ttu-id="82b84-111">Questa sezione definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="82b84-111">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="82b84-112">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="82b84-112">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="82b84-113">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="82b84-113">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[\<bindings>](bindings.md)|<span data-ttu-id="82b84-114">Questa sezione contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="82b84-114">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="82b84-115">Ogni voce è identificata dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="82b84-115">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="82b84-116">I servizi usano le associazioni collegandole mediante l'oggetto `name`.</span><span class="sxs-lookup"><span data-stu-id="82b84-116">Services use bindings by linking them using the `name`.</span></span>|  
|[\<client>](client.md)|<span data-ttu-id="82b84-117">Questa sezione include un elenco degli endpoint usati da un client per connettersi a un servizio.</span><span class="sxs-lookup"><span data-stu-id="82b84-117">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[\<comContracts>](comcontracts.md)|<span data-ttu-id="82b84-118">Questa sezione definisce i contratti COM che consentono l'interoperabilità tra WCF e COM.</span><span class="sxs-lookup"><span data-stu-id="82b84-118">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[\<commonBehaviors>](commonbehaviors.md)|<span data-ttu-id="82b84-119">Il contenuto di questa sezione può essere definito solo nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="82b84-119">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="82b84-120">e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="82b84-120">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="82b84-121">Ogni raccolta definisce gli elementi di comportamento usati rispettivamente da tutti gli endpoint e i servizi WCF nel computer.</span><span class="sxs-lookup"><span data-stu-id="82b84-121">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="82b84-122">Se un comportamento viene definito in entrambe le sezioni `<commonBehaviors>` e `<behaviors>`, la preferenza viene assegnata a quello nella sezione \<behaviors>.</span><span class="sxs-lookup"><span data-stu-id="82b84-122">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="82b84-123">Questa sezione include le impostazioni per le funzionalità di diagnostica di WCF.</span><span class="sxs-lookup"><span data-stu-id="82b84-123">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="82b84-124">L'utente può abilitare o disabilitare tracce, contatori di prestazioni e il provider WMI e può aggiungere filtri dei messaggi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="82b84-124">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[\<extensions>](extensions-section.md)|<span data-ttu-id="82b84-125">Questa sezione include una raccolta di estensioni che consentono di creare associazioni definite dall'utente, comportamenti e altri aspetti relativi alle estensioni.</span><span class="sxs-lookup"><span data-stu-id="82b84-125">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="82b84-126">Questa sezione definisce un set di mapping dei protocolli predefiniti tra gli schemi dei protocolli di trasporto (ad esempio http, net.tcp, net.pipe e così via) e le associazioni di WCF.</span><span class="sxs-lookup"><span data-stu-id="82b84-126">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[\<routing>](routing.md)|<span data-ttu-id="82b84-127">In questa sezione viene definito un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare messaggi quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="82b84-127">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="82b84-128">Questa sezione definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="82b84-128">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="82b84-129">Se questa sezione è vuota, viene usato il tipo predefinito.</span><span class="sxs-lookup"><span data-stu-id="82b84-129">If this section is empty, the default type is used.</span></span>|  
|[\<services>](services.md)|<span data-ttu-id="82b84-130">Questa sezione include una raccolta di servizi.</span><span class="sxs-lookup"><span data-stu-id="82b84-130">The section contains a collection of services.</span></span> <span data-ttu-id="82b84-131">Per ogni servizio definito nell'assembly, questo elemento contiene un elemento `service` nel quale vengono specificate le impostazioni per il servizio.</span><span class="sxs-lookup"><span data-stu-id="82b84-131">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="82b84-132">Questa sezione definisce una raccolta di endpoint standard rappresentati da endpoint preconfigurati riusabili.</span><span class="sxs-lookup"><span data-stu-id="82b84-132">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="82b84-133">Un endpoint standard disporrà di uno o più indirizzi, attributi di associazione e del contratto impostati su un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="82b84-133">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="82b84-134">Ad esempio, nell'endpoint di individuazione il contratto è fisso.</span><span class="sxs-lookup"><span data-stu-id="82b84-134">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="82b84-135">È inoltre possibile usare endpoint standard per estendere endpoint servizio con nuove proprietà in modo analogo alla definizione di associazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="82b84-135">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[\<tracking>](tracking-of-wcf.md)|<span data-ttu-id="82b84-136">In questa sezione vengono definite le impostazioni di rilevamento per un servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="82b84-136">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="82b84-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="82b84-137">Parent Elements</span></span>  
  
|<span data-ttu-id="82b84-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="82b84-138">Element</span></span>|<span data-ttu-id="82b84-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82b84-139">Description</span></span>|  
|-------------|-----------------|  
|\<configuration>|<span data-ttu-id="82b84-140">Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.</span><span class="sxs-lookup"><span data-stu-id="82b84-140">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82b84-141">Commenti</span><span class="sxs-lookup"><span data-stu-id="82b84-141">Remarks</span></span>  
 <span data-ttu-id="82b84-142">WCF non aggiunge elementi alle sezioni di configurazione di altri prodotti.</span><span class="sxs-lookup"><span data-stu-id="82b84-142">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="82b84-143">I servizi WCF vengono definiti nella `services` sezione del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="82b84-143">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="82b84-144">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="82b84-144">An assembly can contain any number of services.</span></span> <span data-ttu-id="82b84-145">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="82b84-145">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="82b84-146">La sezione e il relativo contenuto definiscono in modo specifico il contratto, il comportamento e gli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="82b84-146">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="82b84-147">Fra gli attributi di un servizio, solo `name` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="82b84-147">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="82b84-148">Per impostazione predefinita, il nome di un servizio descrive il tipo CLR sottostante usato per implementare un servizio. È tuttavia possibile modificare la proprietà ConfigurationName di un attributo <xref:System.ServiceModel.ServiceContractAttribute> per eseguire l'override del requisito del tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="82b84-148">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="82b84-149">L'attributo `behaviorConfiguration` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="82b84-149">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="82b84-150">identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="82b84-150">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="82b84-151">Il comportamento specificato da questo attributo deve essere collegato a un comportamento di servizio definito nell'ambito dello stesso file di configurazione, ad esempio lo stesso file o un file padre.</span><span class="sxs-lookup"><span data-stu-id="82b84-151">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="82b84-152">Ogni servizio espone uno o più endpoint definiti in un elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="82b84-152">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="82b84-153">Ogni endpoint presenta indirizzo e associazione propri.</span><span class="sxs-lookup"><span data-stu-id="82b84-153">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="82b84-154">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="82b84-154">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="82b84-155">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="82b84-155">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="82b84-156">L'attributo `binding` definisce la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="82b84-156">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="82b84-157">L'attributo `bindingConfiguration` definisce quale associazione configurata viene usata fra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="82b84-157">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="82b84-158">Una sezione di associazione può infatti definire varie associazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="82b84-158">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b84-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="82b84-159">Example</span></span>  
 <span data-ttu-id="82b84-160">Segue un esempio di file di configurazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="82b84-160">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="82b84-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82b84-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
