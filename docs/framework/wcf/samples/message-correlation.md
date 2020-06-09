---
title: Correlazione dei messaggi
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: 84b10b507f9fdaa7c53cf937bb132c8cc0aac33f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591644"
---
# <a name="message-correlation"></a><span data-ttu-id="d3c60-102">Correlazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d3c60-102">Message Correlation</span></span>

<span data-ttu-id="d3c60-103">In questo esempio viene illustrato come un'applicazione di Accodamento messaggi (MSMQ) può inviare un messaggio MSMQ a un servizio Windows Communication Foundation (WCF) e come i messaggi possono essere correlati tra applicazioni mittente e ricevitore in uno scenario di richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="d3c60-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="d3c60-104">In questo esempio viene utilizzata l'associazione msmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="d3c60-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="d3c60-105">Il servizio in questo caso è un'applicazione console self-hosted che consente di osservare il servizio che riceve i messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="d3c60-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="d3c60-106">k</span><span class="sxs-lookup"><span data-stu-id="d3c60-106">k</span></span>

 <span data-ttu-id="d3c60-107">Il servizio elabora il messaggio ricevuto dal mittente e invia un messaggio di risposta al mittente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="d3c60-108">Il mittente correla la risposta ricevuta alla richiesta inviata originariamente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="d3c60-109">Le proprietà `MessageID` e `CorrelationID` del messaggio vengono utilizzate per correlare i messaggi di richiesta e risposta.</span><span class="sxs-lookup"><span data-stu-id="d3c60-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>

 <span data-ttu-id="d3c60-110">Il contratto di servizio `IOrderProcessor` definisce un'operazione di servizio unidirezionale adatto per l'utilizzo con l'accodamento.</span><span class="sxs-lookup"><span data-stu-id="d3c60-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="d3c60-111">Un messaggio MSMQ non ha un'intestazione Action, pertanto non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi ai contratti dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="d3c60-112">Pertanto, in questo caso può essere presente un solo contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="d3c60-113">Se si desidera definire più contratti dell'operazione nel servizio, l'applicazione deve fornire informazioni in merito a quale intestazione nel messaggio MSMQ (ad esempio, l'etichetta o correlationID) può essere utilizzata per decidere quale contratto dell'operazione inviare.</span><span class="sxs-lookup"><span data-stu-id="d3c60-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="d3c60-114">Il messaggio MSMQ non contiene inoltre informazioni in merito alle intestazioni di cui è stato eseguito il mapping ai diversi parametri del contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-114">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="d3c60-115">Pertanto, può essere presente un solo parametro nel contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-115">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="d3c60-116">Il parametro è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> , che contiene il messaggio MSMQ sottostante.</span><span class="sxs-lookup"><span data-stu-id="d3c60-116">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, which contains the underlying MSMQ message.</span></span> <span data-ttu-id="d3c60-117">Il tipo "T" nella classe `MsmqMessage<T>` rappresenta i dati serializzati nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d3c60-117">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="d3c60-118">In questo esempio, il tipo `PurchaseOrder` è serializzato nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d3c60-118">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="d3c60-119">L'operazione del servizio elabora l'ordine di acquisto e ne visualizza il contenuto e lo stato nella finestra della console del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-119">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="d3c60-120"><xref:System.ServiceModel.OperationBehaviorAttribute> configura l'operazione per integrarsi in una transazione con la coda e contrassegnare la transazione come completa quando l'operazione viene restituita.</span><span class="sxs-lookup"><span data-stu-id="d3c60-120">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="d3c60-121">`PurchaseOrder` contiene i dettagli dell'ordine che deve essere elaborato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-121">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>

```csharp
// Service class that implements the service contract.
public class OrderProcessorService : IOrderProcessor
{
   [OperationBehavior(TransactionScopeRequired = true,
          TransactionAutoComplete = true)]
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)
   {
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;
       Random statusIndexer = new Random();
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
       Console.WriteLine("Processing {0} ", po);
       //Send a response to the client that the order has been received
         and is pending fullfillment.
       SendResponse(ordermsg);
    }

    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)
    {
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");

        //Set the correlation ID such that the client can correlate the response to the order.
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);
        orderResponsemsg.CorrelationId = ordermsg.Id;
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.SendOrderResponse(orderResponsemsg);
            scope.Complete();
        }

        client.Close();
    }
}
```

 <span data-ttu-id="d3c60-122">Il servizio utilizza un `OrderResponseClient` client personalizzato per inviare il messaggio MSMQ alla coda.</span><span class="sxs-lookup"><span data-stu-id="d3c60-122">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="d3c60-123">Poiché l'applicazione che riceve ed elabora il messaggio è un'applicazione MSMQ e non un'applicazione WCF, non esiste alcun contratto di servizio implicito tra le due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d3c60-123">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="d3c60-124">Pertanto, in questo scenario, non è possibile creare un proxy utilizzando lo strumento Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="d3c60-124">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="d3c60-125">Il proxy personalizzato è essenzialmente lo stesso per tutte le applicazioni WCF che utilizzano l' `msmqIntegrationBinding` associazione per inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="d3c60-125">The custom proxy is essentially the same for all WCF applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="d3c60-126">A differenza di altri proxy, non include una serie di operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-126">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="d3c60-127">È un'operazione di solo invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-127">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderResponse
{

    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse
{

    public OrderResponseClient()
    { }

    public OrderResponseClient(string configurationName)
        : base(configurationName)
    { }

    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SendOrderResponse(msg);
    }
}
```

 <span data-ttu-id="d3c60-128">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-128">The service is self hosted.</span></span> <span data-ttu-id="d3c60-129">Quando si utilizza il trasporto di integrazione MSMQ, la coda utilizzata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="d3c60-129">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="d3c60-130">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="d3c60-130">This can be done manually or through code.</span></span> <span data-ttu-id="d3c60-131">In questo esempio, il servizio contiene il codice <xref:System.Messaging> necessario per verificare l'esistenza della coda e crearla se necessario.</span><span class="sxs-lookup"><span data-stu-id="d3c60-131">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="d3c60-132">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-132">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
       // Get the MSMQ queue name from application settings in configuration.
      string queueName =
                ConfigurationManager.AppSettings["orderQueueName"];
      // Create the transacted MSMQ queue if necessary.
      if (!MessageQueue.Exists(queueName))
                MessageQueue.Create(queueName, true);
     // Create a ServiceHost for the OrderProcessorService type.
     using (ServiceHost serviceHost = new
                   ServiceHost(typeof(OrderProcessorService)))
     {
            serviceHost.Open();
            // The service can now be accessed.
            Console.WriteLine("The service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.ReadLine();
            // Close the ServiceHost to shutdown the service.
            serviceHost.Close();
      }
}
```

 <span data-ttu-id="d3c60-133">La coda MSMQ a cui vengono inviate le richieste dell'ordine viene specificata in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-133">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="d3c60-134">Gli endpoint del client e del servizio sono definiti nella sezione system.serviceModel del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3c60-134">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="d3c60-135">Entrambi specificano l'associazione `msmqIntegrationbinding`.</span><span class="sxs-lookup"><span data-stu-id="d3c60-135">Both specify the `msmqIntegrationbinding` binding.</span></span>

```xml
<appSettings>
  <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>

<system.serviceModel>
  <client>
    <endpoint    name="OrderResponseEndpoint"
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"
              binding="msmqIntegrationBinding"
              bindingConfiguration="OrderProcessorBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">
    </endpoint>
  </client>

  <services>
    <service
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"
                            binding="msmqIntegrationBinding"
                bindingConfiguration="OrderProcessorBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">
      </endpoint>
    </service>
  </services>

  <bindings>
    <msmqIntegrationBinding>
      <binding name="OrderProcessorBinding" >
        <security mode="None" />
      </binding>
    </msmqIntegrationBinding>
  </bindings>

</system.serviceModel>
```

 <span data-ttu-id="d3c60-136">L'applicazione client utilizza <xref:System.Messaging> per inviare un messaggio durevole e transazionale alla coda.</span><span class="sxs-lookup"><span data-stu-id="d3c60-136">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="d3c60-137">Il corpo del messaggio contiene l'ordine di acquisto.</span><span class="sxs-lookup"><span data-stu-id="d3c60-137">The message's body contains the purchase order.</span></span>

```csharp
static void PlaceOrder()
{
    //Connect to the queue
    MessageQueue orderQueue =
            new MessageQueue(
                    ConfigurationManager.AppSettings["orderQueueName"])
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

    Message msg = new Message();
    msg.UseDeadLetterQueue = true;
    msg.Body = po;

    //Create a transaction scope.
    using (TransactionScope scope = new
     TransactionScope(TransactionScopeOption.Required))
    {
        // Submit the purchase order.
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
        // Complete the transaction.
        scope.Complete();
    }
    //Save the messageID for order response correlation.
    orderMessageID = msg.Id;
    Console.WriteLine("Placed the order, waiting for response...");
}
```

 <span data-ttu-id="d3c60-138">La coda MSMQ da cui vengono ricevute le risposte per l'ordine è specificato in una sezione appSettings del file di configurazione, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-138">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="d3c60-139">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="d3c60-139">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="d3c60-140">Nell'indirizzo dell'endpoint WCF viene specificato uno schema MSMQ. formatname e viene utilizzato "localhost" per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="d3c60-140">The WCF endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="d3c60-141">Un nome di formato creato correttamente segue msmq.formatname nell'URI in base alle linee guida MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d3c60-141">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="d3c60-142">L'applicazione client salva il `messageID` del messaggio di richiesta dell'ordine che invia al servizio e attende una risposta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-142">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="d3c60-143">Quando una risposta arriva nella coda, il client la correla al messaggio dell'ordine inviato utilizzando la proprietà `correlationID` del messaggio, che contiene il `messageID` del messaggio dell'ordine inviato originariamente dal client al servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-143">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>

```csharp
static void DisplayOrderStatus()
{
    MessageQueue orderResponseQueue = new
     MessageQueue(ConfigurationManager.AppSettings
                  ["orderResponseQueueName"]);
    //Create a transaction scope.
    bool responseReceived = false;
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;
    while (!responseReceived)
    {
       Message responseMsg;
       using (TransactionScope scope2 = new
         TransactionScope(TransactionScopeOption.Required))
       {
          //Receive the Order Response message.
          responseMsg =
              orderResponseQueue.Receive
                   (MessageQueueTransactionType.Automatic);
          scope2.Complete();
     }
     responseMsg.Formatter = new
     System.Messaging.XmlMessageFormatter(new Type[] {
         typeof(PurchaseOrder) });
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;
    //Check if the response is for the order placed.
    if (orderMessageID == responseMsg.CorrelationId)
    {
       responseReceived = true;
       Console.WriteLine("Status of current Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
    else
    {
       Console.WriteLine("Status of previous Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
  }
}
```

 <span data-ttu-id="d3c60-144">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="d3c60-144">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="d3c60-145">Il servizio riceve i messaggi dal client e invia una risposta al client.</span><span class="sxs-lookup"><span data-stu-id="d3c60-145">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="d3c60-146">Il client visualizza la risposta ricevuta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-146">The client displays the response received from the service.</span></span> <span data-ttu-id="d3c60-147">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="d3c60-147">Press ENTER in each console window to shut down the service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="d3c60-148">Questo esempio richiede l'installazione di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="d3c60-148">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="d3c60-149">Vedere le istruzioni di installazione di MSMQ nella sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="d3c60-149">See the MSMQ installation instructions in the See Also section.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="d3c60-150">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d3c60-150">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="d3c60-151">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d3c60-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="d3c60-152">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="d3c60-152">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="d3c60-153">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="d3c60-153">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="d3c60-154">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d3c60-154">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="d3c60-155">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d3c60-155">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="d3c60-156">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="d3c60-156">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="d3c60-157">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="d3c60-157">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="d3c60-158">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="d3c60-158">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="d3c60-159">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="d3c60-159">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="d3c60-160">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="d3c60-160">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="d3c60-161">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d3c60-161">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="d3c60-162">Per eseguire l'esempio in una configurazione con un solo computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d3c60-162">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="d3c60-163">Eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="d3c60-163">Run the sample across computers</span></span>

1. <span data-ttu-id="d3c60-164">Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3c60-164">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="d3c60-165">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="d3c60-165">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="d3c60-166">Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".</span><span class="sxs-lookup"><span data-stu-id="d3c60-166">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="d3c60-167">Nel file Service.exe.config modificare l'indirizzo dell'endpoint del client e specificare il nome del computer client anziché ".".</span><span class="sxs-lookup"><span data-stu-id="d3c60-167">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>

5. <span data-ttu-id="d3c60-168">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d3c60-168">On the service computer, launch Service.exe from a command prompt.</span></span>

6. <span data-ttu-id="d3c60-169">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d3c60-169">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3c60-170">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d3c60-170">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d3c60-171">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d3c60-171">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d3c60-172">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d3c60-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d3c60-173">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-173">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a><span data-ttu-id="d3c60-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3c60-174">See also</span></span>

- [<span data-ttu-id="d3c60-175">Accodamento in WCF</span><span class="sxs-lookup"><span data-stu-id="d3c60-175">Queuing in WCF</span></span>](../feature-details/queuing-in-wcf.md)
- <span data-ttu-id="d3c60-176">[accodamento messaggi](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="d3c60-176">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
