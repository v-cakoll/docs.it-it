---
title: Correlazione dei messaggi
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: adabf02cb8ec232a887bd4720ea9552a7d870fe3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348324"
---
# <a name="message-correlation"></a>Correlazione dei messaggi

In questo esempio viene illustrato come un'applicazione di Accodamento messaggi (MSMQ) può inviare un messaggio MSMQ a un servizio Windows Communication Foundation (WCF) e come i messaggi possono essere correlati tra applicazioni mittente e ricevitore in uno scenario di richiesta/risposta. In questo esempio viene utilizzata l'associazione msmqIntegrationBinding. Il servizio in questo caso è un'applicazione console self-hosted che consente di osservare il servizio che riceve i messaggi in coda. k

 Il servizio elabora il messaggio ricevuto dal mittente e invia un messaggio di risposta al mittente. Il mittente correla la risposta ricevuta alla richiesta inviata originariamente. Le proprietà `MessageID` e `CorrelationID` del messaggio vengono utilizzate per correlare i messaggi di richiesta e risposta.

 Il contratto di servizio `IOrderProcessor` definisce un'operazione di servizio unidirezionale adatto per l'utilizzo con l'accodamento. Un messaggio MSMQ non ha un'intestazione Action, pertanto non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi ai contratti dell'operazione. Pertanto, in questo caso può essere presente un solo contratto dell'operazione. Se si desidera definire più contratti dell'operazione nel servizio, l'applicazione deve fornire informazioni in merito a quale intestazione nel messaggio MSMQ (ad esempio, l'etichetta o correlationID) può essere utilizzata per decidere quale contratto dell'operazione inviare.

 Il messaggio MSMQ non contiene inoltre informazioni in merito alle intestazioni di cui è stato eseguito il mapping ai diversi parametri del contratto dell'operazione. Pertanto, può essere presente un solo parametro nel contratto dell'operazione. Il parametro è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, che contiene il messaggio MSMQ sottostante. Il tipo "T" nella classe `MsmqMessage<T>` rappresenta i dati serializzati nel corpo del messaggio MSMQ. In questo esempio, il tipo `PurchaseOrder` è serializzato nel corpo del messaggio MSMQ.

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 L'operazione del servizio elabora l'ordine di acquisto e ne visualizza il contenuto e lo stato nella finestra della console del servizio. <xref:System.ServiceModel.OperationBehaviorAttribute> configura l'operazione per integrarsi in una transazione con la coda e contrassegnare la transazione come completa quando l'operazione viene restituita. `PurchaseOrder` contiene i dettagli dell'ordine che deve essere elaborato dal servizio.

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

 Il servizio utilizza un `OrderResponseClient` client personalizzato per inviare il messaggio MSMQ alla coda. Poiché l'applicazione che riceve ed elabora il messaggio è un'applicazione MSMQ e non un'applicazione WCF, non esiste alcun contratto di servizio implicito tra le due applicazioni. Pertanto, in questo scenario, non è possibile creare un proxy utilizzando lo strumento Svcutil.exe.

 Il proxy personalizzato è essenzialmente lo stesso per tutte le applicazioni WCF che utilizzano l'associazione `msmqIntegrationBinding` per inviare messaggi. A differenza di altri proxy, non include una serie di operazioni del servizio. È un'operazione di solo invio del messaggio.

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

 Il servizio è indipendente. Quando si utilizza il trasporto di integrazione MSMQ, la coda utilizzata deve essere creata in anticipo. Questa operazione può essere eseguita manualmente o mediante il codice. In questo esempio, il servizio contiene il codice <xref:System.Messaging> necessario per verificare l'esistenza della coda e crearla se necessario. Il nome della coda viene letto dal file di configurazione.

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

 La coda MSMQ a cui vengono inviate le richieste dell'ordine viene specificata in una sezione appSettings del file di configurazione. Gli endpoint del client e del servizio sono definiti nella sezione system.serviceModel del file di configurazione. Entrambi specificano l'associazione `msmqIntegrationbinding`.

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

 L'applicazione client utilizza <xref:System.Messaging> per inviare un messaggio durevole e transazionale alla coda. Il corpo del messaggio contiene l'ordine di acquisto.

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

 La coda MSMQ da cui vengono ricevute le risposte per l'ordine è specificato in una sezione appSettings del file di configurazione, come illustrato nella configurazione di esempio seguente.

> [!NOTE]
> Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso. Nell'indirizzo dell'endpoint WCF viene specificato uno schema MSMQ. formatname e viene utilizzato "localhost" per il computer locale. Un nome di formato creato correttamente segue msmq.formatname nell'URI in base alle linee guida MSMQ.

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 L'applicazione client salva il `messageID` del messaggio di richiesta dell'ordine che invia al servizio e attende una risposta dal servizio. Quando una risposta arriva nella coda, il client la correla al messaggio dell'ordine inviato utilizzando la proprietà `correlationID` del messaggio, che contiene il `messageID` del messaggio dell'ordine inviato originariamente dal client al servizio.

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

 Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client. Il servizio riceve i messaggi dal client e invia una risposta al client. Il client visualizza la risposta ricevuta dal servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.

> [!NOTE]
> Questo esempio richiede l'installazione di accodamento messaggi (MSMQ). Vedere le istruzioni di installazione di MSMQ nella sezione Vedere anche.

## <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Se il servizio viene eseguito prima, verificherà la presenza della coda. Se la coda non è presente, il servizio ne creerà una. È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ. Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.

    1. Aprire Server Manager in Visual Studio 2012.

    2. Espandere la scheda **funzionalità** .

    3. Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.

    4. Controllare la casella **transazionale** .

    5. Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Per eseguire l'esempio in una configurazione con un solo computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="run-the-sample-across-computers"></a>Eseguire l'esempio tra più computer

1. Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.

2. Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.

3. Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".

4. Nel file Service.exe.config modificare l'indirizzo dell'endpoint del client e specificare il nome del computer client anziché ".".

5. Sul computer del servizio eseguire Service.exe da un prompt dei comandi.

6. Sul computer client avviare Client.exe da un prompt dei comandi.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a>Vedere anche

- [Accodamento in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94968)
