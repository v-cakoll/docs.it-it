---
title: Host di servizi personalizzati
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 2aed557d1d045c08aed206660aa7b4b75ffe0e2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145072"
---
# <a name="custom-service-host"></a><span data-ttu-id="85e4c-102">Host di servizi personalizzati</span><span class="sxs-lookup"><span data-stu-id="85e4c-102">Custom Service Host</span></span>
<span data-ttu-id="85e4c-103">Questo esempio dimostra come usare un derivato personalizzato della classe <xref:System.ServiceModel.ServiceHost> per modificare il comportamento in fase di esecuzione di un servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-103">This sample demonstrates how to use a custom derivative of the <xref:System.ServiceModel.ServiceHost> class to alter the run-time behavior of a service.</span></span> <span data-ttu-id="85e4c-104">Questo approccio fornisce un'alternativa riusabile alla configurazione tradizionale di un gran numero di servizi.</span><span class="sxs-lookup"><span data-stu-id="85e4c-104">This approach provides a reusable alternative to configuring a large number of services in a common way.</span></span> <span data-ttu-id="85e4c-105">In questo esempio viene inoltre illustrato come impiegare la classe <xref:System.ServiceModel.Activation.ServiceHostFactory> per usare un ServiceHost personalizzato nell'ambiente di hosting Internet Information Services (IIS) o nel servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service).</span><span class="sxs-lookup"><span data-stu-id="85e4c-105">The sample also demonstrates how to use the <xref:System.ServiceModel.Activation.ServiceHostFactory> class to use a custom ServiceHost in the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85e4c-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="85e4c-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="85e4c-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="85e4c-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="85e4c-108">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="85e4c-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="85e4c-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="85e4c-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a><span data-ttu-id="85e4c-110">Informazioni sullo scenario</span><span class="sxs-lookup"><span data-stu-id="85e4c-110">About the scenario</span></span>
 <span data-ttu-id="85e4c-111">Per impedire la divulgazione involontaria di metadati del servizio potenzialmente sensibili, la configurazione predefinita per i servizi Windows Communication Foundation (WCF) disabilita la pubblicazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="85e4c-111">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="85e4c-112">Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-112">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
 <span data-ttu-id="85e4c-113">L'abilitazione della pubblicazione dei metadati per un gran numero di servizi comporta l'aggiunta degli stessi elementi di configurazione a ciascun singolo servizio, che produce una quantità elevata di informazioni di configurazione sostanzialmente uguali.</span><span class="sxs-lookup"><span data-stu-id="85e4c-113">Enabling metadata publishing for a large number of services involves adding the same configuration elements to each individual service, which results in a large amount of configuration information that is essentially the same.</span></span> <span data-ttu-id="85e4c-114">Come alternativa alla configurazione di ogni singolo servizio, è possibile scrivere il codice imperativo che consente la pubblicazione dei metadati una volta e riusare quindi tale codice su vari servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="85e4c-114">As an alternative to configuring each service individually, it is possible to write the imperative code that enables metadata publishing once and then reuse that code across several different services.</span></span> <span data-ttu-id="85e4c-115">Ciò viene ottenuto creando una nuova classe che viene derivata da <xref:System.ServiceModel.ServiceHost> ed esegue l'override del metodo `ApplyConfiguration`() per aggiungere imperativamente il comportamento di pubblicazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="85e4c-115">This is accomplished by creating a new class that derives from <xref:System.ServiceModel.ServiceHost> and overrides the `ApplyConfiguration`() method to imperatively add the metadata publishing behavior.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85e4c-116">Per maggior chiarezza, questo esempio illustra come creare un endpoint non protetto per la configurazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="85e4c-116">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="85e4c-117">Tali endpoint sono potenzialmente disponibili per utenti anonimi non autenticati e bisogna fare attenzione prima di distribuirli per garantire che la pubblicazione dei metadati di un servizio sia appropriata.</span><span class="sxs-lookup"><span data-stu-id="85e4c-117">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span>  
  
## <a name="implementing-a-custom-servicehost"></a><span data-ttu-id="85e4c-118">Implementazione di un ServiceHost personalizzato</span><span class="sxs-lookup"><span data-stu-id="85e4c-118">Implementing a custom ServiceHost</span></span>
 <span data-ttu-id="85e4c-119">La classe <xref:System.ServiceModel.ServiceHost> espone diversi metodi virtuali utili che possono essere sottoposti a override dagli eredi per modificare il comportamento di un servizio in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-119">The <xref:System.ServiceModel.ServiceHost> class exposes several useful virtual methods that inheritors can override to alter the run-time behavior of a service.</span></span> <span data-ttu-id="85e4c-120">Ad esempio, il metodo `ApplyConfiguration`() legge informazioni di configurazione del servizio dall'archivio di configurazione e modifica di conseguenza <xref:System.ServiceModel.Description.ServiceDescription> dell'host.</span><span class="sxs-lookup"><span data-stu-id="85e4c-120">For example, the `ApplyConfiguration`() method reads service configuration information from the configuration store and alters the host's <xref:System.ServiceModel.Description.ServiceDescription> accordingly.</span></span> <span data-ttu-id="85e4c-121">L'implementazione predefinita legge la configurazione dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-121">The default implementation reads configuration from the application’s configuration file.</span></span> <span data-ttu-id="85e4c-122">Le implementazioni personalizzate possono eseguire l'override di `ApplyConfiguration`() per alterare ulteriormente la <xref:System.ServiceModel.Description.ServiceDescription> usando codice imperativo o anche sostituire completamente l'archivio di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="85e4c-122">Custom implementations can override `ApplyConfiguration`() to further alter the <xref:System.ServiceModel.Description.ServiceDescription> using imperative code or even replace the default configuration store entirely.</span></span> <span data-ttu-id="85e4c-123">Ad esempio, per leggere la configurazione dell'endpoint di un servizio da un database anziché il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-123">For example, to read a service’s endpoint configuration from a database instead of the application’s configuration file.</span></span>  
  
 <span data-ttu-id="85e4c-124">In questo esempio si desidera compilare un ServiceHost personalizzato che aggiunge il ServiceMetadataBehavior, (il quale consente la pubblicazione di metadati) anche se questo comportamento non viene aggiunto in modo esplicito nel file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-124">In this sample, we want to build a custom ServiceHost that adds the ServiceMetadataBehavior, (which enables metadata publishing), even if this behavior is not explicitly added in the service’s configuration file.</span></span> <span data-ttu-id="85e4c-125">Per ottenere questo risultato, viene creata una nuova classe che eredita da <xref:System.ServiceModel.ServiceHost> ed esegue l'override di `ApplyConfiguration`().</span><span class="sxs-lookup"><span data-stu-id="85e4c-125">To accomplish this, we create a new class that inherits from <xref:System.ServiceModel.ServiceHost> and overrides `ApplyConfiguration`().</span></span>  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 <span data-ttu-id="85e4c-126">Poiché ogni configurazione fornita nel file di configurazione dell'applicazione non va ignorata, la prima operazione di override di `ApplyConfiguration`() è chiamare l'implementazione di base.</span><span class="sxs-lookup"><span data-stu-id="85e4c-126">Because we do not want to ignore any configuration that has been provided in the application’s configuration file, the first thing our override of `ApplyConfiguration`() does is call the base implementation.</span></span> <span data-ttu-id="85e4c-127">Dopo che questo metodo è stato completato, è possibile aggiungere in modo imperativo <xref:System.ServiceModel.Description.ServiceMetadataBehavior> alla descrizione usando il codice imperativo seguente.</span><span class="sxs-lookup"><span data-stu-id="85e4c-127">Once this method completes, we can imperatively add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> to the description using the following imperative code.</span></span>  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 <span data-ttu-id="85e4c-128">L'ultima operazione dell'override di `ApplyConfiguration`() è aggiungere l'endpoint di metadati predefinito.</span><span class="sxs-lookup"><span data-stu-id="85e4c-128">The last thing our `ApplyConfiguration`() override must do is add the default metadata endpoint.</span></span> <span data-ttu-id="85e4c-129">Per convenzione, viene creato uno endpoint di metadati per ciascun URI nella raccolta BaseAddresses del host del servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-129">By convention, one metadata endpoint is created for each URI in the service host’s BaseAddresses collection.</span></span>  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a><span data-ttu-id="85e4c-130">Uso di un ServiceHost personalizzato in host indipendente</span><span class="sxs-lookup"><span data-stu-id="85e4c-130">Using a custom ServiceHost in self-host</span></span>  
 <span data-ttu-id="85e4c-131">Ora che è stata completata l'implementazione personalizzata di ServiceHost, è possibile usarlo per aggiungere il comportamento di pubblicazione dei metadati a qualsiasi servizio ospitando tale servizio all'interno di un'istanza di `SelfDescribingServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="85e4c-131">Now that we have completed our custom ServiceHost implementation, we can use it to add metadata publishing behavior to any service by hosting that service inside of an instance of our `SelfDescribingServiceHost`.</span></span> <span data-ttu-id="85e4c-132">Nell'esempio di codice seguente viene illustrato come usarlo nello scenario di host indipendente.</span><span class="sxs-lookup"><span data-stu-id="85e4c-132">The following code shows how to use it in the self-host scenario.</span></span>  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 <span data-ttu-id="85e4c-133">L'host personalizzato legge comunque la configurazione dell'endpoint del servizio dal file di configurazione dell'applicazione, come se fosse stata usata la classe <xref:System.ServiceModel.ServiceHost> predefinita per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-133">Our custom host still reads the service’s endpoint configuration from the application’s configuration file, just as if we had used the default <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="85e4c-134">Tuttavia, poiché è stata aggiunta la logica per abilitare la pubblicazione dei metadati all'interno dell'host personalizzato, non è più necessario abilitare in modo esplicito il comportamento di pubblicazione dei metadati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-134">However, because we added the logic to enable metadata publishing inside of our custom host, we no longer must explicitly enable the metadata publishing behavior in configuration.</span></span> <span data-ttu-id="85e4c-135">L'approccio offre un vantaggio evidente quando si compila un'applicazione che contiene diversi servizi e si desidera abilitare la pubblicazione dei metadati su ognuno di essi senza riscrivere ripetutamente gli stessi elementi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="85e4c-135">This approach has a distinct advantage when you are building an application that contains several services and you want to enable metadata publishing on each of them without writing the same configuration elements over and over.</span></span>  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a><span data-ttu-id="85e4c-136">Utilizzo di un ServiceHost personalizzato in IIS e WAS</span><span class="sxs-lookup"><span data-stu-id="85e4c-136">Using a custom ServiceHost in IIS or WAS</span></span>  
 <span data-ttu-id="85e4c-137">L'uso di un host del servizio personalizzato in scenari di host indipendente è semplice in quanto spetta fondamentalmente al codice dell'applicazione la responsabilità di creare e aprire l'istanza dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-137">Using a custom service host in self-host scenarios is straightforward, because it is your application code that is ultimately responsible for creating and opening the service host instance.</span></span> <span data-ttu-id="85e4c-138">Nell'ambiente di hosting IIS o WAS, tuttavia, l'infrastruttura WCF crea dinamicamente un'istanza dell'host del servizio in risposta ai messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="85e4c-138">In the IIS or WAS hosting environment, however, the WCF infrastructure is dynamically instantiating your service’s host in response to incoming messages.</span></span> <span data-ttu-id="85e4c-139">Gli host del servizio personalizzati possono essere usati anche in questo ambiente di hosting, ma richiedono del codice aggiuntivo nel modulo di un ServiceHostFactory.</span><span class="sxs-lookup"><span data-stu-id="85e4c-139">Custom service hosts can also be used in this hosting environment, but they require some additional code in the form of a ServiceHostFactory.</span></span> <span data-ttu-id="85e4c-140">Nel codice seguente è illustrato un derivato di <xref:System.ServiceModel.Activation.ServiceHostFactory> che restituisce istanze del `SelfDescribingServiceHost` personalizzato.</span><span class="sxs-lookup"><span data-stu-id="85e4c-140">The following code shows a derivative of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns instances of our custom `SelfDescribingServiceHost`.</span></span>  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 <span data-ttu-id="85e4c-141">Come è possibile vedere, l'implementazione di un ServiceHostFactory personalizzato è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="85e4c-141">As you can see, implementing a custom ServiceHostFactory is very straightforward.</span></span> <span data-ttu-id="85e4c-142">Tutta la logica personalizzata risiede all'interno dell'implementazione ServiceHost; la factory restituisce un'istanza della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="85e4c-142">All of the custom logic resides inside of the ServiceHost implementation; the factory returns an instance of the derived class.</span></span>  
  
 <span data-ttu-id="85e4c-143">Per usare una factory personalizzata con un'implementazione del servizio, è necessario aggiungere altri metadati al file con estensione svc del servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-143">To use a custom factory with a service implementation, we must add some additional metadata to the service’s .svc file.</span></span>  
  
```xml
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 <span data-ttu-id="85e4c-144">Qui è stato aggiunto un altro attributo `Factory` alla direttiva `@ServiceHost` al quale è stato passato come valore il nome del tipo CLR della factory personalizzata.</span><span class="sxs-lookup"><span data-stu-id="85e4c-144">Here we have added an additional `Factory` attribute to the `@ServiceHost` directive, and passed the CLR type name of our custom factory as the attribute’s value.</span></span> <span data-ttu-id="85e4c-145">Quando IIS o WAS riceve un messaggio per questo servizio, l'infrastruttura di hosting WCF crea innanzitutto un'istanza di ServiceHostFactory e quindi crea un'istanza dell'host del servizio stesso chiamando `ServiceHostFactory.CreateServiceHost()`.</span><span class="sxs-lookup"><span data-stu-id="85e4c-145">When IIS or WAS receives a message for this service, the WCF hosting infrastructure first creates an instance of the ServiceHostFactory and then instantiate the service host itself by calling `ServiceHostFactory.CreateServiceHost()`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="85e4c-146">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="85e4c-146">Running the sample</span></span>  
 <span data-ttu-id="85e4c-147">Anche se questo esempio fornisce un'implementazione del client e del servizio completamente funzionante, l'obiettivo dell'esempio è illustrare come modificare il comportamento in fase di esecuzione di un servizio per mezzo di un host personalizzato eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e4c-147">Although this sample does provide a fully-functional client and service implementation, the point of the sample is to illustrate how to alter a service’s run-time behavior by means of a custom host., do the following steps:</span></span>  
  
### <a name="observe-the-effect-of-the-custom-host"></a><span data-ttu-id="85e4c-148">Osservare l'effetto dell'host personalizzato</span><span class="sxs-lookup"><span data-stu-id="85e4c-148">Observe the effect of the custom host</span></span>
  
1. <span data-ttu-id="85e4c-149">Aprire il file Web.config del servizio e osservare che non esiste alcuna configurazione che abiliti in modo esplicito i metadati per il servizio.</span><span class="sxs-lookup"><span data-stu-id="85e4c-149">Open the service's Web.config file and observe that there is no configuration explicitly enabling metadata for the service.</span></span>  
  
2. <span data-ttu-id="85e4c-150">Aprire il file con estensione svc @ServiceHost del servizio e osservare che la relativa direttiva contiene un attributo Factory che specifica il nome di un ServiceHostFactory personalizzato.</span><span class="sxs-lookup"><span data-stu-id="85e4c-150">Open the service's .svc file and observe that its @ServiceHost directive contains a Factory attribute that specifies the name of a custom ServiceHostFactory.</span></span>  
  
### <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="85e4c-151">Impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="85e4c-151">Set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="85e4c-152">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85e4c-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="85e4c-153">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85e4c-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="85e4c-154">Dopo aver compilato la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="85e4c-154">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="85e4c-155">La directory ServiceModelSamples dovrebbe ora essere visualizzata come applicazione IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="85e4c-155">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="85e4c-156">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85e4c-156">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

5. <span data-ttu-id="85e4c-157">Per rimuovere l'applicazione IIS 7.0, eseguire *Cleanup.bat*.</span><span class="sxs-lookup"><span data-stu-id="85e4c-157">To remove the IIS 7.0 application, run *Cleanup.bat*.</span></span>

## <a name="see-also"></a><span data-ttu-id="85e4c-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85e4c-158">See also</span></span>

- [<span data-ttu-id="85e4c-159">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="85e4c-159">How to: Host a WCF Service in IIS</span></span>](../feature-details/how-to-host-a-wcf-service-in-iis.md)
