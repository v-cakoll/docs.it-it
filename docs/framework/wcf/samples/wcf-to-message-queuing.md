---
title: Da Windows Communication Foundation a Accodamento messaggi
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: 2e37a6efac6b979645b2dbb338b64f698b3b97e0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344606"
---
# <a name="windows-communication-foundation-to-message-queuing"></a>Da Windows Communication Foundation a Accodamento messaggi

In questo esempio viene illustrato il modo in cui un'applicazione Windows Communication Foundation (WCF) può inviare un messaggio a un'applicazione di Accodamento messaggi (MSMQ). Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda. Non è necessario che il servizio e il client siano in esecuzione contemporaneamente.

 Il servizio riceve i messaggi dalla coda ed elabora gli ordini. Il servizio crea una coda transazionale e configura un gestore di messaggi basato sulla ricezione dei messaggi, come mostra il codice di esempio seguente.

```csharp
static void Main(string[] args)
{
    if (!MessageQueue.Exists(
              ConfigurationManager.AppSettings["queueName"]))
       MessageQueue.Create(
           ConfigurationManager.AppSettings["queueName"], true);
        //Connect to the queue
        MessageQueue Queue = new
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);
    Queue.ReceiveCompleted +=
                 new ReceiveCompletedEventHandler(ProcessOrder);
    Queue.BeginReceive();
    Console.WriteLine("Order Service is running");
    Console.ReadLine();
}
```

 Quando un messaggio viene ricevuto nella coda, viene chiamato il gestore dei messaggi `ProcessOrder`.

```csharp
public static void ProcessOrder(Object source,
    ReceiveCompletedEventArgs asyncResult)
{
    try
    {
        // Connect to the queue.
        MessageQueue Queue = (MessageQueue)source;
        // End the asynchronous receive operation.
        System.Messaging.Message msg =
                     Queue.EndReceive(asyncResult.AsyncResult);
        msg.Formatter = new System.Messaging.XmlMessageFormatter(
                                new Type[] { typeof(PurchaseOrder) });
        PurchaseOrder po = (PurchaseOrder) msg.Body;
        Random statusIndexer = new Random();
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
        Console.WriteLine("Processing {0} ", po);
        Queue.BeginReceive();
    }
    catch (System.Exception ex)
    {
        Console.WriteLine(ex.Message);
    }

}
```

 Il servizio estrae `ProcessOrder` dal corpo del messaggio di MSMQ ed elabora l'ordine.

 Il nome della coda MSMQ viene specificato in una sezione appSettings del file di configurazione, come mostra la configurazione di esempio seguente.

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

> [!NOTE]
> Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.

 Il client crea un ordine di acquisto e invia l'ordine di acquisto all'interno dell'ambito di una transazione, come mostra il codice di esempio seguente.

```csharp
// Create the purchase order
PurchaseOrder po = new PurchaseOrder();
// Fill in the details
...

OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");

MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    client.SubmitPurchaseOrder(ordermsg);
    scope.Complete();
}
Console.WriteLine("Order has been submitted:{0}", po);

//Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

 Il client utilizza un ordine client "in" personalizzato per inviare il messaggio MSMQ alla coda. Poiché l'applicazione che riceve ed elabora il messaggio è un'applicazione MSMQ e non un'applicazione WCF, non esiste alcun contratto di servizio implicito tra le due applicazioni. Quindi, in questo scenario, non si può creare un proxy utilizzando lo strumento Svcutil.exe.

 Il client personalizzato è essenzialmente lo stesso per tutte le applicazioni WCF che utilizzano l'associazione `MsmqIntegration` per inviare messaggi. A differenza di altri client, non include varie operazioni del servizio. È un'operazione di solo invio del messaggio.

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor
{
    public OrderProcessorClient(){}

    public OrderProcessorClient(string configurationName)
        : base(configurationName)
    { }

    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SubmitPurchaseOrder(msg);
    }
}
```

 Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client. È possibile osservare il servizio che riceve i messaggi dal client. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client. Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente. Ad esempio è possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.

> [!NOTE]
> Questo esempio richiede l'installazione di Accodamento messaggi. Vedere le istruzioni di installazione in [Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94968).

## <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Se il servizio viene eseguito prima, verificherà la presenza della coda. Se la coda non è presente, il servizio ne creerà una. È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ. Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.

    1. Aprire Server Manager in Visual Studio 2012.

    2. Espandere la scheda **funzionalità** .

    3. Fare clic con il pulsante destro del mouse su **code di messaggi private**, quindi scegliere **nuovo** > **coda privata**.

    4. Controllare la casella **transazionale** .

    5. Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.

3. Per compilare l' C# edizione o Visual Basic della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Per eseguire l'esempio in una configurazione con un solo computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="run-the-sample-across-computers"></a>Eseguire l'esempio tra più computer

1. Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.

2. Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.

3. Nel file Client.exe.config modificare l'indirizzo dell'endpoint del client e specificare il nome del computer del servizio anziché ".".

4. Sul computer del servizio eseguire Service.exe da un prompt dei comandi.

5. Sul computer client avviare Client.exe da un prompt dei comandi.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`

## <a name="see-also"></a>Vedere anche

- [Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94968)
