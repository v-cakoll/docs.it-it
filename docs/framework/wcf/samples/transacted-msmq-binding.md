---
title: Associazioni MSMQ transazionali
ms.date: 03/30/2017
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
ms.openlocfilehash: fa53099caba144f321698f180fe18f7614a1fa64
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596565"
---
# <a name="transacted-msmq-binding"></a><span data-ttu-id="3a3e9-102">Associazioni MSMQ transazionali</span><span class="sxs-lookup"><span data-stu-id="3a3e9-102">Transacted MSMQ Binding</span></span>

<span data-ttu-id="3a3e9-103">Questo esempio illustra come eseguire comunicazioni in coda transazionali utilizzando Accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="3a3e9-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>

> [!NOTE]
> <span data-ttu-id="3a3e9-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="3a3e9-105">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-105">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="3a3e9-106">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-106">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="3a3e9-107">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-107">The service receives messages from the queue.</span></span> <span data-ttu-id="3a3e9-108">Di conseguenza, per comunicare mediante una coda, il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-108">The service and client, therefore, do not have to be running at the same time to communicate using a queue.</span></span>

<span data-ttu-id="3a3e9-109">Quando vengono utilizzate transazioni per inviare e ricevere messaggi, di fatto vi sono due transazioni distinte.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-109">When transactions are used to send and receive messages, there are actually two separate transactions.</span></span> <span data-ttu-id="3a3e9-110">Quando il client invia messaggi all'interno dell'ambito di una transazione, questa è locale per il client e il gestore delle code client.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-110">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="3a3e9-111">Quando il servizio riceve messaggi all'interno dell'ambito di una transazione, questa è locale per il servizio e il gestore delle code di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-111">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="3a3e9-112">È molto importante ricordare che il client e il servizio non partecipano alla stessa transazione; essi utilizzano invece transazioni diverse per le operazioni con la coda, quali l'invio e la ricezione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-112">It is very important to remember that the client and the service are not participating in the same transaction; rather, they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>

<span data-ttu-id="3a3e9-113">In questo esempio, il client invia un batch di messaggi al servizio dall'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-113">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="3a3e9-114">I messaggi inviati alla coda vengono quindi ricevuti dal servizio fra l'ambito della transazione definito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-114">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span>

<span data-ttu-id="3a3e9-115">Il contratto del servizio è `IOrderProcessor`, come mostrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-115">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span> <span data-ttu-id="3a3e9-116">L'interfaccia definisce un servizio unidirezionale adatto per l'utilizzo con le code.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-116">The interface defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

<span data-ttu-id="3a3e9-117">Il comportamento del servizio definisce un comportamento dell'operazione con `TransactionScopeRequired` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-117">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="3a3e9-118">Questo assicura che lo stesso ambito della transazione che viene usato per recuperare il messaggio dalla coda sia usato da tutti i gestori di risorse ai quali accede il metodo.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-118">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="3a3e9-119">Garantisce anche che se il metodo genera un'eccezione, il messaggio viene restituito alla coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-119">It also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="3a3e9-120">Senza impostare questo comportamento dell'operazione, un canale in coda crea una transazione per leggere il messaggio dalla coda e ne esegue automaticamente il commit prima dell'invio in modo che se l'operazione non riesce, il messaggio va perduto.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-120">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before dispatch such that if the operation fails, the message is lost.</span></span> <span data-ttu-id="3a3e9-121">Lo scenario più comune per le operazioni del servizio è di inserirsi nella transazione che viene utilizzata per leggere il messaggio dalla coda, come dimostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-121">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue, as demonstrated in the following code.</span></span>

```csharp
 // This service class that implements the service contract.
 // This added code writes output to the console window.
 public class OrderProcessorService : IOrderProcessor
 {
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
     public void SubmitPurchaseOrder(PurchaseOrder po)
     {
         Orders.Add(po);
         Console.WriteLine("Processing {0} ", po);
     }
  …
}
```

<span data-ttu-id="3a3e9-122">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-122">The service is self hosted.</span></span> <span data-ttu-id="3a3e9-123">Quando si usa il trasporto MSMQ, la coda usata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-123">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="3a3e9-124">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-124">This can be done manually or through code.</span></span> <span data-ttu-id="3a3e9-125">In questo esempio, il servizio contiene il codice necessario per verificare l'esistenza della coda e crearla se necessario.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-125">In this sample, the service contains code to check for the existence of the queue and create the queue if it does not exist.</span></span> <span data-ttu-id="3a3e9-126">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-126">The queue name is read from the configuration file.</span></span> <span data-ttu-id="3a3e9-127">L'indirizzo di base viene utilizzato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il proxy per il servizio.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-127">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get the MSMQ queue name from appSettings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);

    // Create a ServiceHost for the OrderProcessorService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shut down the service.
        serviceHost.Close();
    }
}
```

<span data-ttu-id="3a3e9-128">Il nome della coda MSMQ viene specificato in una sezione appSettings del file di configurazione, come mostra la configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-128">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="3a3e9-129">Il nome della coda usa un punto (.) per il computer locale e barre rovesciate come separatori all'interno del percorso quando la coda viene creata usando <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-129">The queue name uses a dot (.) for the local computer and backslash separators in its path when creating the queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="3a3e9-130">L'endpoint Windows Communication Foundation (WCF) utilizza l'indirizzo della coda con lo schema net. MSMQ, utilizza "localhost" per indicare il computer locale e utilizza le barre nel percorso.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-130">The Windows Communication Foundation (WCF) endpoint uses the queue address with net.msmq scheme, uses "localhost" to denote the local computer, and uses forward slashes in its path.</span></span>

<span data-ttu-id="3a3e9-131">Il client crea un ambito di transazione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-131">The client creates a transaction scope.</span></span> <span data-ttu-id="3a3e9-132">La comunicazione con la coda avviene all'interno dell'ambito della transazione, facendo in modo che venga trattata come unità atomica nella quale alla coda vengono inviati tutti i messaggi o nessuno.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-132">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="3a3e9-133">Il commit della transazione viene eseguito chiamando <xref:System.Transactions.TransactionScope.Complete%2A> nell'ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-133">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>

```csharp
// Create a client.
OrderProcessorClient client = new OrderProcessorClient();

// Create the purchase order.
PurchaseOrder po = new PurchaseOrder();
po.CustomerId = "somecustomer.com";
po.PONumber = Guid.NewGuid().ToString();

PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
lineItem1.ProductId = "Blue Widget";
lineItem1.Quantity = 54;
lineItem1.UnitCost = 29.99F;

PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
lineItem2.ProductId = "Red Widget";
lineItem2.Quantity = 890;
lineItem2.UnitCost = 45.89F;

po.orderLineItems = new PurchaseOrderLineItem[2];
po.orderLineItems[0] = lineItem1;
po.orderLineItems[1] = lineItem2;

// Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    // Make a queued call to submit the purchase order.
    client.SubmitPurchaseOrder(po);
    // Complete the transaction.
    scope.Complete();
}

// Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="3a3e9-134">Per verificare che le transazioni stiano funzionando, modificare il client impostando l'ambito della transazione come commento, come mostra il codice di esempio seguente, ricompilare la soluzione ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-134">To verify that transactions are working, modify the client by commenting the transaction scope as shown in the following sample code, rebuild the solution, and run the client.</span></span>

```csharp
//scope.Complete();
```

<span data-ttu-id="3a3e9-135">Poiché la transazione non è stata completata, i messaggi non vengono inviati alla coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-135">Because the transaction is not completed, the messages are not sent to the queue.</span></span>

<span data-ttu-id="3a3e9-136">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-136">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="3a3e9-137">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-137">You can see the service receive messages from the client.</span></span> <span data-ttu-id="3a3e9-138">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-138">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="3a3e9-139">Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-139">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="3a3e9-140">È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-140">You can run the client, shut it down, and then start up the service and it still receives the messages.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3a3e9-141">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3a3e9-141">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3a3e9-142">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a3e9-142">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3a3e9-143">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-143">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="3a3e9-144">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-144">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="3a3e9-145">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-145">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="3a3e9-146">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-146">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="3a3e9-147">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-147">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="3a3e9-148">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="3a3e9-148">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="3a3e9-149">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-149">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="3a3e9-150">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="3a3e9-150">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="3a3e9-151">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-151">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="3a3e9-152">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a3e9-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="3a3e9-153">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3a3e9-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

<span data-ttu-id="3a3e9-154">Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="3a3e9-155">Nell'associazione sono presenti due proprietà importanti per la sicurezza del trasporto MSMQ: <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> e <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-155">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span></span> <span data-ttu-id="3a3e9-156">Per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-156">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="3a3e9-157">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-157">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the Active Directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="3a3e9-158">Se si esegue questo esempio in un computer che non soddisfa questi criteri, si riceve un errore.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-158">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="3a3e9-159">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro o privo di integrazione con Active Directory</span><span class="sxs-lookup"><span data-stu-id="3a3e9-159">To run the sample on a computer joined to a workgroup or without Active Directory integration</span></span>

1. <span data-ttu-id="3a3e9-160">Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nel codice di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-160">If your computer is not part of a domain or does not have Active Directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code.</span></span>

    ```xml
    <system.serviceModel>
      <services>
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"
                 behaviorConfiguration="OrderProcessorServiceBehavior">
          <host>
            <baseAddresses>
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
            </baseAddresses>
          </host>
          <!-- Define NetMsmqEndpoint. -->
          <endpoint
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"
              binding="netMsmqBinding"
              bindingConfiguration="Binding1"
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
          <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
          <endpoint address="mex"
                    binding="mexHttpBinding"
                    contract="IMetadataExchange" />
        </service>
      </services>

      <bindings>
        <netMsmqBinding>
          <binding name="Binding1">
            <security mode="None" />
          </binding>
        </netMsmqBinding>
      </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="OrderProcessorServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. <span data-ttu-id="3a3e9-161">Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-161">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a3e9-162">L'impostazione di `security mode` su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-162">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a3e9-163">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-163">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3a3e9-164">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-164">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3a3e9-165">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3a3e9-166">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3a3e9-166">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`
