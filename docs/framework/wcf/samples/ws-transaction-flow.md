---
title: Flusso delle transazioni WS
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 781934e9ab27f761e71841c2edc509f9b8022aa7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094748"
---
# <a name="ws-transaction-flow"></a>Flusso delle transazioni WS
Questo esempio dimostra l'uso di una transazione coordinata dal client e le opzioni client e server per il flusso delle transazioni mediante il protocollo WS-Atomic Transaction o OleTransactions. Questo esempio si basa sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice, ma le operazioni sono attribuite per illustrare l'uso della `TransactionFlowAttribute` con l'enumerazione **TransactionFlowOption** per determinare il grado di attivazione del flusso delle transazioni. All'interno dell'ambito della transazione propagata, viene scritto un log delle operazioni richieste in un database che persiste fino a che la transazione coordinata dal client non è stata completata; se la transazione client non viene completata, la transazione del servizio Web assicura che non venga eseguito il commit degli aggiornamenti appropriati al database.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Dopo avere avviato una connessione con il servizio e una transazione, il client accede ad alcune operazioni del servizio. Il contratto per il servizio è definito come segue, con ognuna delle operazioni che dimostra un'impostazione diversa per `TransactionFlowOption`.  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);   
}  
```

 Questo definisce le operazioni nell'ordine in cui devono essere elaborate:  
  
- Una richiesta di operazione `Add` deve includere una transazione propagata.  
  
- Una richiesta di operazione `Subtract` può includere una transazione propagata.  
  
- Una richiesta di operazione `Multiply` non deve includere una transazione propagata mediante l'impostazione esplicita NotAllowed.  
  
- Una richiesta di operazione `Divide` non deve includere una transazione propagata mediante l'omissione di un attributo `TransactionFlow`.  
  
 Per abilitare il flusso delle transazioni, è necessario usare le associazioni con la proprietà [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) abilitata in aggiunta agli attributi operativi appropriati. In questo esempio, la configurazione del servizio espone un endpoint TCP e un endpoint HTTP oltre a un endpoint di scambio dei metadati. L'endpoint TCP e l'endpoint HTTP utilizzano le associazioni seguenti, entrambe per le quali è abilitata la proprietà [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) .  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
> L'associazione netTcpBinding fornita dal sistema consente di specificare il transactionProtocol mentre la wsHttpBinding fornita dal sistema usa solo il protocollo WSAtomicTransactionOctober2004 più interoperabile. Il protocollo OleTransactions è disponibile solo per l'uso da parte dei client Windows Communication Foundation (WCF).  
  
 Per la classe che implementa l'interfaccia `ICalculator`, a tutti i metodi viene attribuita la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> impostata su `true`. Questa impostazione dichiara che tutte le azioni intraprese all'interno del metodo avvengono all'interno dell'ambito di una transazione. In questo caso, le azioni intraprese includono la registrazione sul database del log. Se la richiesta dell'operazione include una transazione propagata allora le azioni avvengono all'interno dell'ambito della transazione in ingresso o viene generato automaticamente un nuovo ambito della transazione.  
  
> [!NOTE]
> La proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> definisce il comportamento locale alle implementazioni del metodo del servizio e non definisce la capacità o la necessità del client di propagare una transazione.  

```csharp
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```

 Nel client, le impostazioni `TransactionFlowOption` del servizio sulle operazioni vengono riflesse nella definizione generata del client relativa all'interfaccia `ICalculator`. Inoltre, le impostazioni della proprietà di `transactionFlow` del servizio sono riflesse nella configurazione dell'applicazione del client. Il client può determinare il trasporto e il protocollo selezionando l'endpoint `endpointConfigurationName` appropriato.  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> Il comportamento osservato di questo esempio è lo stesso indipendentemente dal protocollo o dal trasporto scelto.  
  
 Dopo avere avviato la connessione al servizio, il client crea un nuovo `TransactionScope` intorno alle chiamate alle operazioni del servizio.  

```csharp
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```

 Le chiamate alle operazioni sono come segue:  
  
- La richiesta `Add` propaga la transazione richiesta al servizio e le azioni del servizio si verificano all'interno dell'ambito della transazione del client.  
  
- Anche la prima richiesta `Subtract` propaga la transazione consentita al servizio e di nuovo le azioni del servizio si verificano all'interno dell'ambito della transazione del client.  
  
- La seconda richiesta `Subtract` viene eseguita all'interno di un nuovo ambito della transazione dichiarato con l'opzione `TransactionScopeOption.Suppress`. Questo sopprime la transazione esterna iniziale del client e la richiesta non propaga una transazione al servizio. Questo approccio consente a un client di rinunciare esplicitamente e protegge dalla propagazione di una transazione a un servizio quando non viene richiesta. Le azioni del servizio avvengono all'interno dell'ambito di una nuova transazione non connessa.  
  
- La richiesta `Multiply` non propaga una transazione al servizio, in quanto la definizione generata del client relativa all'interfaccia `ICalculator` include un oggetto <xref:System.ServiceModel.TransactionFlowAttribute> impostato su <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.  
  
- La richiesta `Divide` non propaga una transazione al servizio, in quanto di nuovo la definizione generata del client relativa all'interfaccia `ICalculator` non include un oggetto `TransactionFlowAttribute`. Le azioni del servizio avvengono nuovamente all'interno dell'ambito di un'altra nuova transazione non connessa.  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 La registrazione delle richieste di operazione del servizio viene visualizzata nella finestra della console del servizio. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 Dopo un'esecuzione corretta, l'ambito della transazione del client viene completato e viene eseguito il commit di tutte le azioni intraprese all'interno di quel ambito. In particolare, i 5 record menzionati vengono resi permanenti nel database del servizio. I primi 2 di questi si sono verificati all'interno dell'ambito della transazione del client.  
  
 Se si verifica un'eccezione in un punto qualsiasi all'interno dell'oggetto `TransactionScope` del client, la transazione non potrà essere completata. Ciò impedisce il commit nel database dei record registrati all'interno di quell'ambito. Questo effetto può essere osservato ripetendo l'esecuzione dell'esempio dopo avere impostato come commento la chiamata per il completamento dell'oggetto `TransactionScope` esterno. In una tale esecuzione, vengono registrate solo le ultime 3 azioni (dalla seconda richiesta `Subtract` e le richieste `Multiply` e `Divide`), in quanto la transazione client non si è propagata fino a tali azioni.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per compilare la C# versione o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2. Verificare che sia stato installato SQL Server Express Edition o SQL Server e che la stringa di connessione sia stata impostata correttamente nel file di configurazione dell'applicazione del servizio. Per eseguire l'esempio senza usare un database, impostare il valore `usingSql` nel file di configurazione dell'applicazione del servizio su `false`  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Nella configurazione con più computer abilitare Distributed Transaction Coordinator usando le istruzioni seguenti e usare lo strumento WsatConfig.exe di Windows SDK per abilitare il supporto di rete delle transazioni WCF. Per informazioni sulla configurazione di WsatConfig. exe, vedere [configurazione del supporto per le transazioni WS-Atomic](../feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Sia che si esegua l'esempio nello stesso computer o in computer diversi, è necessario configurare Microsoft Distributed Transaction Coordinator (MSDTC) per abilitare il flusso delle transazioni di rete e utilizzare lo strumento WsatConfig. exe per abilitare il supporto di rete delle transazioni WCF.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>Per configurare Microsoft Distributed Transaction Coordinator (MSDTC) per supportare l'esecuzione dell'esempio  
  
1. In un computer del servizio che esegue Windows Server 2003 o Windows XP configurare MSDTC per consentire transazioni di rete in ingresso seguendo queste istruzioni.  
  
    1. Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.  
  
    2. Espandere **Servizi componenti**. Aprire la cartella **computer** .  
  
    3. Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.  
  
    4. Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.  
  
    5. Controllare **l'accesso di rete DTC** e **consentire il traffico in ingresso**.  
  
    6. Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.  
  
    7. Scegliere **OK** per chiudere la finestra di dialogo.  
  
2. In un computer del servizio che esegue Windows Server 2008 o Windows Vista configurare MSDTC per consentire transazioni di rete in ingresso seguendo queste istruzioni.  
  
    1. Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.  
  
    2. Espandere **Servizi componenti**. Aprire la cartella **computer** . Selezionare **Distributed Transaction Coordinator**.  
  
    3. Fare doppio clic su **coordinatore DTC** e selezionare **Proprietà**.  
  
    4. Nella scheda **sicurezza** selezionare accesso di **rete DTC** e **Consenti connessioni in ingresso**.  
  
    5. Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.  
  
    6. Scegliere **OK** per chiudere la finestra di dialogo.  
  
3. Nel computer client configurare MSDTC per consentire le transazioni di rete in uscita.  
  
    1. Dal menu **Start** passare a `Control Panel`, quindi strumenti di **Amministrazione**e quindi **Servizi componenti**.  
  
    2. Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.  
  
    3. Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.  
  
    4. Controllare **l'accesso di rete DTC** e **consentire il traffico in uscita**.  
  
    5. Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.  
  
    6. Scegliere **OK** per chiudere la finestra di dialogo.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
