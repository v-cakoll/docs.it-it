---
title: Configurazione dei servizi WCF nel codice
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c05cc5947a36bbe8573c5308cdfbbe3f6c990815
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="6f0e0-102">Configurazione dei servizi WCF nel codice</span><span class="sxs-lookup"><span data-stu-id="6f0e0-102">Configuring WCF Services in Code</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="6f0e0-103"> consente agli sviluppatori di configurare i servizi utilizzando file di configurazione o codice.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-103"> allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="6f0e0-104">I file di configurazione sono utili quando è necessario configurare un servizio dopo la relativa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="6f0e0-105">Quando si utilizzano i file di configurazione, un professionista IT deve solo aggiornare il file di configurazione. Non è necessario eseguire la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="6f0e0-106">I file di configurazione, tuttavia, possono risultare complessi e difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="6f0e0-107">Non è disponibile alcun supporto per il debug dei file di configurazione e, poiché il riferimento agli elementi di configurazione viene fatto in base ai nomi, i file di configurazione della creazione possono risultare difficili e soggetti a errori.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="6f0e0-108"> consente inoltre di configurare i servizi nel codice.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-108"> also allows you to configure services in code.</span></span> <span data-ttu-id="6f0e0-109">Nelle versioni precedenti di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 e versioni precedenti), la configurazione dei servizi nel codice era semplice negli scenari indipendenti. La classe <xref:System.ServiceModel.ServiceHost> consentiva di configurare endpoint e comportamenti prima di chiamare ServiceHost.Open.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-109">In earlier versions of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="6f0e0-110">Negli scenari ospitati dal Web, tuttavia, non è possibile accedere direttamente alla classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="6f0e0-111">Per configurare un servizio ospitato dal Web era necessario creare un oggetto `System.ServiceModel.ServiceHostFactory` che creava l'oggetto <xref:System.ServiceModel.Activation.ServiceHostFactory> ed effettuava qualsiasi configurazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="6f0e0-112">A partire da .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] fornisce un modo più semplice per configurare sia i servizi indipendenti sia quelli ospitati dal Web nel codice.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-112">Starting with .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="6f0e0-113">Metodo Configure</span><span class="sxs-lookup"><span data-stu-id="6f0e0-113">The Configure method</span></span>  
 <span data-ttu-id="6f0e0-114">Definire semplicemente un metodo statico pubblico denominato `Configure` con la firma seguente nella classe di implementazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="6f0e0-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="6f0e0-115">Il metodo Configure accetta un'istanza dell'oggetto <xref:System.ServiceModel.ServiceConfiguration> che consente allo sviluppatore di aggiungere endpoint e comportamenti.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="6f0e0-116">Questo metodo viene chiamato da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] prima che venga aperto l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-116">This method is called by [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] before the service host is opened.</span></span> <span data-ttu-id="6f0e0-117">Una volta definito, tutte le impostazioni di configurazione del servizio specificate in un file app.config o web.config verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="6f0e0-118">Nel frammento di codice riportato di seguito viene illustrato come definire il metodo `Configure` e aggiungere un endpoint del servizio, un comportamento dell'endpoint e comportamenti del servizio:</span><span class="sxs-lookup"><span data-stu-id="6f0e0-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="6f0e0-119">Per abilitare un protocollo come HTTPS per un servizio, è possibile aggiungere in modo esplicito un endpoint che utilizza il protocollo oppure aggiungere automaticamente gli endpoint chiamando ServiceConfiguration.EnableProtocol(Binding) che aggiunge un endpoint per ogni indirizzo di base compatibile con il protocollo e ogni contratto di servizio definito.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="6f0e0-120">Nel codice seguente viene illustrato come utilizzare il metodo ServiceConfiguration.EnableProtocol:</span><span class="sxs-lookup"><span data-stu-id="6f0e0-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="6f0e0-121">Le impostazioni di <`protocolMappings`> sezione vengono utilizzati solo se nessun endpoint applicazione aggiunti al <xref:System.ServiceModel.ServiceConfiguration> a livello di codice. Facoltativamente, è possibile caricare la configurazione del servizio dal file di configurazione dell'applicazione predefinito chiamando <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> e quindi modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="6f0e0-122">La classe <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> consente inoltre di caricare la configurazione da una configurazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="6f0e0-123">Nell'esempio di codice seguente viene illustrato come implementare questa azione:</span><span class="sxs-lookup"><span data-stu-id="6f0e0-123">The following code illustrates how to implement this:</span></span>  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f0e0-124">Si noti che <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> Ignora <`host`> impostazioni all'interno di <`service`> tag di <`system.serviceModel`>.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="6f0e0-125">Concettualmente, <`host`> di configurazione dell'host, non la configurazione del servizio e si ottiene caricato prima di configurare il metodo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0e0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f0e0-126">See Also</span></span>  
 [<span data-ttu-id="6f0e0-127">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-127">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [<span data-ttu-id="6f0e0-128">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="6f0e0-128">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="6f0e0-129">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="6f0e0-129">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="6f0e0-130">Attivazione basata sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-130">Configuration-Based Activation</span></span>](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [<span data-ttu-id="6f0e0-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-131">Configuration</span></span>](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [<span data-ttu-id="6f0e0-132">Attivazione basata sulla configurazione in IIS e WAS</span><span class="sxs-lookup"><span data-stu-id="6f0e0-132">Configuration-Based Activation in IIS and WAS</span></span>](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [<span data-ttu-id="6f0e0-133">Configurazione e supporto dei metadati</span><span class="sxs-lookup"><span data-stu-id="6f0e0-133">Configuration and Metadata Support</span></span>](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [<span data-ttu-id="6f0e0-134">Configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-134">Configuration</span></span>](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [<span data-ttu-id="6f0e0-135">Procedura: Specificare un'associazione al servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-135">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="6f0e0-136">Procedura: creare un Endpoint del servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-136">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [<span data-ttu-id="6f0e0-137">Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="6f0e0-138">Procedura: Specificare un'associazione al client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="6f0e0-138">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
