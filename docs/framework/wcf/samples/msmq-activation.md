---
title: Attivazione MSMQ
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 0dbd24a612d56c0fe88066f625be2a8369b7df5b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602539"
---
# <a name="msmq-activation"></a>Attivazione MSMQ

In questo esempio viene illustrato come ospitare le applicazioni del servizio di attivazione dei processi di Windows (WAS) lette da una coda di messaggi. Questo esempio usa `netMsmqBinding` e si basa sull'esempio di [comunicazione bidirezionale](two-way-communication.md) . Il servizio in questo caso è un'applicazione ospitata su Web. Il client è indipendente e genera output sulla console per osservare lo stato degli ordini di acquisto inviati.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

> [!NOTE]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> \<InstallDrive>: \ WF_WCF_Samples
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.
>
> \<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.

Il servizio Attivazione processo Windows (WAS), il nuovo meccanismo di attivazione del processo per Windows Server 2008, fornisce funzionalità simili a IIS che in precedenza erano disponibili solo per applicazioni basate su HTTP per applicazioni che utilizzano protocolli non HTTP. Windows Communication Foundation (WCF) utilizza l'interfaccia dell'adattatore listener per comunicare le richieste di attivazione ricevute tramite i protocolli non HTTP supportati da WCF, ad esempio TCP, named pipe e MSMQ. La funzionalità per ricevere richieste su protocolli non HTTP viene ospitata dai servizi Windows gestiti in esecuzione su SMSvcHost.exe.

Il servizio di adattatore listener Net.Msmq (NetMsmqActivator) attiva le applicazioni in coda in base ai messaggi nella coda.

Il client invia ordini di acquisto al servizio dall'ambito di una transazione. Il servizio riceve gli ordini in una transazione e li elabora. Il servizio richiama il client con lo stato dell'ordine. Per facilitare la comunicazione bidirezionale il client e il servizio usano entrambi code per accodare gli ordini di acquisto e lo stato degli ordini.

Il contratto di servizio `IOrderProcessor` definisce operazioni del servizio unidirezionale che usano l'accodamento. L'operazione del servizio usa l'endpoint di risposta per inviare gli stati degli ordini al client. L'indirizzo dell'endpoint di risposta è l'URI della coda usato per restituire lo stato dell'ordine al client. L'applicazione di elaborazione degli ordini implementa questo contratto.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

Il contratto di risposta a cui inviare lo stato dell'ordine è specificato dal client. Il client implementa il contratto dello stato dell'ordine. Il servizio usa il client generato di questo contratto per restituire lo stato dell'ordine al client.

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

L'operazione del servizio elabora l'ordine di acquisto inviato. <xref:System.ServiceModel.OperationBehaviorAttribute> viene applicato all'operazione del servizio per specificare l'inserimento automatico nell'elenco nella transazione usata per ricevere il messaggio dalla coda e il completamento automatico della transazione al completamento dell'operazione del servizio. La classe `Orders` incapsula la funzionalità di elaborazione degli ordini. In questo caso, aggiunge l'ordine di acquisto a un dizionario. La transazione che l'operazione del servizio ha inserito nell'elenco è disponibile per le operazioni nella classe `Orders`.

L'operazione del servizio, oltre a elaborare l'ordine di acquisto inviato, risponde al client in merito allo stato dell'ordine.

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

L'associazione client da usare viene specificata mediante un file di configurazione.

Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione. L'endpoint per il servizio è definito nella sezione System.serviceModel del file di configurazione.

> [!NOTE]
> Il nome della coda MSMQ e l'indirizzo endpoint usano convenzioni di indirizzamento leggermente diverse. Nel nome della coda MSMQ viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso. L'indirizzo endpoint WCF specifica uno schema net. MSMQ:, utilizza "localhost" per il computer locale e utilizza le barre nel percorso. Per leggere da una coda ospitata sul computer remoto, sostituire "." e "localhost" con il nome computer remoto.

Viene usato un file con estensione svc con il nome della classe per ospitare il codice del servizio in WAS.

Il file Service.svc stesso contiene una direttiva per creare `OrderProcessorService`.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

Il file Service.svc contiene inoltre una direttiva assembly per garantire che System.Transactions.dll venga caricato.

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

Il client crea un ambito di transazione. La comunicazione con il servizio avviene all'interno dell'ambito della transazione, la quale viene trattata come unità atomica nella quale tutti i messaggi hanno esito positivo o negativo. Il commit della transazione viene eseguito chiamando `Complete` nell'ambito della transazione.

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

Il codice client implementa il contratto `IOrderStatus` per ricevere lo stato dell'ordine dal servizio. In questo caso, stampa lo stato dell'ordine.

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

La coda dello stato degli ordini viene creata nel metodo `Main`. La configurazione del client comprende la configurazione del servizio di stato degli ordini per ospitare il servizio di stato degli ordini, come illustrato nella configurazione di esempio seguente.

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

Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del server e del client. È possibile osservare che il server riceve i messaggi dal client. Premere INVIO in tutte le finestre della console per arrestare il server e il client.

Il client visualizza le informazioni sullo stato dell'ordine inviate dal server.

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi che IIS 7,0 sia installato, in quanto è necessario per l'attivazione di WAS.

2. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md). Inoltre, è necessario installare i componenti di attivazione non HTTP WCF:

    1. Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.

    2. Selezionare **programmi e funzionalità**.

    3. Fare clic **su attivazione o disattivazione delle funzionalità Windows**.

    4. In **Riepilogo funzionalità**fare clic su **Aggiungi funzionalità**.

    5. Espandere il nodo **Microsoft .NET Framework 3,0** e controllare la funzionalità di **attivazione non http Windows Communication Foundation** .

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Eseguire il client lanciando client.exe da una finestra di comando. In questo modo verrà creata la coda e gli verrà inviato un messaggio. Lasciare il client in esecuzione per vedere cosa succede quando il servizio legge il messaggio

5. Il servizio di attivazione MSMQ viene eseguito come impostazione predefinita come Servizio di rete. Pertanto, la coda usata per attivare l'applicazione deve disporre delle autorizzazioni di ricezione e di lettura per il Servizio di rete. Queste autorizzazioni possono essere aggiunte usando il sistema di accodamento messaggi MMC:

    1. Dal menu **Start** fare clic su **Esegui**, quindi digitare `Compmgmt.msc` e premere INVIO.

    2. In **Servizi e applicazioni**espandere **Accodamento messaggi**.

    3. Fare clic su **code private**.

    4. Fare clic con il pulsante destro del mouse sulla coda (ServiceModelSamples/Service. svc) e scegliere **Proprietà**.

    5. Nella scheda **sicurezza** fare clic su **Aggiungi** e assegnare le autorizzazioni Visualizza e ricevi al servizio di rete.

6. Configurare il servizio di attivazione dei processi di Windows (WAS) per supportare l'attivazione MSMQ.

    Per maggiore praticità, i passaggi seguenti vengono implementati in un file batch denominato AddMsmqSiteBinding.cmd posto nella directory degli esempi.

    1. Per supportare l'attivazione net.msmq, è innanzitutto necessario associare il sito Web predefinito al protocollo net.msmq. A tale fine, usare appcmd.exe, installato con il set di strumenti di gestione di IIS 7.0. Da un prompt dei comandi con privilegi elevati (amministratore), eseguire il comando seguente:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

        Questo comando aggiunge un'associazione di sito net.msmq al sito Web predefinito.

    2. Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.msmq comune, ognuna di esse può abilitare individualmente il supporto net.msmq. Per abilitare net.msmq per l'applicazione /servicemodelsamples, eseguire il comando seguente da un prompt dei comandi con privilegi elevati.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

        Questo comando consente di accedere all'applicazione/servicemodelsamples usando `http://localhost/servicemodelsamples` e `net.msmq://localhost/servicemodelsamples` .

7. Se in precedenza non è stato fatto, assicurarsi che il servizio di attivazione MSMQ sia abilitato. Dal menu **Start** fare clic su **Esegui**, quindi digitare `Services.msc` . Eseguire una ricerca nell'elenco dei servizi per l' **adattatore listener Net. MSMQ**. Fare clic con il pulsante destro del mouse e scegliere **Proprietà**. Impostare **tipo di avvio** su **automatico**, fare clic su **applica** e fare clic sul pulsante **Avvia** . È necessario eseguire questo passaggio solo la prima volta che si usa il servizio di adattatore listener Net.Msmq.

8. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md). Modificare inoltre il codice nel client che invia l'ordine di acquisto in modo che corrisponda al nome del computer nell'URI della coda durante l'invio di ordini di acquisto. Usare il codice seguente:

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. Rimuovere l'associazione di sito net.msmq aggiunta per questo esempio.

    Per praticità, i passaggi seguenti vengono implementati in un file batch denominato RemoveMsmqSiteBinding.cmd posto nella directory degli esempi:

    1. Rimuovere net.msmq dall'elenco dei protocolli abilitati eseguendo il comando seguente da una finestra del prompt dei comandi con privilegi elevati.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

    2. Rimuovere l'associazione di sito net.msmq eseguendo il comando seguente da un prompt dei comandi con privilegi elevati.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

    > [!WARNING]
    > L'esecuzione del file batch determinerà la reimpostazione di DefaultAppPool per l'esecuzione con .NET Framework versione 2.0.

Per impostazione predefinita con il trasporto dell'associazione `netMsmqBinding` è abilitata la sicurezza. Il tipo di sicurezza del trasporto è determinato da due proprietà, `MsmqAuthenticationMode` e `MsmqProtectionLevel`. Per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`. Affinché MSMQ fornisca la funzionalità di autenticazione e firma, deve appartenere a un dominio. Se si esegue questo esempio in un computer che non appartiene a un dominio, si riceverà l'errore seguente: "Il certificato interno del servizio di accodamento messaggi non esiste".

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro

1. Se il computer non appartiene a un dominio, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su None, come illustrato nell'esempio di configurazione seguente.

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. Modificare la configurazione sul server e sul client prima di eseguire l'esempio.

    > [!NOTE]
    > L'impostazione di `security mode` su `None` è equivalente all'impostazione di `MsmqAuthenticationMode`, `MsmqProtectionLevel` e della sicurezza `Message` su `None`.

3. Per abilitare l'attivazione su un computer che fa parte di un gruppo di lavoro, il servizio di attivazione e il processo di lavoro devono essere eseguiti con un account utente specifico (deve essere lo stesso per entrambi) e la coda deve essere dotata di ACL per l'account utente specifico.

     Per modificare l'identità con la quale viene eseguito il processo di lavoro:

    1. Eseguire Inetmgr.exe.

    2. In **pool di applicazioni**fare clic con il pulsante destro del mouse su **AppPool** (in genere **DefaultAppPool**) e scegliere **imposta impostazioni predefinite pool di applicazioni...**.

    3. Modificare le proprietà dell'identità per usare l'account utente specifico.

     Per modificare l'identità con la quale viene eseguito il servizio di attivazione:

    1. Eseguire Services.msc.

    2. Fare clic con il pulsante destro del mouse sull' **Adapter NET. MsmqListener**e scegliere **Proprietà**.

4. Modificare l'account nella scheda **Logon** .

5. In un gruppo di lavoro è inoltre necessario che il servizio venga eseguito usando un token di accesso senza restrizioni. A tale scopo, eseguire il comando seguente:

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
