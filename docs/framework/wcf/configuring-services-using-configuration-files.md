---
title: Configurazione dei servizi tramite file di configurazione
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: caf6e238ca286e5e712c0273e10502655fd7ff4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174797"
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="7e573-102">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7e573-102">Configuring Services Using Configuration Files</span></span>
<span data-ttu-id="7e573-103">La configurazione di un servizio Windows Communication Foundation (WCF) con un file di configurazione offre la flessibilità di fornire dati sul comportamento dell'endpoint e del servizio nel punto di distribuzione anziché in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-103">Configuring a Windows Communication Foundation (WCF) service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="7e573-104">In questo argomento vengono delineate le principali tecniche disponibili.</span><span class="sxs-lookup"><span data-stu-id="7e573-104">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="7e573-105">Un servizio WCF è configurabile utilizzando la tecnologia di configurazione di .NET Framework.A WCF service is configurable using the .NET Framework configuration technology.</span><span class="sxs-lookup"><span data-stu-id="7e573-105">A WCF service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="7e573-106">In genere, gli elementi XML vengono aggiunti al file Web.config per un sito Internet Information Services (IIS) che ospita un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="7e573-106">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="7e573-107">Gli elementi consentono di modificare dettagli, quali gli indirizzi degli endpoint (gli indirizzi effettivi usati per comunicare con il servizio), per i singoli computer.</span><span class="sxs-lookup"><span data-stu-id="7e573-107">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="7e573-108">Inoltre, WCF include diversi elementi forniti dal sistema che consentono di selezionare rapidamente le funzionalità di base per un servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-108">In addition, WCF includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="7e573-109">A partire da .NET Framework 4.NET Framework 4, WCF viene fornito con un nuovo modello di configurazione predefinito che semplifica i requisiti di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="7e573-109">Starting with .NET Framework 4, WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="7e573-110">Se non si fornisce alcuna configurazione WCF per un determinato servizio, il runtime configura automaticamente il servizio con alcuni endpoint standard e l'associazione/comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="7e573-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="7e573-111">In pratica, la scrittura della configurazione è una parte importante della programmazione di applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="7e573-111">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
 <span data-ttu-id="7e573-112">Per ulteriori informazioni, vedere [Configurazione delle associazioni per i servizi](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7e573-112">For more information, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="7e573-113">Per un elenco degli elementi [utilizzati](system-provided-bindings.md)più di più comune, vedere Associazioni fornite dal sistema .</span><span class="sxs-lookup"><span data-stu-id="7e573-113">For a list of the most commonly used elements, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="7e573-114">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="7e573-114">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e573-115">Nel caso di distribuzione di scenari affiancati in cui vengono implementate due versioni diverse di un servizio, è necessario specificare nomi parziali di assembly a cui viene fatto riferimento nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-115">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="7e573-116">Questa operazione è necessaria perché il file di configurazione è condiviso tra tutte le versioni di un servizio che potrebbero essere in esecuzione in versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e573-116">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="7e573-117">System.Configuration: Web.config e App.config</span><span class="sxs-lookup"><span data-stu-id="7e573-117">System.Configuration: Web.config and App.config</span></span>  
 <span data-ttu-id="7e573-118">WCF utilizza il sistema di configurazione System.Configuration di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e573-118">WCF uses the System.Configuration configuration system of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7e573-119">Quando si configura un servizio in Visual Studio, utilizzare un file Web.config o un file App.config per specificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7e573-119">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="7e573-120">La scelta del nome del file di configurazione è determinata dall'ambiente host scelto per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-120">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="7e573-121">Se si sta usando IIS per ospitare il servizio, usare un file Web.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-121">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="7e573-122">Se si sta usando un altro ambiente host, usare un file App.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-122">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="7e573-123">In Visual Studio il file denominato App.config viene usato per creare il file di configurazione finale.</span><span class="sxs-lookup"><span data-stu-id="7e573-123">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="7e573-124">Il nome finale effettivamente usato per la configurazione dipende dal nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7e573-124">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="7e573-125">Ad esempio, un assembly denominato "Cohowinery.exe" ha un file di configurazione finale denominato "Cohowinery.exe.config".</span><span class="sxs-lookup"><span data-stu-id="7e573-125">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="7e573-126">Tuttavia, è sufficiente modificare il file App.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-126">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="7e573-127">Le modifiche apportate al file vengono automaticamente apportate al file di configurazione finale dell'applicazione in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-127">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="7e573-128">Quando si usa un file App.config, il sistema di configurazione unisce il file App.config al contenuto del file Machine.config, al momento dell'avvio dell'applicazione e dell'applicazione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-128">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="7e573-129">Questo meccanismo consente di definire impostazioni a livello di computer nel file Machine.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-129">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="7e573-130">Il file App.config può essere usato per eseguire l'override del file Machine.config; è inoltre possibile bloccare le impostazioni nel file Machine.config in modo che vengano usate.</span><span class="sxs-lookup"><span data-stu-id="7e573-130">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="7e573-131">Nel caso di Web.config, il sistema di configurazione esegue il merge dei file Web.config in tutte le directory che conducono alla directory dell'applicazione nella configurazione che viene applicata.</span><span class="sxs-lookup"><span data-stu-id="7e573-131">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="7e573-132">Per altre informazioni sulla configurazione e sulle priorità <xref:System.Configuration> delle impostazioni, vedere gli argomenti nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7e573-132">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="7e573-133">Principali sezioni del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7e573-133">Major Sections of the Configuration File</span></span>  
 <span data-ttu-id="7e573-134">Le sezioni principali del file di configurazione includono gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7e573-134">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
> <span data-ttu-id="7e573-135">Le sezioni di associazioni e comportamenti sono facoltative e vengono incluse solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="7e573-135">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="7e573-136">I \<servizi> Element</span><span class="sxs-lookup"><span data-stu-id="7e573-136">The \<services> Element</span></span>  
 <span data-ttu-id="7e573-137">L'elemento `services` contiene le specifiche per tutti i servizi ospitati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-137">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="7e573-138">A partire dal modello di configurazione semplificato in .NET Framework 4, questa sezione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7e573-138">Starting with the simplified configuration model in .NET Framework 4, this section is optional.</span></span>  
  
 [<span data-ttu-id="7e573-139">\<servizi></span><span class="sxs-lookup"><span data-stu-id="7e573-139">\<services></span></span>](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="7e573-140">Il \<servizio> Element</span><span class="sxs-lookup"><span data-stu-id="7e573-140">The \<service> Element</span></span>  
 <span data-ttu-id="7e573-141">Ogni servizio ha gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e573-141">Each service has these attributes:</span></span>  
  
- <span data-ttu-id="7e573-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="7e573-142">`name`.</span></span> <span data-ttu-id="7e573-143">Specifica il tipo che fornisce un'implementazione di un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="7e573-144">Si tratta di un nome completo costituito dallo spazio dei nomi, seguito da un punto e quindi dal nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="7e573-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="7e573-145">Ad esempio `"MyNameSpace.myServiceType"`.</span><span class="sxs-lookup"><span data-stu-id="7e573-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
- <span data-ttu-id="7e573-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7e573-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="7e573-147">Specifica il nome di uno degli elementi `behavior` presenti nell'elemento `behaviors` .</span><span class="sxs-lookup"><span data-stu-id="7e573-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="7e573-148">Il comportamento specificato regola azioni, stabilendo, ad esempio, se il servizio consente la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="7e573-149">Se il valore è il nome vuoto o se non viene specificato alcun attributo `behaviorConfiguration` , viene aggiunto al servizio il set predefinito di comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
- [<span data-ttu-id="7e573-150">\<>di servizio</span><span class="sxs-lookup"><span data-stu-id="7e573-150">\<service></span></span>](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="7e573-151">Elemento \<> dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="7e573-151">The \<endpoint> Element</span></span>  
 <span data-ttu-id="7e573-152">Ogni endpoint richiede un indirizzo, un'associazione e un contratto, rappresentati dagli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e573-152">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
- <span data-ttu-id="7e573-153">`address`.</span><span class="sxs-lookup"><span data-stu-id="7e573-153">`address`.</span></span> <span data-ttu-id="7e573-154">Specifica l'URI (Uniform Resource Identifier) del servizio, che può essere un indirizzo assoluto o uno relativo all'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-154">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="7e573-155">Se impostato su una stringa vuota, indica che l'endpoint è disponibile all'indirizzo di base specificato durante la creazione di <xref:System.ServiceModel.ServiceHost> per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-155">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
- <span data-ttu-id="7e573-156">`binding`.</span><span class="sxs-lookup"><span data-stu-id="7e573-156">`binding`.</span></span> <span data-ttu-id="7e573-157">In genere, specifica un'associazione fornita dal sistema come <xref:System.ServiceModel.WSHttpBinding>, ma può specificare anche un'associazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7e573-157">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="7e573-158">L'associazione specificata determina il tipo di trasporto, sicurezza e codifica usato e se sono supportati o attivati flussi, sessioni affidabili o transazioni.</span><span class="sxs-lookup"><span data-stu-id="7e573-158">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
- <span data-ttu-id="7e573-159">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7e573-159">`bindingConfiguration`.</span></span> <span data-ttu-id="7e573-160">Se i valori predefiniti di un'associazione devono essere modificati, è possibile farlo configurando l'elemento `binding` appropriato nell'elemento `bindings` .</span><span class="sxs-lookup"><span data-stu-id="7e573-160">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="7e573-161">A questo attributo deve essere assegnato lo stesso valore dell'attributo `name` dell'elemento `binding` usato per modificare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="7e573-161">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="7e573-162">Se non viene assegnato alcun nome o non si specifica alcun attributo `bindingConfiguration` nell'associazione, nell'endpoint viene usata l'associazione predefinita del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-162">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
- <span data-ttu-id="7e573-163">`contract`.</span><span class="sxs-lookup"><span data-stu-id="7e573-163">`contract`.</span></span> <span data-ttu-id="7e573-164">Specifica l'interfaccia che definisce il contratto.</span><span class="sxs-lookup"><span data-stu-id="7e573-164">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="7e573-165">Si tratta dell'interfaccia implementata nel tipo CLR (Common Language Runtime) specificato dall'attributo `name` dell'elemento `service` .</span><span class="sxs-lookup"><span data-stu-id="7e573-165">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
- [<span data-ttu-id="7e573-166">\<>endpoint</span><span class="sxs-lookup"><span data-stu-id="7e573-166">\<endpoint></span></span>](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="7e573-167">Elemento \<di> delle associazioniThe bindings> Element</span><span class="sxs-lookup"><span data-stu-id="7e573-167">The \<bindings> Element</span></span>  
 <span data-ttu-id="7e573-168">L'elemento `bindings` contiene le specifiche per tutte le associazioni usabili da qualsiasi endpoint definito in qualsiasi servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-168">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [<span data-ttu-id="7e573-169">\<associazioni></span><span class="sxs-lookup"><span data-stu-id="7e573-169">\<bindings></span></span>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="7e573-170">Elemento \<della> di associazioneThe binding> Element</span><span class="sxs-lookup"><span data-stu-id="7e573-170">The \<binding> Element</span></span>  
 <span data-ttu-id="7e573-171">L'elemento `binding` contenuto nell'elemento `bindings` può essere una delle associazioni fornite dal sistema (vedere [System-Provided Bindings](system-provided-bindings.md)) o un'associazione personalizzata (vedere [Custom Bindings](./extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="7e573-171">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](system-provided-bindings.md)) or a custom binding (see [Custom Bindings](./extending/custom-bindings.md)).</span></span> <span data-ttu-id="7e573-172">L'elemento `binding` ha un attributo `name` che mette in correlazione l'associazione e l'endpoint specificato nell'attributo `bindingConfiguration` dell'elemento `endpoint` .</span><span class="sxs-lookup"><span data-stu-id="7e573-172">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="7e573-173">Se non è specificato alcun nome, l'associazione corrisponde all'impostazione predefinita del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-173">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
<span data-ttu-id="7e573-174">Per ulteriori informazioni sulla configurazione di servizi e client, vedere [Configurazione dei servizi WCF](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="7e573-174">For more information about configuring services and clients, see [Configuring WCF services](configuring-services.md).</span></span>
  
 [<span data-ttu-id="7e573-175">\<>di associazione</span><span class="sxs-lookup"><span data-stu-id="7e573-175">\<binding></span></span>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="7e573-176">Il \<> dei comportamenti</span><span class="sxs-lookup"><span data-stu-id="7e573-176">The \<behaviors> Element</span></span>  
 <span data-ttu-id="7e573-177">Si tratta di un elemento contenitore per gli elementi `behavior` che definiscono i comportamenti di un servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-177">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [<span data-ttu-id="7e573-178">\<comportamenti></span><span class="sxs-lookup"><span data-stu-id="7e573-178">\<behaviors></span></span>](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="7e573-179">Il \<comportamento>elementoThe behavior> Element</span><span class="sxs-lookup"><span data-stu-id="7e573-179">The \<behavior> Element</span></span>  
 <span data-ttu-id="7e573-180">Ogni `behavior` elemento è `name` identificato da un attributo e fornisce `throttling` un comportamento fornito dal sistema, ad esempio <> o un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7e573-180">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="7e573-181">Se non viene assegnato alcun nome, l'elemento relativo al comportamento corrisponde al comportamento del servizio o dell'endpoint predefinito.</span><span class="sxs-lookup"><span data-stu-id="7e573-181">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [<span data-ttu-id="7e573-182">\<>di comportamento</span><span class="sxs-lookup"><span data-stu-id="7e573-182">\<behavior></span></span>](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="7e573-183">Come usare configurazioni di associazioni e comportamenti</span><span class="sxs-lookup"><span data-stu-id="7e573-183">How to Use Binding and Behavior Configurations</span></span>  
 <span data-ttu-id="7e573-184">WCF semplifica la condivisione delle configurazioni tra gli endpoint usando un sistema di riferimento nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-184">WCF makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="7e573-185">Invece di assegnare direttamente valori di configurazione a un endpoint, i valori di configurazione relativi all'associazione vengono raggruppati in elementi `bindingConfiguration` nella sezione `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="7e573-185">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="7e573-186">Una configurazione di associazione è un gruppo denominato di impostazioni su un'associazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-186">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="7e573-187">Gli endpoint possono quindi fare riferimento a `bindingConfiguration` in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7e573-187">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint
          address="myAddress" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint
          address="myAddress2" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint
          address="myAddress3" binding="basicHttpBinding"
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7e573-188">L'attributo `name` di `bindingConfiguration` è impostato nell'elemento `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="7e573-188">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="7e573-189">Deve `name` essere una stringa univoca all'interno dell'ambito del tipo di associazione, in questo caso il [<basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md), o un valore vuoto per fare riferimento all'associazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7e573-189">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="7e573-190">L'endpoint si collega alla configurazione impostando l'attributo `bindingConfiguration` su questa stringa.</span><span class="sxs-lookup"><span data-stu-id="7e573-190">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="7e573-191">Un attributo `behaviorConfiguration` viene implementato nello stesso modo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e573-191">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7e573-192">Si noti che al servizio viene aggiunto il set predefinito di comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="7e573-192">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="7e573-193">Questo sistema consente agli endpoint di condividere configurazioni comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7e573-193">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="7e573-194">Se è necessario un ambito a livello di computer, creare la configurazione dell'associazione o del comportamento in Machine.config.If machine-wide scope is required, create the binding or behavior configuration in Machine.config. Le impostazioni di configurazione sono disponibili in tutti i file App.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-194">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="7e573-195">[Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) semplifica la creazione di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="7e573-195">The [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="7e573-196">Unione di comportamenti</span><span class="sxs-lookup"><span data-stu-id="7e573-196">Behavior Merge</span></span>  
 <span data-ttu-id="7e573-197">La funzionalità di unione dei comportamenti semplifica la gestione di questi ultimi quando si desidera un set di comportamenti comuni da usare in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="7e573-197">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="7e573-198">Tale funzionalità consente di specificare i comportamenti a livelli diversi della gerarchia di configurazione e consente altresì ai servizi di ereditare i comportamenti da più livelli della gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-198">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="7e573-199">Per illustrare questo funzionamento, si presupponga di disporre del layout di directory virtuale seguente in IIS:</span><span class="sxs-lookup"><span data-stu-id="7e573-199">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 <span data-ttu-id="7e573-200">E `~\Web.config` il file ha i seguenti contenuti:</span><span class="sxs-lookup"><span data-stu-id="7e573-200">And your `~\Web.config` file has the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7e573-201">Un figlio Web.config è situato in ~\Child\Web.config con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="7e573-201">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7e573-202">Il servizio presente in ~\Child\Service.svc si comporterà come se disponesse di entrambi i comportamenti di serviceDebug e serviceMetadata,</span><span class="sxs-lookup"><span data-stu-id="7e573-202">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="7e573-203">mentre il servizio in ~ \Service.svc disporrà solo del comportamento di serviceDebug.</span><span class="sxs-lookup"><span data-stu-id="7e573-203">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="7e573-204">In pratica vengono unite le due raccolte di comportamenti con lo stesso nome (in questo caso la stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="7e573-204">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="7e573-205">È inoltre possibile cancellare \<le raccolte di comportamenti utilizzando il tag \<clear> e rimuovere singoli comportamenti dalla raccolta utilizzando il tag remove>.</span><span class="sxs-lookup"><span data-stu-id="7e573-205">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="7e573-206">Le due configurazioni seguenti, ad esempio, determinano il solo comportamento di serviceMetadata per il servizio figlio:</span><span class="sxs-lookup"><span data-stu-id="7e573-206">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7e573-207">L'unione di comportamenti può essere eseguita per raccolte di comportamenti anonimi, come illustrato in precedenza, e raccolte di comportamenti denominati.</span><span class="sxs-lookup"><span data-stu-id="7e573-207">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="7e573-208">L'unione dei comportamenti funziona nell'ambiente di hosting IIS, in cui i file Web.config vengono uniti gerarchicamente con il file Web.config radice e machine.config. Ma funziona anche nell'ambiente dell'applicazione, dove machine.config può essere unito al file App.config.</span><span class="sxs-lookup"><span data-stu-id="7e573-208">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="7e573-209">L'unione di comportamenti si applica sia comportamenti dell'endpoint che a comportamenti del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="7e573-209">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="7e573-210">Se una raccolta di comportamenti figlio contiene un comportamento già presente nella raccolta di comportamenti padre, il comportamento figlio sostituisce quello del padre.</span><span class="sxs-lookup"><span data-stu-id="7e573-210">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="7e573-211">Pertanto, se una `<serviceMetadata httpGetEnabled="False" />` raccolta di comportamenti `<serviceMetadata httpGetEnabled="True" />`padre e una raccolta di comportamenti figlio avevano , il comportamento figlio eseguirebbe l'override del comportamento padre nell'insieme di comportamenti e httpGetEnabled sarebbe "true".</span><span class="sxs-lookup"><span data-stu-id="7e573-211">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e573-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e573-212">See also</span></span>

- [<span data-ttu-id="7e573-213">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="7e573-213">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="7e573-214">Configurazione dei servizi WCFConfiguring WCF services</span><span class="sxs-lookup"><span data-stu-id="7e573-214">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="7e573-215">\<>di servizio</span><span class="sxs-lookup"><span data-stu-id="7e573-215">\<service></span></span>](../configure-apps/file-schema/wcf/service.md)
- [<span data-ttu-id="7e573-216">\<>di associazione</span><span class="sxs-lookup"><span data-stu-id="7e573-216">\<binding></span></span>](../configure-apps/file-schema/wcf/bindings.md)
