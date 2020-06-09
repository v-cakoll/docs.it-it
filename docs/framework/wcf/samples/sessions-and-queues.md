---
title: Sessioni e code
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 425135b533b898cbc75464f50ce8a5e8f6550755
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584168"
---
# <a name="sessions-and-queues"></a><span data-ttu-id="351f6-102">Sessioni e code</span><span class="sxs-lookup"><span data-stu-id="351f6-102">Sessions and queues</span></span>

<span data-ttu-id="351f6-103">In questo esempio viene illustrato come inviare e ricevere una serie di messaggi correlati in una comunicazione in coda sul trasporto di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="351f6-103">This sample demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="351f6-104">In questo esempio viene usata l'associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="351f6-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="351f6-105">Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="351f6-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="351f6-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="351f6-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="351f6-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="351f6-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="351f6-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="351f6-109">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="351f6-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="351f6-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="351f6-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 <span data-ttu-id="351f6-111">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-111">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="351f6-112">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-112">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="351f6-113">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-113">The service receives messages from the queue.</span></span> <span data-ttu-id="351f6-114">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="351f6-114">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="351f6-115">A volte, un client invia una serie di messaggi correlati tra loro in un gruppo.</span><span class="sxs-lookup"><span data-stu-id="351f6-115">Sometimes, a client sends a set of messages that are related to each other in a group.</span></span> <span data-ttu-id="351f6-116">Quando i messaggi devono essere elaborati insieme o in un ordine specifico, è possibile utilizzare una coda per raggrupparli, in modo che vengano elaborati da una sola applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-116">When messages must be processed together or in a specified order, a queue can be used to group them together, for processing by a single receiving application.</span></span> <span data-ttu-id="351f6-117">Questo aspetto è particolarmente importante quando sono presenti molte applicazioni di destinazione in un gruppo di server ed è necessario assicurare che un gruppo di messaggi sia elaborato dalla stessa applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-117">This is particularly important when there are several receiving applications on a group of servers and it is necessary to ensure that a group of messages is processed by the same receiving application.</span></span> <span data-ttu-id="351f6-118">Le sessioni in coda sono un meccanismo utilizzato per inviare e ricevere una serie correlata di messaggi che devono essere elaborati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="351f6-118">Queued sessions are a mechanism used to send and receive a related set of messages that must get processed all at once.</span></span> <span data-ttu-id="351f6-119">Le sessioni in coda richiedono l'esibizione di questo modello da parte di una transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-119">Queued sessions require a transaction to exhibit this pattern.</span></span>  
  
 <span data-ttu-id="351f6-120">In questo esempio, il client invia una serie di messaggi al servizio durante una sessione all'interno dell'ambito di una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-120">In the sample, the client sends a number of messages to the service as part of a session within the scope of a single transaction.</span></span>  
  
 <span data-ttu-id="351f6-121">Il contratto di servizio è `IOrderTaker`che definisce un servizio unidirezionale adatto per l'uso con le code.</span><span class="sxs-lookup"><span data-stu-id="351f6-121">The service contract is `IOrderTaker`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="351f6-122">L'elemento <xref:System.ServiceModel.SessionMode> utilizzato nel contratto mostrato nel codice di esempio seguente indica che i messaggi fanno parte della sessione.</span><span class="sxs-lookup"><span data-stu-id="351f6-122">The <xref:System.ServiceModel.SessionMode> used in the contract shown in the following sample code indicates that the messages are part of the session.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 <span data-ttu-id="351f6-123">Il servizio definisce le operazioni del servizio in modo tale che la prima operazione si integri in una transazione ma non la completi automaticamente.</span><span class="sxs-lookup"><span data-stu-id="351f6-123">The service defines service operations in such a way that the first operation enlists in a transaction but does not automatically complete the transaction.</span></span> <span data-ttu-id="351f6-124">Le operazioni successive si integrano nella stessa transazione ma non la completano automaticamente.</span><span class="sxs-lookup"><span data-stu-id="351f6-124">Subsequent operations also enlist in the same transaction but do not automatically complete.</span></span> <span data-ttu-id="351f6-125">L'ultima operazione della sessione completa automaticamente la transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-125">The last operation in the session automatically completes the transaction.</span></span> <span data-ttu-id="351f6-126">In questo modo, la stessa transazione viene utilizzata per molte chiamate a operazioni nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="351f6-126">Thus, the same transaction is used for several operation invocations in the service contract.</span></span> <span data-ttu-id="351f6-127">Se una delle operazioni genera un'eccezione, viene eseguito il rollback della transazione e la sessione viene reinserita nella coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-127">If any of the operations throw an exception, then the transaction rolls back and the session is put back into the queue.</span></span> <span data-ttu-id="351f6-128">Al completamento dell'ultima operazione, viene eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-128">Upon successful completion of the last operation, the transaction is committed.</span></span> <span data-ttu-id="351f6-129">Il servizio utilizza `PerSession` come <xref:System.ServiceModel.InstanceContextMode> per ricevere tutti i messaggi in una sessione sulla stessa istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="351f6-129">The service uses `PerSession` as the <xref:System.ServiceModel.InstanceContextMode> to receive all messages in a session on the same instance of the service.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 <span data-ttu-id="351f6-130">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="351f6-130">The service is self hosted.</span></span> <span data-ttu-id="351f6-131">Quando si usa il trasporto MSMQ, la coda usata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="351f6-131">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="351f6-132">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="351f6-132">This can be done manually or through code.</span></span> <span data-ttu-id="351f6-133">In questo esempio, il servizio contiene il codice <xref:System.Messaging> necessario per verificare l'esistenza della coda e crearla se necessario.</span><span class="sxs-lookup"><span data-stu-id="351f6-133">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="351f6-134">Il nome della coda viene letto dal file di configurazione utilizzando la coda <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="351f6-134">The queue name is read from the configuration file using the <xref:System.Configuration.ConfigurationManager.AppSettings%2A> class.</span></span>  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
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

 <span data-ttu-id="351f6-135">Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="351f6-136">L'endpoint per il servizio è definito nella sezione system.serviceModel del file di configurazione e specifica l'associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="351f6-136">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="351f6-137">Il client crea un ambito di transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-137">The client creates a transaction scope.</span></span> <span data-ttu-id="351f6-138">Tutti i messaggi nella sessione vengono inviati alla coda nell'ambito della transazione, facendo in modo che venga trattata come un unità atomica nella quale tutti i messaggi riescono o meno.</span><span class="sxs-lookup"><span data-stu-id="351f6-138">All messages in the session are sent to the queue within the transaction scope, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="351f6-139">Il commit della transazione viene eseguito chiamando <xref:System.Transactions.TransactionScope.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="351f6-139">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A>.</span></span>  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> <span data-ttu-id="351f6-140">È possibile utilizzare solo una transazione per tutti i messaggi della sessione e tutti i messaggi della sessione devono essere inviati prima di eseguire il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="351f6-140">You can use only a single transaction for all messages in the session and all messages in the session must be sent before committing the transaction.</span></span> <span data-ttu-id="351f6-141">La chiusura del client chiude la sessione.</span><span class="sxs-lookup"><span data-stu-id="351f6-141">Closing the client closes the session.</span></span> <span data-ttu-id="351f6-142">Pertanto, il client deve essere chiuso prima che la transazione sia completata per inviare tutti i messaggi della sessione alla coda.</span><span class="sxs-lookup"><span data-stu-id="351f6-142">Therefore, the client has to be closed before the transaction is completed to send all messages in the session to the queue.</span></span>  
  
 <span data-ttu-id="351f6-143">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="351f6-143">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="351f6-144">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="351f6-144">You can see the service receive messages from the client.</span></span> <span data-ttu-id="351f6-145">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="351f6-145">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="351f6-146">Poiché viene usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="351f6-146">Because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="351f6-147">È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="351f6-147">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>  
  
 <span data-ttu-id="351f6-148">Nel client.</span><span class="sxs-lookup"><span data-stu-id="351f6-148">On the client.</span></span>  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="351f6-149">Nel servizio.</span><span class="sxs-lookup"><span data-stu-id="351f6-149">On the service.</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="351f6-150">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="351f6-150">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="351f6-151">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="351f6-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="351f6-152">Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="351f6-152">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="351f6-153">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="351f6-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
 <span data-ttu-id="351f6-154">Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata.</span><span class="sxs-lookup"><span data-stu-id="351f6-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="351f6-155">Esistono due proprietà rilevanti per la sicurezza del trasporto MSMQ e, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> per <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign` .</span><span class="sxs-lookup"><span data-stu-id="351f6-155">There are two relevant properties for MSMQ transport security namely, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="351f6-156">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ.</span><span class="sxs-lookup"><span data-stu-id="351f6-156">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="351f6-157">Se si esegue questo esempio in un computer che non soddisfa questi criteri, si riceve un errore.</span><span class="sxs-lookup"><span data-stu-id="351f6-157">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>  
  
### <a name="run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="351f6-158">Eseguire l'esempio in un computer aggiunto a un gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="351f6-158">Run the sample on a computer joined to a workgroup</span></span>  
  
1. <span data-ttu-id="351f6-159">Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="351f6-159">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
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
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="351f6-160">Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="351f6-160">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="351f6-161">L'impostazione della modalità di sicurezza su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> e della sicurezza di `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="351f6-161">Setting security mode to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
