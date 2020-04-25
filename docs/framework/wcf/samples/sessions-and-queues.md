---
title: Sessioni e code
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 489a8f5e782faca679991809e575e98153de95e0
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140595"
---
# <a name="sessions-and-queues"></a>Sessioni e code
In questo esempio viene illustrato come inviare e ricevere una serie di messaggi correlati in una comunicazione in coda sul trasporto di accodamento messaggi (MSMQ). In questo esempio viene usata l'associazione `netMsmqBinding`. Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 Nella comunicazione in coda, il client comunica al servizio usando una coda. Più precisamente, il client invia messaggi a una coda. Il servizio riceve messaggi dalla coda. Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.  
  
 A volte, un client invia una serie di messaggi correlati tra loro in un gruppo. Quando i messaggi devono essere elaborati insieme o in un ordine specifico, è possibile utilizzare una coda per raggrupparli, in modo che vengano elaborati da una sola applicazione di destinazione. Questo aspetto è particolarmente importante quando sono presenti molte applicazioni di destinazione in un gruppo di server ed è necessario assicurare che un gruppo di messaggi sia elaborato dalla stessa applicazione di destinazione. Le sessioni in coda sono un meccanismo utilizzato per inviare e ricevere una serie correlata di messaggi che devono essere elaborati contemporaneamente. Le sessioni in coda richiedono l'esibizione di questo modello da parte di una transazione.  
  
 In questo esempio, il client invia una serie di messaggi al servizio durante una sessione all'interno dell'ambito di una singola transazione.  
  
 Il contratto di servizio è `IOrderTaker`che definisce un servizio unidirezionale adatto per l'uso con le code. L'elemento <xref:System.ServiceModel.SessionMode> utilizzato nel contratto mostrato nel codice di esempio seguente indica che i messaggi fanno parte della sessione.  

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

 Il servizio definisce le operazioni del servizio in modo tale che la prima operazione si integri in una transazione ma non la completi automaticamente. Le operazioni successive si integrano nella stessa transazione ma non la completano automaticamente. L'ultima operazione della sessione completa automaticamente la transazione. In questo modo, la stessa transazione viene utilizzata per molte chiamate a operazioni nel contratto di servizio. Se una delle operazioni genera un'eccezione, viene eseguito il rollback della transazione e la sessione viene reinserita nella coda. Al completamento dell'ultima operazione, viene eseguito il commit della transazione. Il servizio utilizza `PerSession` come <xref:System.ServiceModel.InstanceContextMode> per ricevere tutti i messaggi in una sessione sulla stessa istanza del servizio.  

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

 Il servizio è indipendente. Quando si usa il trasporto MSMQ, la coda usata deve essere creata in anticipo. Questa operazione può essere eseguita manualmente o mediante il codice. In questo esempio, il servizio contiene il codice <xref:System.Messaging> necessario per verificare l'esistenza della coda e crearla se necessario. Il nome della coda viene letto dal file di configurazione utilizzando la coda <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.  

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

 Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione. L'endpoint per il servizio è definito nella sezione system.serviceModel del file di configurazione e specifica l'associazione `netMsmqBinding`.  
  
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
  
 Il client crea un ambito di transazione. Tutti i messaggi nella sessione vengono inviati alla coda nell'ambito della transazione, facendo in modo che venga trattata come un unità atomica nella quale tutti i messaggi riescono o meno. Il commit della transazione viene eseguito chiamando <xref:System.Transactions.TransactionScope.Complete%2A>.  

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
> È possibile utilizzare solo una transazione per tutti i messaggi della sessione e tutti i messaggi della sessione devono essere inviati prima di eseguire il commit della transazione. La chiusura del client chiude la sessione. Pertanto, il client deve essere chiuso prima che la transazione sia completata per inviare tutti i messaggi della sessione alla coda.  
  
 Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client. È possibile osservare il servizio che riceve i messaggi dal client. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client. Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente. È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.  
  
 Nel client.  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 Nel servizio.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
 Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata. Esistono <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> due proprietà rilevanti per la sicurezza del trasporto MSMQ e <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` , per impostazione predefinita, la modalità di autenticazione è impostata `Windows` su e il livello di protezione è `Sign`impostato su. Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ. Se si esegue questo esempio in un computer che non soddisfà questi criteri si riceve un errore.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro o privo di integrazione con Active Directory  
  
1. Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nella configurazione di esempio seguente.  
  
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
  
2. Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.  
  
    > [!NOTE]
    > L'impostazione della modalità di sicurezza su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> e della sicurezza di `Message` su `None`.  
