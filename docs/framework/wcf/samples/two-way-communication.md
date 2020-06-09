---
title: Comunicazione bidirezionale
ms.date: 03/30/2017
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
ms.openlocfilehash: 291380d656b0e22c7fdf1cb291c45d05359a95c8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591267"
---
# <a name="two-way-communication"></a><span data-ttu-id="4183c-102">Comunicazione bidirezionale</span><span class="sxs-lookup"><span data-stu-id="4183c-102">Two-Way Communication</span></span>
<span data-ttu-id="4183c-103">Questo esempio dimostra come eseguire comunicazioni transazionali bidirezionali in coda su MSQM.</span><span class="sxs-lookup"><span data-stu-id="4183c-103">This sample demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span> <span data-ttu-id="4183c-104">In questo esempio viene usata l'associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="4183c-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="4183c-105">In questo caso, il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="4183c-105">In this case, the service is a self-hosted console application that allows you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4183c-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4183c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4183c-107">Questo esempio è basato sull' [associazione MSMQ transazionale](transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="4183c-107">This sample is based on the [Transacted MSMQ Binding](transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="4183c-108">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="4183c-108">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="4183c-109">Il client invia messaggi a una coda e il servizio riceve i messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="4183c-109">The client sends messages to a queue, and the service receives messages from the queue.</span></span> <span data-ttu-id="4183c-110">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4183c-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="4183c-111">Questo esempio dimostra la comunicazione bidirezionale usando le code.</span><span class="sxs-lookup"><span data-stu-id="4183c-111">This sample demonstrates 2-way communication using queues.</span></span> <span data-ttu-id="4183c-112">Il client invia ordini di acquisto alla coda dall'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-112">The client sends purchase orders to the queue from within the scope of a transaction.</span></span> <span data-ttu-id="4183c-113">Il servizio riceve gli ordini, elabora l'ordine e quindi richiama il client con lo stato dell'ordine dalla coda all'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-113">The service receives the orders, processes the order and then calls back the client with the status of the order from the queue within the scope of a transaction.</span></span> <span data-ttu-id="4183c-114">Per facilitare la comunicazione bidirezionale il client e il servizio usano entrambi code per accodare gli ordini di acquisto e lo stato degli ordini.</span><span class="sxs-lookup"><span data-stu-id="4183c-114">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>  
  
 <span data-ttu-id="4183c-115">Il contratto di servizio `IOrderProcessor` definisce operazioni del servizio bidirezionale che sono adeguate all'accodamento.</span><span class="sxs-lookup"><span data-stu-id="4183c-115">The service contract `IOrderProcessor` defines one-way service operations that suit the use of queuing.</span></span> <span data-ttu-id="4183c-116">L'operazione del servizio include l'endpoint di risposta al qual e inviare gli stati degli ordini</span><span class="sxs-lookup"><span data-stu-id="4183c-116">The service operation includes the reply endpoint to use to send the order statuses to.</span></span> <span data-ttu-id="4183c-117">L'endpoint di risposta è URI della coda alla quale restituire lo stato dell'ordine per il client.</span><span class="sxs-lookup"><span data-stu-id="4183c-117">The reply endpoint is the URI of the queue to send the order status back to the client.</span></span> <span data-ttu-id="4183c-118">L'applicazione di elaborazione degli ordini implementa questo contratto.</span><span class="sxs-lookup"><span data-stu-id="4183c-118">The order processing application implements this contract.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string
                                  reportOrderStatusTo);  
}
```
  
 <span data-ttu-id="4183c-119">Il contratto di risposta per inviare lo stato dell'ordine è specificato dal client.</span><span class="sxs-lookup"><span data-stu-id="4183c-119">The reply contract to send order status is specified by the client.</span></span> <span data-ttu-id="4183c-120">Il client implementa il contratto dello stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="4183c-120">The client implements the order status contract.</span></span> <span data-ttu-id="4183c-121">Il servizio usa il proxy generato di questo contratto per restituire lo stato dell'ordine al client.</span><span class="sxs-lookup"><span data-stu-id="4183c-121">The service uses the generated proxy of this contract to send order status back to the client.</span></span>  

```csharp
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```

 <span data-ttu-id="4183c-122">L'operazione del servizio elabora l'ordine di acquisto inviato.</span><span class="sxs-lookup"><span data-stu-id="4183c-122">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="4183c-123"><xref:System.ServiceModel.OperationBehaviorAttribute> viene applicato all'operazione del servizio per specificare l'inserimento automatico nell'elenco in una transazione usata per ricevere il messaggio dalla coda e il completamento automatico delle transazioni al completamento dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="4183c-123">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in a transaction that is used to receive the message from the queue and automatic completion of transactions on completion of the service operation.</span></span> <span data-ttu-id="4183c-124">La classe `Orders` incapsula la funzionalità di elaborazione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="4183c-124">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="4183c-125">In questo caso, aggiunge l'ordine di acquisto a un dizionario.</span><span class="sxs-lookup"><span data-stu-id="4183c-125">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="4183c-126">La transazione che l'operazione del servizio ha inserito nell'elenco è disponibile per le operazioni nella classe `Orders`.</span><span class="sxs-lookup"><span data-stu-id="4183c-126">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>  
  
 <span data-ttu-id="4183c-127">L'operazione del servizio, oltre a elaborare l'ordine di acquisto inviato risponde al client in merito allo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="4183c-127">The service operation, in addition to processing the submitted purchase order, replies back to the client on the status of the order.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```

 <span data-ttu-id="4183c-128">Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-128">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="4183c-129">L'endpoint per il servizio è definito nella sezione System.ServiceModel del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-129">The endpoint for the service is defined in the System.ServiceModel section of the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4183c-130">Il nome della coda MSMQ e l'indirizzo endpoint usano convenzioni di indirizzamento leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="4183c-130">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="4183c-131">Nel nome della coda MSMQ viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="4183c-131">The MSMQ queue name uses a dot (.) for the local machine and backslash separators in its path.</span></span> <span data-ttu-id="4183c-132">L'indirizzo dell'endpoint Windows Communication Foundation (WCF) specifica uno schema net. MSMQ:, utilizza "localhost" per il computer locale e usa le barre nel percorso.</span><span class="sxs-lookup"><span data-stu-id="4183c-132">The Windows Communication Foundation (WCF) endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine, and uses forward slashes in its path.</span></span> <span data-ttu-id="4183c-133">Per leggere da una coda ospitata sul computer remoto, sostituire "." e "localhost" con il nome computer remoto.</span><span class="sxs-lookup"><span data-stu-id="4183c-133">To read from a queue that is hosted on the remote machine, replace the "." and "localhost" to the remote machine name.</span></span>  
  
 <span data-ttu-id="4183c-134">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="4183c-134">The service is self hosted.</span></span> <span data-ttu-id="4183c-135">Quando si usa il trasporto MSMQ, la coda usata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="4183c-135">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="4183c-136">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="4183c-136">This can be done manually or through code.</span></span> <span data-ttu-id="4183c-137">In questo esempio, il servizio verifica l'esistenza della coda e la crea se necessario.</span><span class="sxs-lookup"><span data-stu-id="4183c-137">In this sample, the service checks for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="4183c-138">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-138">The queue name is read from the configuration file.</span></span> <span data-ttu-id="4183c-139">L'indirizzo di base viene utilizzato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il proxy per il servizio.</span><span class="sxs-lookup"><span data-stu-id="4183c-139">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
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
    }  
}  
```

 <span data-ttu-id="4183c-140">Il client crea una transazione.</span><span class="sxs-lookup"><span data-stu-id="4183c-140">The client creates a transaction.</span></span> <span data-ttu-id="4183c-141">La comunicazione con la coda avviene all'interno dell'ambito della transazione, facendo in modo che venga trattata come unità atomica nella quale tutti i messaggi riescono o meno.</span><span class="sxs-lookup"><span data-stu-id="4183c-141">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span>  

```csharp
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```

 <span data-ttu-id="4183c-142">Il codice client implementa il contratto `IOrderStatus` per ricevere lo stato dell'ordine dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4183c-142">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="4183c-143">In questo caso, stampa lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="4183c-143">In this case, it prints out the order status.</span></span>  

```csharp
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,
                                                           status);  
    }  
}  
```

 <span data-ttu-id="4183c-144">La coda dello stato degli ordini viene creata nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="4183c-144">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="4183c-145">La configurazione del client comprende la configurazione del servizio di stato degli ordini per ospitare il servizio di stato degli ordini, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4183c-145">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
              binding="netMsmqBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="4183c-146">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="4183c-146">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="4183c-147">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="4183c-147">You can see the service receive messages from the client.</span></span> <span data-ttu-id="4183c-148">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="4183c-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="4183c-149">Il servizio visualizza le informazioni dell'ordine di acquisto e indica che restituisce lo stato dell'ordine alla coda di stato degli ordini.</span><span class="sxs-lookup"><span data-stu-id="4183c-149">The service displays the purchase order information and indicates it is sending back the order status to the order status queue.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 <span data-ttu-id="4183c-150">Il client visualizza le informazioni sullo stato dell'ordine inviate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4183c-150">The client displays the order status information sent by the service.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4183c-151">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4183c-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4183c-152">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4183c-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4183c-153">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4183c-153">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="4183c-154">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4183c-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4183c-155">Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare i nomi degli endpoint nella configurazione client in modo che corrisponda al codice client.</span><span class="sxs-lookup"><span data-stu-id="4183c-155">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint names in the client configuration to match the client code.</span></span>  
  
 <span data-ttu-id="4183c-156">Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4183c-156">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="4183c-157">Esistono due proprietà rilevanti per la sicurezza del trasporto MSMQ <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> e, per <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign` .</span><span class="sxs-lookup"><span data-stu-id="4183c-157">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="4183c-158">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4183c-158">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="4183c-159">Se si esegue questo esempio in un computer che non soddisfà questi criteri si riceve un errore.</span><span class="sxs-lookup"><span data-stu-id="4183c-159">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="4183c-160">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro o privo di integrazione con Active Directory</span><span class="sxs-lookup"><span data-stu-id="4183c-160">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1. <span data-ttu-id="4183c-161">Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4183c-161">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2. <span data-ttu-id="4183c-162">La disattivazione della sicurezza per una configurazione client genera quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4183c-162">Turning off security for a client configuration generates the following:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"
                    binding="netMsmqBinding"
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3. <span data-ttu-id="4183c-163">Il servizio per questo esempio crea un'associazione in `OrderProcessorService`.</span><span class="sxs-lookup"><span data-stu-id="4183c-163">The service for this sample creates a binding in the `OrderProcessorService`.</span></span> <span data-ttu-id="4183c-164">Aggiungere una riga di codice dopo la creazione dell'istanza dell'associazione per impostare la modalità di sicurezza su `None`.</span><span class="sxs-lookup"><span data-stu-id="4183c-164">Add a line of code after the binding is instantiated to set the security mode to `None`.</span></span>  
  
    ```csharp
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4. <span data-ttu-id="4183c-165">Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="4183c-165">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4183c-166">L'impostazione di `security mode` su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> o della sicurezza del `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="4183c-166">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> or `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4183c-167">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4183c-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4183c-168">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4183c-168">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="4183c-169">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4183c-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4183c-170">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4183c-170">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
