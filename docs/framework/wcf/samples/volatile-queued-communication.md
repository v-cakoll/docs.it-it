---
title: Comunicazione volatile in coda
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: a9f7e8a96fd293c7f87cc19846a42a42f28de288
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602343"
---
# <a name="volatile-queued-communication"></a><span data-ttu-id="b665b-102">Comunicazione volatile in coda</span><span class="sxs-lookup"><span data-stu-id="b665b-102">Volatile Queued Communication</span></span>

<span data-ttu-id="b665b-103">In questo esempio viene illustrato come eseguire la comunicazione volatile in coda sul trasporto dell'accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b665b-103">This sample demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="b665b-104">Nell'esempio viene utilizzato <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="b665b-104">This sample uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="b665b-105">Il servizio, in questo caso, è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="b665b-105">The service in this case is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="b665b-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b665b-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="b665b-107">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="b665b-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="b665b-108">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="b665b-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="b665b-109">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="b665b-109">The service receives messages from the queue.</span></span> <span data-ttu-id="b665b-110">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b665b-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="b665b-111">Quando si invia un messaggio senza garanzie, MSMQ esegue tutti i tentativi possibili per recapitare il messaggio, mentre se si utilizzano le garanzie "una sola volta" MSMQ assicura che il messaggio venga recapitato oppure, se ciò non è possibile, notifica all'utente che il messaggio non può essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="b665b-111">When you send a message with no assurances, MSMQ only makes a best effort to deliver the message, unlike with Exactly Once assurances where MSMQ ensures that the message gets delivered or, if it cannot be delivered, lets you know that the message cannot be delivered.</span></span>

<span data-ttu-id="b665b-112">In alcuni scenari può essere necessario inviare un messaggio volatile senza garanzia su una coda, ad esempio quando il recapito tempestivo ha la priorità rispetto all'eventualità di perdere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b665b-112">In certain scenarios, you may want to send a volatile message with no assurances over a queue, when timely delivery is more important than losing messages.</span></span> <span data-ttu-id="b665b-113">Se il gestore delle code si arresta in modo anomalo, i messaggi volatili andranno persi.</span><span class="sxs-lookup"><span data-stu-id="b665b-113">Volatile messages do not survive queue manager crashes.</span></span> <span data-ttu-id="b665b-114">Pertanto se il gestore delle code si arresta in modo anomalo, la coda non transazionale utilizzata per archiviare i messaggi volatili resta attiva ma i messaggi stessi vengono persi perché non sono archiviati sul disco.</span><span class="sxs-lookup"><span data-stu-id="b665b-114">Therefore if the queue manager crashes, the non-transactional queue used to store volatile messages survives but the messages themselves do not because the messages are not stored on the disk.</span></span>

> [!NOTE]
> <span data-ttu-id="b665b-115">Non è possibile inviare messaggi volatili senza garanzie all'interno dell'ambito di una transazione utilizzando MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b665b-115">You cannot send volatile messages with no assurances within the scope of a transaction using MSMQ.</span></span> <span data-ttu-id="b665b-116">È necessario creare anche una coda non transazionale per inviare messaggi volatili.</span><span class="sxs-lookup"><span data-stu-id="b665b-116">You also must create a non-transactional queue to send volatile messages.</span></span>

<span data-ttu-id="b665b-117">Il contratto di servizio in questo esempio è `IStockTicker` che definisce servizi unidirezionali particolarmente indicati per l'utilizzo con l'accodamento.</span><span class="sxs-lookup"><span data-stu-id="b665b-117">The service contract in this sample is `IStockTicker` that defines one-way services that are best suited for use with queuing.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

<span data-ttu-id="b665b-118">L'operazione del servizio visualizza il simbolo e il prezzo del ticket delle azioni, come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b665b-118">The service operation displays the stock ticker symbol and price, as shown in the following sample code:</span></span>

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

<span data-ttu-id="b665b-119">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="b665b-119">The service is self hosted.</span></span> <span data-ttu-id="b665b-120">Quando si usa il trasporto MSMQ, la coda usata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="b665b-120">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="b665b-121">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="b665b-121">This can be done manually or through code.</span></span> <span data-ttu-id="b665b-122">In questo esempio, il servizio contiene il codice necessario per verificare l'esistenza della coda e crearla, se necessario.</span><span class="sxs-lookup"><span data-stu-id="b665b-122">In this sample, the service contains code to check for the existence of the queue and create it if required.</span></span> <span data-ttu-id="b665b-123">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b665b-123">The queue name is read from the configuration file.</span></span> <span data-ttu-id="b665b-124">L'indirizzo di base viene utilizzato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il proxy per il servizio.</span><span class="sxs-lookup"><span data-stu-id="b665b-124">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy for the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shutdown the service.
        serviceHost.Close();
    }
}
```

<span data-ttu-id="b665b-125">Il nome della coda MSMQ è specificato nella sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b665b-125">The MSMQ queue name is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="b665b-126">L'endpoint per il servizio è definito nella sezione system.serviceModel del file di configurazione e specifica l'associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="b665b-126">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>

> [!NOTE]
> <span data-ttu-id="b665b-127">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso quando la coda viene creata usando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="b665b-127">The queue name uses a dot (.) for the local machine and backslash separators in its path when creating a queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="b665b-128">L'indirizzo dell'endpoint Windows Communication Foundation (WCF) specifica uno schema net. MSMQ:, utilizza "localhost" per il computer locale e le barre nel percorso.</span><span class="sxs-lookup"><span data-stu-id="b665b-128">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine and forward slashes in its path.</span></span>

<span data-ttu-id="b665b-129">Anche le garanzie e la durabilità o volatilità dei messaggi sono specificate nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="b665b-129">The assurances and durability or volatility of messages are also specified in the configuration.</span></span>

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

<span data-ttu-id="b665b-130">Poiché nell'esempio vengono inviati messaggi in coda utilizzando una coda non transazionale, i messaggi sottoposti a transazione non possono essere inviati alla coda.</span><span class="sxs-lookup"><span data-stu-id="b665b-130">Because the sample sends queued messages by using a non-transactional queue, transacted messages cannot be sent to the queue.</span></span>

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

<span data-ttu-id="b665b-131">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="b665b-131">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="b665b-132">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="b665b-132">You can see the service receive messages from the client.</span></span> <span data-ttu-id="b665b-133">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="b665b-133">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="b665b-134">Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b665b-134">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="b665b-135">È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b665b-135">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b665b-136">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b665b-136">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="b665b-137">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b665b-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="b665b-138">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b665b-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="b665b-139">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b665b-139">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

<span data-ttu-id="b665b-140">Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata.</span><span class="sxs-lookup"><span data-stu-id="b665b-140">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="b665b-141">Esistono due proprietà pertinenti per la sicurezza del trasporto MSMQ <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> e, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign` .</span><span class="sxs-lookup"><span data-stu-id="b665b-141">There are two pertinent properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="b665b-142">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b665b-142">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="b665b-143">Se si esegue questo esempio in un computer che non soddisfà questi criteri si riceve un errore.</span><span class="sxs-lookup"><span data-stu-id="b665b-143">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="b665b-144">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro o privo di integrazione con Active Directory</span><span class="sxs-lookup"><span data-stu-id="b665b-144">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>

1. <span data-ttu-id="b665b-145">Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nel codice di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="b665b-145">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code:</span></span>

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="b665b-146">Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="b665b-146">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b665b-147">L'impostazione di `security mode` su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="b665b-147">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b665b-148">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b665b-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b665b-149">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b665b-149">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b665b-150">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b665b-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b665b-151">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b665b-151">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
