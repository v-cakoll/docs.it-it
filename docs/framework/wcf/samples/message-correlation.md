---
title: Correlazione dei messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef105626d2427f0ea6dd49f696b78ffac4834f92
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="message-correlation"></a><span data-ttu-id="e3bbe-102">Correlazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e3bbe-102">Message Correlation</span></span>
<span data-ttu-id="e3bbe-103">In questo esempio viene illustrato come un'applicazione di accodamento messaggi (MSMQ) può inviare un messaggio MSMQ a un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e come i messaggi possono essere correlati tra applicazioni mittenti e riceventi, in uno scenario di richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="e3bbe-104">In questo esempio viene utilizzata l'associazione msmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="e3bbe-105">Il servizio in questo caso è un'applicazione console self-hosted che consente di osservare il servizio che riceve i messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="e3bbe-106">k</span><span class="sxs-lookup"><span data-stu-id="e3bbe-106">k</span></span>  
  
 <span data-ttu-id="e3bbe-107">Il servizio elabora il messaggio ricevuto dal mittente e invia un messaggio di risposta al mittente.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="e3bbe-108">Il mittente correla la risposta ricevuta alla richiesta inviata originariamente.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="e3bbe-109">Le proprietà `MessageID` e `CorrelationID` del messaggio vengono utilizzate per correlare i messaggi di richiesta e risposta.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>  
  
 <span data-ttu-id="e3bbe-110">Il contratto di servizio `IOrderProcessor` definisce un'operazione di servizio unidirezionale adatto per l'utilizzo con l'accodamento.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="e3bbe-111">Un messaggio MSMQ non ha un'intestazione Action, pertanto non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi ai contratti dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="e3bbe-112">Pertanto, in questo caso può essere presente un solo contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="e3bbe-113">Se si desidera definire più contratti dell'operazione nel servizio, l'applicazione deve fornire informazioni in merito a quale intestazione nel messaggio MSMQ (ad esempio, l'etichetta o correlationID) può essere utilizzata per decidere quale contratto dell'operazione inviare.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span> <span data-ttu-id="e3bbe-114">Questa funzionalità viene illustrata la [Demux personalizzato](../../../../docs/framework/wcf/samples/custom-demux.md).</span><span class="sxs-lookup"><span data-stu-id="e3bbe-114">This is demonstrated in the [Custom Demux](../../../../docs/framework/wcf/samples/custom-demux.md).</span></span>  
  
 <span data-ttu-id="e3bbe-115">Il messaggio MSMQ non contiene inoltre informazioni in merito alle intestazioni di cui è stato eseguito il mapping ai diversi parametri del contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-115">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="e3bbe-116">Pertanto, può essere presente un solo parametro nel contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-116">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="e3bbe-117">Il parametro è di tipo <!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`--> , `System.ServiceModel.MSMQIntegration.MsmqMessage` che contiene il messaggio MSMQ sottostante.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-117">The parameter is of type <!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`--> , `System.ServiceModel.MSMQIntegration.MsmqMessage` which contains the underlying MSMQ message.</span></span> <span data-ttu-id="e3bbe-118">Il tipo "T" nella classe `MsmqMessage<T>` rappresenta i dati serializzati nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-118">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="e3bbe-119">In questo esempio, il tipo `PurchaseOrder` è serializzato nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-119">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
```  
  
 <span data-ttu-id="e3bbe-120">L'operazione del servizio elabora l'ordine di acquisto e ne visualizza il contenuto e lo stato nella finestra della console del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-120">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="e3bbe-121"><xref:System.ServiceModel.OperationBehaviorAttribute> configura l'operazione per integrarsi in una transazione con la coda e contrassegnare la transazione come completa quando l'operazione viene restituita.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-121">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="e3bbe-122">`PurchaseOrder` contiene i dettagli dell'ordine che deve essere elaborato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-122">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>  
  
```  
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
  
 <span data-ttu-id="e3bbe-123">Il servizio utilizza un `OrderResponseClient` client personalizzato per inviare il messaggio MSMQ alla coda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-123">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="e3bbe-124">Poiché l'applicazione che riceve ed elabora il messaggio è un'applicazione MSMQ e non un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], non c'è contratto di servizio implicito tra le due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-124">Because the application that receives and processes the message is an MSMQ application and not a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="e3bbe-125">Pertanto, in questo scenario, non è possibile creare un proxy utilizzando lo strumento Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-125">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>  
  
 <span data-ttu-id="e3bbe-126">Il proxy personalizzato è essenzialmente lo stesso per tutte le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che utilizzano l'associazione `msmqIntegrationBinding` per inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-126">The custom proxy is essentially the same for all [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="e3bbe-127">A differenza di altri proxy, non include una serie di operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-127">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="e3bbe-128">È un'operazione di solo invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-128">It is a submit message operation only.</span></span>  
  
```  
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
  
 <span data-ttu-id="e3bbe-129">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-129">The service is self hosted.</span></span> <span data-ttu-id="e3bbe-130">Quando si utilizza il trasporto di integrazione MSMQ, la coda utilizzata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-130">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="e3bbe-131">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-131">This can be done manually or through code.</span></span> <span data-ttu-id="e3bbe-132">In questo esempio, il servizio contiene il codice <xref:System.Messaging> necessario per verificare l'esistenza della coda e crearla se necessario.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-132">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="e3bbe-133">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-133">The queue name is read from the configuration file.</span></span>  
  
```  
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
  
 <span data-ttu-id="e3bbe-134">La coda MSMQ a cui vengono inviate le richieste dell'ordine viene specificata in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-134">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="e3bbe-135">Gli endpoint del client e del servizio sono definiti nella sezione system.serviceModel del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-135">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="e3bbe-136">Entrambi specificano l'associazione `msmqIntegrationbinding`.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-136">Both specify the `msmqIntegrationbinding` binding.</span></span>  
  
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
  
 <span data-ttu-id="e3bbe-137">L'applicazione client utilizza <xref:System.Messaging> per inviare un messaggio durevole e transazionale alla coda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-137">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="e3bbe-138">Il corpo del messaggio contiene l'ordine di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-138">The message's body contains the purchase order.</span></span>  
  
```  
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
  
 <span data-ttu-id="e3bbe-139">La coda MSMQ da cui vengono ricevute le risposte per l'ordine è specificato in una sezione appSettings del file di configurazione, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-139">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3bbe-140">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-140">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="e3bbe-141">Nell'indirizzo dell'endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene specificato uno schema msmq.formatname e viene utilizzato "localhost" per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-141">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="e3bbe-142">Un nome di formato creato correttamente segue msmq.formatname nell'URI in base alle linee guida MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-142">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>  
  
```xml  
<appSettings>  
    <add key=" orderResponseQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
 <span data-ttu-id="e3bbe-143">L'applicazione client salva il `messageID` del messaggio di richiesta dell'ordine che invia al servizio e attende una risposta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-143">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="e3bbe-144">Quando una risposta arriva nella coda, il client la correla al messaggio dell'ordine inviato utilizzando la proprietà `correlationID` del messaggio, che contiene il `messageID` del messaggio dell'ordine inviato originariamente dal client al servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-144">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>  
  
```  
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
  
 <span data-ttu-id="e3bbe-145">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-145">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e3bbe-146">Il servizio riceve i messaggi dal client e invia una risposta al client.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-146">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="e3bbe-147">Il client visualizza la risposta ricevuta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-147">The client displays the response received from the service.</span></span> <span data-ttu-id="e3bbe-148">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3bbe-149">Questo esempio richiede l'installazione di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="e3bbe-149">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="e3bbe-150">Vedere le istruzioni di installazione di MSMQ nella sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-150">See the MSMQ installation instructions in the See Also section.</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="e3bbe-151">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e3bbe-151">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e3bbe-152">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3bbe-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e3bbe-153">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-153">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="e3bbe-154">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-154">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="e3bbe-155">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-155">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="e3bbe-156">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-156">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="e3bbe-157">Aprire Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3bbe-157">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="e3bbe-158">Espandere il **funzionalità** scheda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-158">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="e3bbe-159">Fare doppio clic su **code Private**e selezionare **New**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-159">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="e3bbe-160">Controllare il **transazionale** casella.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-160">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="e3bbe-161">Immettere `ServiceModelSamplesTransacted` come il nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-161">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="e3bbe-162">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3bbe-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="e3bbe-163">Per eseguire l'esempio nella configurazione di un singolo computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3bbe-163">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e3bbe-164">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="e3bbe-164">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="e3bbe-165">Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-165">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="e3bbe-166">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-166">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="e3bbe-167">Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".</span><span class="sxs-lookup"><span data-stu-id="e3bbe-167">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="e3bbe-168">Nel file Service.exe.config modificare l'indirizzo dell'endpoint del client e specificare il nome del computer client anziché ".".</span><span class="sxs-lookup"><span data-stu-id="e3bbe-168">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>  
  
5.  <span data-ttu-id="e3bbe-169">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-169">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
6.  <span data-ttu-id="e3bbe-170">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-170">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3bbe-171">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-171">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e3bbe-172">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e3bbe-173">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3bbe-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3bbe-174">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e3bbe-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`  
  
## <a name="see-also"></a><span data-ttu-id="e3bbe-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3bbe-175">See Also</span></span>  
 [<span data-ttu-id="e3bbe-176">Accodamento messaggi in WCF</span><span class="sxs-lookup"><span data-stu-id="e3bbe-176">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="e3bbe-177">Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="e3bbe-177">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=94968)
