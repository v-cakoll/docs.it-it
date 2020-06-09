---
title: Comportamento delle transazioni di un servizio
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: 0be5bf0dbe6416febb898fb5150c5a516c8b0969
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591527"
---
# <a name="service-transaction-behavior"></a>Comportamento delle transazioni di un servizio

In questo esempio vengono illustrati l'uso di una transazione coordinata dal client e le impostazioni di ServiceBehaviorAttribute e OperationBehaviorAttribute per controllare il comportamento delle transazioni di un servizio. Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice, ma viene esteso per gestire un log del server delle operazioni eseguite in una tabella di database e un totale di esecuzione con stato per le operazioni della calcolatrice. Le scritture rese permanenti nella tabella del registro sul server dipendono dal risultato di una transazione coordinata dal client: se la transazione client non viene completata, la transazione del servizio Web assicura che non venga eseguito il commit degli aggiornamenti al database.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Nel contratto per il servizio è definito che per tutte le operazioni è necessario che una transazione venga propagata con le richieste:

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",
                    SessionMode = SessionMode.Required)]
public interface ICalculator
{
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Add(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Subtract(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Multiply(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Divide(double n);
}
```

Per abilitare il flusso della transazione in ingresso, il servizio viene configurato con l'wsHttpBinding fornito dal sistema con l'attributo TransactionFlow impostato su `true`. Questa associazione utilizza il protocollo WSAtomicTransactionOctober2004 interoperativo:

```xml
<bindings>
  <wsHttpBinding>
    <binding name="transactionalBinding" transactionFlow="true" />
  </wsHttpBinding>
</bindings>
```

Dopo aver iniziato una connessione al servizio e a una transazione, il client accede a numerose operazioni del servizio all'interno dell'ambito di tale transazione e quindi completa la transazione e chiude la connessione:

```csharp
// Create a client
CalculatorClient client = new CalculatorClient();

// Create a transaction scope with the default isolation level of Serializable
using (TransactionScope tx = new TransactionScope())
{
    Console.WriteLine("Starting transaction");

    // Call the Add service operation.
    double value = 100.00D;
    Console.WriteLine("  Adding {0}, running total={1}",
                                        value, client.Add(value));

    // Call the Subtract service operation.
    value = 45.00D;
    Console.WriteLine("  Subtracting {0}, running total={1}",
                                        value, client.Subtract(value));

    // Call the Multiply service operation.
    value = 9.00D;
    Console.WriteLine("  Multiplying by {0}, running total={1}",
                                        value, client.Multiply(value));

    // Call the Divide service operation.
    value = 15.00D;
    Console.WriteLine("  Dividing by {0}, running total={1}",
                                        value, client.Divide(value));

    Console.WriteLine("  Completing transaction");
    tx.Complete();
}

Console.WriteLine("Transaction committed");

// Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

Nel servizio sono presenti tre attribuiti che influiscono sul comportamento delle transazioni del servizio nelle modalità seguenti:

- Per `ServiceBehaviorAttribute`:

  - La proprietà `TransactionTimeout` specifica il periodo di timeout entro il quale una transazione deve essere completata. In questo esempio è impostato su 30 secondi.

  - La proprietà `TransactionIsolationLevel` specifica il livello di isolamento della transazione supportato dal servizio. Questo valore deve corrispondere al livello di isolamento del client.

  - La proprietà `ReleaseServiceInstanceOnTransactionComplete` specifica se l'istanza del servizio sottostante viene riciclata al completamento di una transazione. Impostando questa proprietà su `false`, il servizio gestisce la stessa istanza del servizio tra varie richieste di operazione. Questo aspetto è necessario per gestire il totale parziale. Se la proprietà è impostata su `true`, viene generata una nuova istanza dopo ogni azione completata.

  - La proprietà `TransactionAutoCompleteOnSessionClose` specifica se alla chiusura della sessione corrente vengono completate le transazioni in attesa. Impostando la `false` proprietà su, le singole operazioni devono impostare la <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> proprietà su `true` o per richiedere in modo esplicito una chiamata al <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> metodo per completare le transazioni. Nell'esempio vengono illustrati entrambi gli approcci.

- Per `ServiceContractAttribute`:

  - La proprietà `SessionMode` specifica se il servizio correla le richieste appropriate in una sessione logica. Poiché questo servizio include operazioni in cui la proprietà OperationBehaviorAttribute TransactionAutoComplete è impostata su `false` (Multiply e Divide), è necessario specificare `SessionMode.Required`. Ad esempio, l'operazione Multiply non completa la relativa transazione e si basa su una chiamata successiva a Divide completarla utilizzando il metodo `SetTransactionComplete`; il servizio deve essere in grado di determinare che queste operazioni sono in esecuzione all'interno della stessa sessione.

- Per `OperationBehaviorAttribute`:

  - La proprietà `TransactionScopeRequired` specifica se le azioni dell'operazione devono essere eseguite all'interno di un ambito della transazione. È impostata su `true` per tutte le operazioni in questo esempio e, poiché il client propaga la relativa transazione a tutte le operazioni, le azioni si verificano all'interno dell'ambito di tale transazione del client.

  - La proprietà `TransactionAutoComplete` specifica la transazione in cui viene eseguito il metodo viene completata automaticamente se non si verificano eccezioni non gestite. Come descritto in precedenza, questa proprietà è impostata su `true` per le operazioni Add e Subtract, e su `false` per le operazioni Multiply e Divide. Le operazioni Add e Subtract completano automaticamente le azioni, mentre Divide completa le azioni tramite una chiamata esplicita al metodo `SetTransactionComplete`. Multiply non completa le azioni, bensì si basa necessariamente su una chiamata successiva, ad esempio a Divide, per completare le azioni.

L'implementazione del servizio con gli attributi è illustrata di seguito:

```csharp
[ServiceBehavior(
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,
    TransactionTimeout = "00:00:30",
    ReleaseServiceInstanceOnTransactionComplete = false,
    TransactionAutoCompleteOnSessionClose = false)]
public class CalculatorService : ICalculator
{
    double runningTotal;

    public CalculatorService()
    {
        Console.WriteLine("Creating new service instance...");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Add(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));
        runningTotal = runningTotal + n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Subtract(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));
        runningTotal = runningTotal - n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Multiply(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));
        runningTotal = runningTotal * n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Divide(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));
        runningTotal = runningTotal / n;
        OperationContext.Current.SetTransactionComplete();
        return runningTotal;
    }

    // Logging method omitted for brevity
}
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Starting transaction
Performing calculations...
  Adding 100, running total=100
  Subtracting 45, running total=55
  Multiplying by 9, running total=495
  Dividing by 15, running total=33
  Completing transaction
Transaction committed
Press <ENTER> to terminate client.
```

La registrazione delle richieste di operazione del servizio viene visualizzata nella finestra della console del servizio. Premere INVIO nella finestra del client per arrestare il client.

```console
Press <ENTER> to terminate service.
Creating new service instance...
  Writing row 1 to database: Adding 100 to 0
  Writing row 2 to database: Subtracting 45 from 100
  Writing row 3 to database: Multiplying 55 by 9
  Writing row 4 to database: Dividing 495 by 15
```

Si noti che, oltre a gestire il totale parziale dei calcoli, il servizio segnala la creazione di istanze (un'istanza per questo esempio) e registra le richieste di operazione in un database. Poiché tutte le richieste vengono propagate alla transazione del client, qualsiasi errore nel completamento della transazione comporta il rollback di tutte le operazioni del database. Questa situazione può essere dimostrata in vari modi:

- Commentare la chiamata del client a `tx.Complete`() ed eseguirla di nuovo; questo comporta l'uscita del client dall'ambito della transazione senza completare la transazione.

- Commentare la chiamata all'operazione del servizio Divide; questo impedisce il completamento dell'azione iniziata dall'operazione Multiply e, di conseguenza, della transazione del client.

- Generare un'eccezione non gestita in un punto qualsiasi dell'ambito della transazione del client; anche questa operazione impedisce al client di completare la transazione.

Il risultato di queste proceduta è che non viene eseguito il commit di nessuna delle operazioni eseguite all'interno di tale ambito e il conteggio delle righe reso persistente nel database non viene incrementato.

> [!NOTE]
> Nell'ambito del processo di compilazione, il file di database viene copiato nella cartella bin. È necessario esaminare tale copia del file di database per osservare le righe persistenti nel registro anziché il file incluso nel progetto di Visual Studio.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Verificare di avere installato SQL Server 2005 Express Edition o SQL Server 2005. Nel file App.config del servizio, può essere impostato il database `connectionString` oppure le interazioni del database possono essere disabilitate impostando il valore `usingSql` di appSettings su `false`.

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

Se si esegue l'esempio tra più computer, è necessario configurare Microsoft Distributed Transaction Coordinator (MSDTC) per abilitare il flusso delle transazioni di rete e usare lo strumento WsatConfig. exe per abilitare il supporto di rete delle transazioni Windows Communication Foundation (WCF).

### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a>Per configurare Microsoft Distributed Transaction Coordinator (MSDTC) allo scopo di supportare l'esecuzione dell'esempio tra diversi computer

1. Nel computer del servizio configurare MSDTC per consentire le transazioni di rete in ingresso.

    1. Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.

    2. Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.

    3. Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.

    4. Controllare **l'accesso di rete DTC** e **consentire il traffico in ingresso**.

    5. Fare clic su **Sì** per riavviare il servizio MS DTC e quindi fare clic su **OK**.

    6. Fare clic su **OK** per chiudere la finestra di dialogo.

2. Nel computer del servizio e nel computer client configurare Windows Firewall per includere Microsoft Distributed Transaction Coordinator (MSDTC) nell'elenco delle applicazioni accettate:

    1. Eseguire l'applicazione Windows Firewall dal Pannello di controllo.

    2. Nella scheda **eccezioni** fare clic su **Aggiungi programma**.

    3. Passare alla cartella C:\WINDOWS\System32.

    4. Selezionare MSDTC. exe e fare clic su **Apri**.

    5. Fare clic su **OK** per chiudere la finestra di dialogo **Aggiungi programma** , quindi fare di nuovo clic su **ok** per chiudere l'applet Windows Firewall.

3. Nel computer client configurare MSDTC per consentire le transazioni di rete in uscita.

    1. Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.

    2. Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.

    3. Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.

    4. Controllare **l'accesso di rete DTC** e **consentire il traffico in uscita**.

    5. Fare clic su **Sì** per riavviare il servizio MS DTC e quindi fare clic su **OK**.

    6. Fare clic su **OK** per chiudere la finestra di dialogo.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`
