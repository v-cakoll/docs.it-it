---
title: Configurazione dei servizi WCF nel codice
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 4ff49b4e17ae179426cc033a955ecf2c71f2a3e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174810"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="84feb-102">Configurazione dei servizi WCF nel codice</span><span class="sxs-lookup"><span data-stu-id="84feb-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="84feb-103">Windows Communication Foundation (WCF) consente agli sviluppatori di configurare i servizi utilizzando i file di configurazione o il codice.</span><span class="sxs-lookup"><span data-stu-id="84feb-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="84feb-104">I file di configurazione sono utili quando è necessario configurare un servizio dopo la relativa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="84feb-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="84feb-105">Quando si utilizzano i file di configurazione, un professionista IT deve solo aggiornare il file di configurazione. Non è necessario eseguire la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="84feb-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="84feb-106">I file di configurazione, tuttavia, possono risultare complessi e difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="84feb-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="84feb-107">Non è disponibile alcun supporto per il debug dei file di configurazione e, poiché il riferimento agli elementi di configurazione viene fatto in base ai nomi, i file di configurazione della creazione possono risultare difficili e soggetti a errori.</span><span class="sxs-lookup"><span data-stu-id="84feb-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="84feb-108">WCF consente inoltre di configurare i servizi nel codice.</span><span class="sxs-lookup"><span data-stu-id="84feb-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="84feb-109">Nelle versioni precedenti di WCF (4.0 e versioni precedenti) la configurazione dei <xref:System.ServiceModel.ServiceHost> servizi nel codice era semplice in scenari self-hosted, la classe ha consentito di configurare gli endpoint e i comportamenti prima di chiamare ServiceHost.Open.In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span><span class="sxs-lookup"><span data-stu-id="84feb-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="84feb-110">Negli scenari ospitati dal Web, tuttavia, non è possibile accedere direttamente alla classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="84feb-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="84feb-111">Per configurare un servizio ospitato dal Web era necessario creare un oggetto `System.ServiceModel.ServiceHostFactory` che creava l'oggetto <xref:System.ServiceModel.Activation.ServiceHostFactory> ed effettuava qualsiasi configurazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="84feb-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="84feb-112">A partire da .NET 4.5.NET 4.5, WCF fornisce un modo più semplice per configurare i servizi ospitati sia self-hosted che web ospitati nel codice.</span><span class="sxs-lookup"><span data-stu-id="84feb-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="84feb-113">Metodo Configure</span><span class="sxs-lookup"><span data-stu-id="84feb-113">The Configure method</span></span>  
 <span data-ttu-id="84feb-114">Definire semplicemente un metodo statico pubblico denominato `Configure` con la firma seguente nella classe di implementazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="84feb-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="84feb-115">Il metodo Configure accetta un'istanza dell'oggetto <xref:System.ServiceModel.ServiceConfiguration> che consente allo sviluppatore di aggiungere endpoint e comportamenti.</span><span class="sxs-lookup"><span data-stu-id="84feb-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="84feb-116">Questo metodo viene chiamato da WCF prima dell'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="84feb-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="84feb-117">Una volta definito, tutte le impostazioni di configurazione del servizio specificate in un file app.config o web.config verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="84feb-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="84feb-118">Nel frammento di codice riportato di seguito viene illustrato come definire il metodo `Configure` e aggiungere un endpoint del servizio, un comportamento dell'endpoint e comportamenti del servizio:</span><span class="sxs-lookup"><span data-stu-id="84feb-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
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
            return $"You entered: {value}";
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
  
 <span data-ttu-id="84feb-119">Per abilitare un protocollo come HTTPS per un servizio, è possibile aggiungere in modo esplicito un endpoint che utilizza il protocollo oppure aggiungere automaticamente gli endpoint chiamando ServiceConfiguration.EnableProtocol(Binding) che aggiunge un endpoint per ogni indirizzo di base compatibile con il protocollo e ogni contratto di servizio definito.</span><span class="sxs-lookup"><span data-stu-id="84feb-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="84feb-120">Nel codice seguente viene illustrato come utilizzare il metodo ServiceConfiguration.EnableProtocol:</span><span class="sxs-lookup"><span data-stu-id="84feb-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
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
       config.EnableProtocol(new BasicHttpsBinding());
       config.EnableProtocol(new NetTcpBinding());
       config.EnableProtocol(new NetNamedPipeBinding());
       // add an extra BasicHttpBinding endpoint at http:///basic
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");
    }
}
```  
  
 <span data-ttu-id="84feb-121">Le impostazioni nella `protocolMappings` sezione> <vengono utilizzate solo se <xref:System.ServiceModel.ServiceConfiguration> non vengono aggiunti endpoint applicazione a livello di codice. Facoltativamente, è possibile caricare la configurazione del <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> servizio dal file di configurazione dell'applicazione predefinito chiamando e quindi modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="84feb-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="84feb-122">La classe <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> consente inoltre di caricare la configurazione da una configurazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="84feb-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="84feb-123">Nell'esempio di codice seguente viene illustrato come implementare questa azione:</span><span class="sxs-lookup"><span data-stu-id="84feb-123">The following code illustrates how to implement this:</span></span>  
  
```csharp
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
> <span data-ttu-id="84feb-124">Si <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> noti `host` che ignora <`service` impostazioni di `system.serviceModel`> all'interno del <> tag di <>.</span><span class="sxs-lookup"><span data-stu-id="84feb-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="84feb-125">Concettualmente, `host` <> riguarda la configurazione host, non la configurazione del servizio e viene caricata prima dell'esecuzione del metodo Configure.</span><span class="sxs-lookup"><span data-stu-id="84feb-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84feb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84feb-126">See also</span></span>

- [<span data-ttu-id="84feb-127">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-127">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="84feb-128">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="84feb-128">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
- [<span data-ttu-id="84feb-129">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="84feb-129">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="84feb-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-130">Configuration</span></span>](./samples/configuration-sample.md)
- [<span data-ttu-id="84feb-131">Attivazione basata sulla configurazione in IIS e WAS</span><span class="sxs-lookup"><span data-stu-id="84feb-131">Configuration-Based Activation in IIS and WAS</span></span>](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="84feb-132">Supporto di configurazione e metadati</span><span class="sxs-lookup"><span data-stu-id="84feb-132">Configuration and Metadata Support</span></span>](./extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="84feb-133">Configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-133">Configuration</span></span>](./diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="84feb-134">Procedura: Specificare un'associazione al servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-134">How to: Specify a Service Binding in Configuration</span></span>](how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="84feb-135">Procedura: creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-135">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="84feb-136">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-136">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="84feb-137">Procedura: Specificare un'associazione al client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="84feb-137">How to: Specify a Client Binding in Configuration</span></span>](how-to-specify-a-client-binding-in-configuration.md)
