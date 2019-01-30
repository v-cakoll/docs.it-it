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
ms.openlocfilehash: 7b0c91bafc14dee0d298a5cd31dc674f5002466a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274196"
---
# <a name="systemservicemodel"></a><span data-ttu-id="a662d-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a662d-102">\<system.serviceModel></span></span>
<span data-ttu-id="a662d-103">Questa sezione di configurazione contiene tutti gli elementi di configurazione di ServiceModel di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a662d-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a662d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a662d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a662d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a662d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a662d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a662d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a662d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a662d-107">Attributes</span></span>  
 <span data-ttu-id="a662d-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="a662d-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a662d-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a662d-109">Child Elements</span></span>  
  
|<span data-ttu-id="a662d-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a662d-110">Element</span></span>|<span data-ttu-id="a662d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a662d-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a662d-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a662d-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="a662d-113">Questa sezione definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="a662d-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="a662d-114">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="a662d-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="a662d-115">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="a662d-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="a662d-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a662d-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="a662d-117">Questa sezione contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a662d-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="a662d-118">Ogni voce è identificata dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="a662d-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="a662d-119">I servizi usano le associazioni collegandole mediante l'oggetto `name`.</span><span class="sxs-lookup"><span data-stu-id="a662d-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="a662d-120">\<client></span><span class="sxs-lookup"><span data-stu-id="a662d-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="a662d-121">Questa sezione include un elenco degli endpoint usati da un client per connettersi a un servizio.</span><span class="sxs-lookup"><span data-stu-id="a662d-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="a662d-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="a662d-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="a662d-123">Questa sezione definisce i contratti COM che consentono l'interoperabilità tra WCF e COM.</span><span class="sxs-lookup"><span data-stu-id="a662d-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="a662d-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="a662d-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="a662d-125">Il contenuto di questa sezione può essere definito solo nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="a662d-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="a662d-126">e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="a662d-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="a662d-127">Ogni raccolta definisce elementi di comportamento usati rispettivamente da tutti gli endpoint WCF e servizi nel computer.</span><span class="sxs-lookup"><span data-stu-id="a662d-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="a662d-128">Se un comportamento viene definito in entrambe `<commonBehaviors>` e `<behaviors>` sezioni, il comportamento nel \<comportamenti > sezione è data la preferenza.</span><span class="sxs-lookup"><span data-stu-id="a662d-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="a662d-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="a662d-129">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="a662d-130">Questa sezione include le impostazioni per le funzionalità di diagnostica di WCF.</span><span class="sxs-lookup"><span data-stu-id="a662d-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="a662d-131">L'utente può abilitare o disabilitare tracce, contatori di prestazioni e il provider WMI e può aggiungere filtri dei messaggi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a662d-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="a662d-132">\<extensions></span><span class="sxs-lookup"><span data-stu-id="a662d-132">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="a662d-133">Questa sezione include una raccolta di estensioni che consentono di creare associazioni definite dall'utente, comportamenti e altri aspetti relativi alle estensioni.</span><span class="sxs-lookup"><span data-stu-id="a662d-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="a662d-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="a662d-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="a662d-135">In questa sezione definisce un set di mapping del protocollo predefinito tra gli schemi di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e le associazioni di WCF.</span><span class="sxs-lookup"><span data-stu-id="a662d-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="a662d-136">\<routing></span><span class="sxs-lookup"><span data-stu-id="a662d-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a662d-137">In questa sezione definisce un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing di tabelle che definiscono gli endpoint di destinazione per l'invio di messaggi a quello in cui un corrisponde al filtro.</span><span class="sxs-lookup"><span data-stu-id="a662d-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="a662d-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="a662d-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="a662d-139">Questa sezione definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="a662d-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="a662d-140">Se questa sezione è vuota, viene usato il tipo predefinito.</span><span class="sxs-lookup"><span data-stu-id="a662d-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="a662d-141">\<services></span><span class="sxs-lookup"><span data-stu-id="a662d-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="a662d-142">Questa sezione include una raccolta di servizi.</span><span class="sxs-lookup"><span data-stu-id="a662d-142">The section contains a collection of services.</span></span> <span data-ttu-id="a662d-143">Per ogni servizio definito nell'assembly, questo elemento contiene un elemento `service` nel quale vengono specificate le impostazioni per il servizio.</span><span class="sxs-lookup"><span data-stu-id="a662d-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="a662d-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a662d-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a662d-145">Questa sezione definisce una raccolta di endpoint standard rappresentati da endpoint preconfigurati riusabili.</span><span class="sxs-lookup"><span data-stu-id="a662d-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="a662d-146">Un endpoint standard disporrà di uno o più indirizzi, attributi di associazione e del contratto impostati su un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="a662d-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="a662d-147">Ad esempio, nell'endpoint di individuazione il contratto è fisso.</span><span class="sxs-lookup"><span data-stu-id="a662d-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="a662d-148">È inoltre possibile usare endpoint standard per estendere endpoint servizio con nuove proprietà in modo analogo alla definizione di associazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a662d-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="a662d-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a662d-149">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|<span data-ttu-id="a662d-150">Questa sezione definisce le impostazioni di rilevamento per un servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a662d-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a662d-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a662d-151">Parent Elements</span></span>  
  
|<span data-ttu-id="a662d-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="a662d-152">Element</span></span>|<span data-ttu-id="a662d-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a662d-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a662d-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a662d-154">\<configuration></span></span>|<span data-ttu-id="a662d-155">Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.</span><span class="sxs-lookup"><span data-stu-id="a662d-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a662d-156">Note</span><span class="sxs-lookup"><span data-stu-id="a662d-156">Remarks</span></span>  
 <span data-ttu-id="a662d-157">WCF non aggiunge elementi alle sezioni di configurazione di altri prodotti.</span><span class="sxs-lookup"><span data-stu-id="a662d-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="a662d-158">Servizi WCF sono definiti nel `services` sezione del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a662d-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="a662d-159">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="a662d-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="a662d-160">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="a662d-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="a662d-161">La sezione e il relativo contenuto definiscono in modo specifico il contratto, il comportamento e gli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="a662d-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="a662d-162">Fra gli attributi di un servizio, solo `name` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a662d-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="a662d-163">Per impostazione predefinita, il nome di un servizio descrive il tipo CLR sottostante usato per implementare un servizio. È tuttavia possibile modificare la proprietà ConfigurationName di un attributo <xref:System.ServiceModel.ServiceContractAttribute> per eseguire l'override del requisito del tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="a662d-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="a662d-164">L'attributo `behaviorConfiguration` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a662d-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="a662d-165">identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="a662d-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="a662d-166">Il comportamento specificato da questo attributo deve essere collegato a un comportamento di servizio definito nell'ambito dello stesso file di configurazione, ad esempio lo stesso file o un file padre.</span><span class="sxs-lookup"><span data-stu-id="a662d-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="a662d-167">Ogni servizio espone uno o più endpoint definiti in un elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="a662d-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="a662d-168">Ogni endpoint presenta indirizzo e associazione propri.</span><span class="sxs-lookup"><span data-stu-id="a662d-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="a662d-169">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="a662d-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="a662d-170">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="a662d-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="a662d-171">L'attributo `binding` definisce la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="a662d-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="a662d-172">L'attributo `bindingConfiguration` definisce quale associazione configurata viene usata fra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="a662d-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="a662d-173">Una sezione di associazione può infatti definire varie associazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="a662d-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a662d-174">Esempio</span><span class="sxs-lookup"><span data-stu-id="a662d-174">Example</span></span>  
 <span data-ttu-id="a662d-175">Segue un esempio di file di configurazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="a662d-175">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a662d-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a662d-176">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
