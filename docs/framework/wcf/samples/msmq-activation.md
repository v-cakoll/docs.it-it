---
title: Attivazione MSMQ
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 805ab78908b4d1146cce94cac5357bafbb35c832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744797"
---
# <a name="msmq-activation"></a><span data-ttu-id="b0883-102">Attivazione MSMQ</span><span class="sxs-lookup"><span data-stu-id="b0883-102">MSMQ Activation</span></span>

<span data-ttu-id="b0883-103">In questo esempio viene illustrato come ospitare le applicazioni del servizio di attivazione dei processi di Windows (WAS) lette da una coda di messaggi.</span><span class="sxs-lookup"><span data-stu-id="b0883-103">This sample demonstrates how to host applications in Windows Process Activation Service (WAS) that are read from a message queue.</span></span> <span data-ttu-id="b0883-104">Questo esempio usa il `netMsmqBinding` e si basa sull'esempio di [comunicazione bidirezionale](../../../../docs/framework/wcf/samples/two-way-communication.md) .</span><span class="sxs-lookup"><span data-stu-id="b0883-104">This sample uses the `netMsmqBinding` and is based on the [Two-Way Communication](../../../../docs/framework/wcf/samples/two-way-communication.md) sample.</span></span> <span data-ttu-id="b0883-105">Il servizio in questo caso è un'applicazione ospitata su Web. Il client è indipendente e genera output sulla console per osservare lo stato degli ordini di acquisto inviati.</span><span class="sxs-lookup"><span data-stu-id="b0883-105">The service in this case is a Web-hosted application and the client is self-hosted and outputs to the console to observe the status of purchase orders submitted.</span></span>

> [!NOTE]
> <span data-ttu-id="b0883-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b0883-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="b0883-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b0883-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b0883-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b0883-108">Check for the following (default) directory before continuing.</span></span>
>
> <span data-ttu-id="b0883-109">\<Unitàinstallazione >: \ WF_WCF_Samples</span><span class="sxs-lookup"><span data-stu-id="b0883-109">\<InstallDrive>:\WF_WCF_Samples</span></span>
>
> <span data-ttu-id="b0883-110">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi relativi a WCF e [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0883-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all WCF and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0883-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b0883-111">This sample is located in the following directory.</span></span>
>
> <span data-ttu-id="b0883-112">\<Unitàinstallazione >: \Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span><span class="sxs-lookup"><span data-stu-id="b0883-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span></span>

<span data-ttu-id="b0883-113">Il servizio Attivazione processo Windows (WAS), il nuovo meccanismo di attivazione del processo per Windows Server 2008, fornisce funzionalità simili a IIS che in precedenza erano disponibili solo per applicazioni basate su HTTP per applicazioni che utilizzano protocolli non HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0883-113">Windows Process Activation Service (WAS), the new process activation mechanism for Windows Server 2008, provides IIS-like features that were previously only available to HTTP-based applications to applications that use non-HTTP protocols.</span></span> <span data-ttu-id="b0883-114">Windows Communication Foundation (WCF) utilizza l'interfaccia dell'adattatore listener per comunicare le richieste di attivazione ricevute tramite i protocolli non HTTP supportati da WCF, ad esempio TCP, named pipe e MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b0883-114">Windows Communication Foundation (WCF) uses the Listener Adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, Named Pipes, and MSMQ.</span></span> <span data-ttu-id="b0883-115">La funzionalità per ricevere richieste su protocolli non HTTP viene ospitata dai servizi Windows gestiti in esecuzione su SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b0883-115">The functionality for receiving requests over non-HTTP protocols is hosted by managed Windows services running in SMSvcHost.exe.</span></span>

<span data-ttu-id="b0883-116">Il servizio di adattatore listener Net.Msmq (NetMsmqActivator) attiva le applicazioni in coda in base ai messaggi nella coda.</span><span class="sxs-lookup"><span data-stu-id="b0883-116">The Net.Msmq Listener Adapter service (NetMsmqActivator) activates queued applications based on messages in the queue.</span></span>

<span data-ttu-id="b0883-117">Il client invia ordini di acquisto al servizio dall'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-117">The client sends purchase orders to the service from within the scope of a transaction.</span></span> <span data-ttu-id="b0883-118">Il servizio riceve gli ordini in una transazione e li elabora.</span><span class="sxs-lookup"><span data-stu-id="b0883-118">The service receives the orders in a transaction and processes them.</span></span> <span data-ttu-id="b0883-119">Il servizio richiama il client con lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b0883-119">The service then calls back the client with the status of the order.</span></span> <span data-ttu-id="b0883-120">Per facilitare la comunicazione bidirezionale il client e il servizio usano entrambi code per accodare gli ordini di acquisto e lo stato degli ordini.</span><span class="sxs-lookup"><span data-stu-id="b0883-120">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>

<span data-ttu-id="b0883-121">Il contratto di servizio `IOrderProcessor` definisce operazioni del servizio unidirezionale che usano l'accodamento.</span><span class="sxs-lookup"><span data-stu-id="b0883-121">The service contract `IOrderProcessor` defines the one-way service operations that work with queuing.</span></span> <span data-ttu-id="b0883-122">L'operazione del servizio usa l'endpoint di risposta per inviare gli stati degli ordini al client.</span><span class="sxs-lookup"><span data-stu-id="b0883-122">The service operation uses the reply endpoint to send order statuses to the client.</span></span> <span data-ttu-id="b0883-123">L'indirizzo dell'endpoint di risposta è l'URI della coda usato per restituire lo stato dell'ordine al client.</span><span class="sxs-lookup"><span data-stu-id="b0883-123">The reply endpoint's address is the URI of the queue used to send the order status back to the client.</span></span> <span data-ttu-id="b0883-124">L'applicazione di elaborazione degli ordini implementa questo contratto.</span><span class="sxs-lookup"><span data-stu-id="b0883-124">The order processing application implements this contract.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

<span data-ttu-id="b0883-125">Il contratto di risposta a cui inviare lo stato dell'ordine è specificato dal client.</span><span class="sxs-lookup"><span data-stu-id="b0883-125">The reply contract to send order status to is specified by the client.</span></span> <span data-ttu-id="b0883-126">Il client implementa il contratto dello stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b0883-126">The client implements the order status contract.</span></span> <span data-ttu-id="b0883-127">Il servizio usa il client generato di questo contratto per restituire lo stato dell'ordine al client.</span><span class="sxs-lookup"><span data-stu-id="b0883-127">The service uses the generated client of this contract to send order status back to the client.</span></span>

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

<span data-ttu-id="b0883-128">L'operazione del servizio elabora l'ordine di acquisto inviato.</span><span class="sxs-lookup"><span data-stu-id="b0883-128">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="b0883-129"><xref:System.ServiceModel.OperationBehaviorAttribute> viene applicato all'operazione del servizio per specificare l'inserimento automatico nell'elenco nella transazione usata per ricevere il messaggio dalla coda e il completamento automatico della transazione al completamento dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="b0883-129">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in the transaction that is used to receive the message from the queue and automatic completion of the transaction on completion of the service operation.</span></span> <span data-ttu-id="b0883-130">La classe `Orders` incapsula la funzionalità di elaborazione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="b0883-130">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="b0883-131">In questo caso, aggiunge l'ordine di acquisto a un dizionario.</span><span class="sxs-lookup"><span data-stu-id="b0883-131">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="b0883-132">La transazione che l'operazione del servizio ha inserito nell'elenco è disponibile per le operazioni nella classe `Orders`.</span><span class="sxs-lookup"><span data-stu-id="b0883-132">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>

<span data-ttu-id="b0883-133">L'operazione del servizio, oltre a elaborare l'ordine di acquisto inviato, risponde al client in merito allo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b0883-133">The service operation, in addition to processing the submitted purchase order, replies back to the client about the status of the order.</span></span>

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

<span data-ttu-id="b0883-134">L'associazione client da usare viene specificata mediante un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-134">The client binding to use is specified using a configuration file.</span></span>

<span data-ttu-id="b0883-135">Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="b0883-136">L'endpoint per il servizio è definito nella sezione System.serviceModel del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-136">The endpoint for the service is defined in the System.serviceModel section of the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="b0883-137">Il nome della coda MSMQ e l'indirizzo endpoint usano convenzioni di indirizzamento leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="b0883-137">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="b0883-138">Nel nome della coda MSMQ viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="b0883-138">The MSMQ queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="b0883-139">L'indirizzo endpoint WCF specifica uno schema net. MSMQ:, utilizza "localhost" per il computer locale e utilizza le barre nel percorso.</span><span class="sxs-lookup"><span data-stu-id="b0883-139">The WCF endpoint address specifies a net.msmq: scheme, uses "localhost" for the local computer, and uses forward slashes in its path.</span></span> <span data-ttu-id="b0883-140">Per leggere da una coda ospitata sul computer remoto, sostituire "." e "localhost" con il nome computer remoto.</span><span class="sxs-lookup"><span data-stu-id="b0883-140">To read from a queue that is hosted on the remote computer, replace the "." and "localhost" to the remote computer name.</span></span>

<span data-ttu-id="b0883-141">Viene usato un file con estensione svc con il nome della classe per ospitare il codice del servizio in WAS.</span><span class="sxs-lookup"><span data-stu-id="b0883-141">A .svc file with the name of the class is used to host the service code in WAS.</span></span>

<span data-ttu-id="b0883-142">Il file Service.svc stesso contiene una direttiva per creare `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="b0883-142">The Service.svc file itself contains a directive to create the `OrderProcessorService`.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

<span data-ttu-id="b0883-143">Il file Service.svc contiene inoltre una direttiva assembly per garantire che System.Transactions.dll venga caricato.</span><span class="sxs-lookup"><span data-stu-id="b0883-143">The Service.svc file also contains an assembly directive to ensure that System.Transactions.dll is loaded.</span></span>

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

<span data-ttu-id="b0883-144">Il client crea un ambito di transazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-144">The client creates a transaction scope.</span></span> <span data-ttu-id="b0883-145">La comunicazione con il servizio avviene all'interno dell'ambito della transazione, la quale viene trattata come unità atomica nella quale tutti i messaggi hanno esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="b0883-145">Communication with the service takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="b0883-146">Il commit della transazione viene eseguito chiamando `Complete` nell'ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="b0883-146">The transaction is committed by calling `Complete` on the transaction scope.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

    // Create the purchase order
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

    //Create a transaction scope.
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

<span data-ttu-id="b0883-147">Il codice client implementa il contratto `IOrderStatus` per ricevere lo stato dell'ordine dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b0883-147">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="b0883-148">In questo caso, stampa lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b0883-148">In this case, it prints out the order status.</span></span>

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

<span data-ttu-id="b0883-149">La coda dello stato degli ordini viene creata nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="b0883-149">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="b0883-150">La configurazione del client comprende la configurazione del servizio di stato degli ordini per ospitare il servizio di stato degli ordini, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b0883-150">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

<span data-ttu-id="b0883-151">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del server e del client.</span><span class="sxs-lookup"><span data-stu-id="b0883-151">When you run the sample, the client and service activities are displayed in both the server and client console windows.</span></span> <span data-ttu-id="b0883-152">È possibile osservare che il server riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="b0883-152">You can see the server receive messages from the client.</span></span> <span data-ttu-id="b0883-153">Premere INVIO in tutte le finestre della console per arrestare il server e il client.</span><span class="sxs-lookup"><span data-stu-id="b0883-153">Press ENTER in each console window to shut down the server and client.</span></span>

<span data-ttu-id="b0883-154">Il client visualizza le informazioni sullo stato dell'ordine inviate dal server.</span><span class="sxs-lookup"><span data-stu-id="b0883-154">The client displays the order status information sent by the server:</span></span>

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0883-155">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b0883-155">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="b0883-156">Assicurarsi che IIS 7,0 sia installato, in quanto è necessario per l'attivazione di WAS.</span><span class="sxs-lookup"><span data-stu-id="b0883-156">Ensure that IIS 7.0 is installed, as it is required for WAS activation.</span></span>

2. <span data-ttu-id="b0883-157">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0883-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span> <span data-ttu-id="b0883-158">Inoltre, è necessario installare i componenti di attivazione non HTTP WCF:</span><span class="sxs-lookup"><span data-stu-id="b0883-158">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="b0883-159">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="b0883-159">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="b0883-160">Selezionare **programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b0883-160">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="b0883-161">Fare clic **su attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="b0883-161">Click **Turn Windows Features on or off**.</span></span>

    4. <span data-ttu-id="b0883-162">In **Riepilogo funzionalità**fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b0883-162">Under **Features Summary**, click **Add Features**.</span></span>

    5. <span data-ttu-id="b0883-163">Espandere il nodo **Microsoft .NET Framework 3,0** e controllare la funzionalità di **attivazione non http Windows Communication Foundation** .</span><span class="sxs-lookup"><span data-stu-id="b0883-163">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="b0883-164">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0883-164">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="b0883-165">Eseguire il client lanciando client.exe da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="b0883-165">Run the client by executing client.exe from a command window.</span></span> <span data-ttu-id="b0883-166">In questo modo verrà creata la coda e gli verrà inviato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="b0883-166">This creates the queue and sends a message to it.</span></span> <span data-ttu-id="b0883-167">Lasciare il client in esecuzione per vedere cosa succede quando il servizio legge il messaggio</span><span class="sxs-lookup"><span data-stu-id="b0883-167">Leave the client running to see the result of the service reading the message</span></span>

5. <span data-ttu-id="b0883-168">Il servizio di attivazione MSMQ viene eseguito come impostazione predefinita come Servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="b0883-168">The MSMQ activation service runs as Network Service by default.</span></span> <span data-ttu-id="b0883-169">Pertanto, la coda usata per attivare l'applicazione deve disporre delle autorizzazioni di ricezione e di lettura per il Servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="b0883-169">Therefore, the queue that is used to activate the application must have receive and peek permissions for Network Service.</span></span> <span data-ttu-id="b0883-170">Queste autorizzazioni possono essere aggiunte usando il sistema di accodamento messaggi MMC:</span><span class="sxs-lookup"><span data-stu-id="b0883-170">This can be added by using the Message Queuing MMC:</span></span>

    1. <span data-ttu-id="b0883-171">Dal menu **Start** fare clic su **Esegui**, quindi digitare `Compmgmt.msc` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b0883-171">From the **Start** menu, click **Run**, then type `Compmgmt.msc` and press ENTER.</span></span>

    2. <span data-ttu-id="b0883-172">In **Servizi e applicazioni**espandere **Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="b0883-172">Under **Services and Applications**, expand **Message Queuing**.</span></span>

    3. <span data-ttu-id="b0883-173">Fare clic su **code private**.</span><span class="sxs-lookup"><span data-stu-id="b0883-173">Click **Private Queues**.</span></span>

    4. <span data-ttu-id="b0883-174">Fare clic con il pulsante destro del mouse sulla coda (ServiceModelSamples/Service. svc) e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b0883-174">Right-click the queue (servicemodelsamples/Service.svc) and choose **Properties**.</span></span>

    5. <span data-ttu-id="b0883-175">Nella scheda **sicurezza** fare clic su **Aggiungi** e assegnare le autorizzazioni Visualizza e ricevi al servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="b0883-175">On the **Security** tab, click **Add** and give peek and receive permissions to Network Service.</span></span>

6. <span data-ttu-id="b0883-176">Configurare il servizio di attivazione dei processi di Windows (WAS) per supportare l'attivazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b0883-176">Configure the Windows Process Activation Service (WAS) to support MSMQ activation.</span></span>

    <span data-ttu-id="b0883-177">Per maggiore praticità, i passaggi seguenti vengono implementati in un file batch denominato AddMsmqSiteBinding.cmd posto nella directory degli esempi.</span><span class="sxs-lookup"><span data-stu-id="b0883-177">As a convenience, the following steps are implemented in a batch file called AddMsmqSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="b0883-178">Per supportare l'attivazione net.msmq, è innanzitutto necessario associare il sito Web predefinito al protocollo net.msmq.</span><span class="sxs-lookup"><span data-stu-id="b0883-178">To support net.msmq activation, the default Web site must first be bound to the net.msmq protocol.</span></span> <span data-ttu-id="b0883-179">A tale fine, usare appcmd.exe, installato con il set di strumenti di gestione di IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="b0883-179">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="b0883-180">Da un prompt dei comandi con privilegi elevati (amministratore), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b0883-180">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="b0883-181">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="b0883-181">This command is a single line of text.</span></span>

        <span data-ttu-id="b0883-182">Questo comando aggiunge un'associazione di sito net.msmq al sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="b0883-182">This command adds a net.msmq site binding to the default Web site.</span></span>

    2. <span data-ttu-id="b0883-183">Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.msmq comune, ognuna di esse può abilitare individualmente il supporto net.msmq.</span><span class="sxs-lookup"><span data-stu-id="b0883-183">Although all applications within a site share a common net.msmq binding, each application can enable net.msmq support individually.</span></span> <span data-ttu-id="b0883-184">Per abilitare net.msmq per l'applicazione /servicemodelsamples, eseguire il comando seguente da un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="b0883-184">To enable net.msmq for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > <span data-ttu-id="b0883-185">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="b0883-185">This command is a single line of text.</span></span>

        <span data-ttu-id="b0883-186">Questo comando consente di accedere all'applicazione/servicemodelsamples usando `http://localhost/servicemodelsamples` e `net.msmq://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="b0883-186">This command enables the /servicemodelsamples application to be accessed using `http://localhost/servicemodelsamples` and `net.msmq://localhost/servicemodelsamples`.</span></span>

7. <span data-ttu-id="b0883-187">Se in precedenza non è stato fatto, assicurarsi che il servizio di attivazione MSMQ sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="b0883-187">If you have not done so previously, ensure that the MSMQ activation service is enabled.</span></span> <span data-ttu-id="b0883-188">Dal menu **Start** fare clic su **esegui**e digitare `Services.msc`.</span><span class="sxs-lookup"><span data-stu-id="b0883-188">From the **Start** menu, click **Run**, and type `Services.msc`.</span></span> <span data-ttu-id="b0883-189">Eseguire una ricerca nell'elenco dei servizi per l' **adattatore listener Net. MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="b0883-189">Search the list of services for the **Net.Msmq Listener Adapter**.</span></span> <span data-ttu-id="b0883-190">Fare clic con il pulsante destro del mouse e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b0883-190">Right-click and select **Properties**.</span></span> <span data-ttu-id="b0883-191">Impostare **tipo di avvio** su **automatico**, fare clic su **applica** e fare clic sul pulsante **Avvia** .</span><span class="sxs-lookup"><span data-stu-id="b0883-191">Set the **Startup Type** to **Automatic**, click **Apply** and click the **Start** button.</span></span> <span data-ttu-id="b0883-192">È necessario eseguire questo passaggio solo la prima volta che si usa il servizio di adattatore listener Net.Msmq.</span><span class="sxs-lookup"><span data-stu-id="b0883-192">This step must only be done once prior to the first usage of the Net.Msmq Listener Adapter service.</span></span>

8. <span data-ttu-id="b0883-193">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0883-193">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="b0883-194">Modificare inoltre il codice nel client che invia l'ordine di acquisto in modo che corrisponda al nome del computer nell'URI della coda durante l'invio di ordini di acquisto.</span><span class="sxs-lookup"><span data-stu-id="b0883-194">Additionally, change the code on the client that submits the purchase order to reflect the computer name in the URI of the queue when submitting the purchase order.</span></span> <span data-ttu-id="b0883-195">Usare il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0883-195">Use the following code:</span></span>

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. <span data-ttu-id="b0883-196">Rimuovere l'associazione di sito net.msmq aggiunta per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="b0883-196">Remove the net.msmq site binding you added for this sample.</span></span>

    <span data-ttu-id="b0883-197">Per praticità, i passaggi seguenti vengono implementati in un file batch denominato RemoveMsmqSiteBinding.cmd posto nella directory degli esempi:</span><span class="sxs-lookup"><span data-stu-id="b0883-197">As a convenience, the following steps are implemented in a batch file called RemoveMsmqSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="b0883-198">Rimuovere net.msmq dall'elenco dei protocolli abilitati eseguendo il comando seguente da una finestra del prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="b0883-198">Remove net.msmq from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="b0883-199">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="b0883-199">This command is a single line of text.</span></span>

    2. <span data-ttu-id="b0883-200">Rimuovere l'associazione di sito net.msmq eseguendo il comando seguente da un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="b0883-200">Remove the net.msmq site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="b0883-201">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="b0883-201">This command is a single line of text.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b0883-202">L'esecuzione del file batch determinerà la reimpostazione di DefaultAppPool per l'esecuzione con .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="b0883-202">Running the batch file will reset the DefaultAppPool to run using .NET Framework version 2.0.</span></span>

<span data-ttu-id="b0883-203">Per impostazione predefinita con il trasporto dell'associazione `netMsmqBinding` è abilitata la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b0883-203">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="b0883-204">Il tipo di sicurezza del trasporto è determinato da due proprietà, `MsmqAuthenticationMode` e `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="b0883-204">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="b0883-205">Per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`.</span><span class="sxs-lookup"><span data-stu-id="b0883-205">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="b0883-206">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, deve appartenere a un dominio.</span><span class="sxs-lookup"><span data-stu-id="b0883-206">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="b0883-207">Se si esegue questo esempio in un computer che non appartiene a un dominio, si riceverà l'errore seguente: "Il certificato interno del servizio di accodamento messaggi non esiste".</span><span class="sxs-lookup"><span data-stu-id="b0883-207">If you run this sample on a computer that is not part of a domain, the following error is received: "User's internal message queuing certificate does not exist".</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="b0883-208">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="b0883-208">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="b0883-209">Se il computer non appartiene a un dominio, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su None, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="b0883-209">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to none as shown in the following sample configuration.</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. <span data-ttu-id="b0883-210">Modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="b0883-210">Change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0883-211">L'impostazione di `security mode` su `None` è equivalente all'impostazione di `MsmqAuthenticationMode`, `MsmqProtectionLevel` e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="b0883-211">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

3. <span data-ttu-id="b0883-212">Per abilitare l'attivazione su un computer che fa parte di un gruppo di lavoro, il servizio di attivazione e il processo di lavoro devono essere eseguiti con un account utente specifico (deve essere lo stesso per entrambi) e la coda deve essere dotata di ACL per l'account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="b0883-212">To enable activation in a computer joined to a workgroup, both the activation service and the worker process must be run with a specific user account (must be same for both) and the queue must have ACLs for the specific user account.</span></span>

     <span data-ttu-id="b0883-213">Per modificare l'identità con la quale viene eseguito il processo di lavoro:</span><span class="sxs-lookup"><span data-stu-id="b0883-213">To change the identity that the worker process runs under:</span></span>

    1. <span data-ttu-id="b0883-214">Eseguire Inetmgr.exe.</span><span class="sxs-lookup"><span data-stu-id="b0883-214">Run Inetmgr.exe.</span></span>

    2. <span data-ttu-id="b0883-215">In **pool di applicazioni**fare clic con il pulsante destro del mouse su **AppPool** (in genere **DefaultAppPool**) e scegliere **imposta impostazioni predefinite pool di applicazioni...** .</span><span class="sxs-lookup"><span data-stu-id="b0883-215">Under **Application Pools**, right-click the **AppPool** (typically **DefaultAppPool**) and choose **Set Application Pool Defaults…**.</span></span>

    3. <span data-ttu-id="b0883-216">Modificare le proprietà dell'identità per usare l'account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="b0883-216">Change the Identity properties to use the specific user account.</span></span>

     <span data-ttu-id="b0883-217">Per modificare l'identità con la quale viene eseguito il servizio di attivazione:</span><span class="sxs-lookup"><span data-stu-id="b0883-217">To change the identity that the Activation Service runs under:</span></span>

    1. <span data-ttu-id="b0883-218">Eseguire Services.msc.</span><span class="sxs-lookup"><span data-stu-id="b0883-218">Run Services.msc.</span></span>

    2. <span data-ttu-id="b0883-219">Fare clic con il pulsante destro del mouse sull' **Adapter NET. MsmqListener**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b0883-219">Right-click the **Net.MsmqListener Adapter**, and choose **Properties**.</span></span>

4. <span data-ttu-id="b0883-220">Modificare l'account nella scheda **Logon** .</span><span class="sxs-lookup"><span data-stu-id="b0883-220">Change the account in the **LogOn** tab.</span></span>

5. <span data-ttu-id="b0883-221">In un gruppo di lavoro è inoltre necessario che il servizio venga eseguito usando un token di accesso senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="b0883-221">In workgroup, the service must also run using an unrestricted token.</span></span> <span data-ttu-id="b0883-222">A tale scopo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b0883-222">To do this, run the following in a command window:</span></span>

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a><span data-ttu-id="b0883-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0883-223">See also</span></span>

- <span data-ttu-id="b0883-224">[Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b0883-224">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
