---
title: Comportamento delle transazioni di un servizio
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: 38ad03d64d95e0653fba8018c59c62db9a698096
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715115"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="aa66d-102">Comportamento delle transazioni di un servizio</span><span class="sxs-lookup"><span data-stu-id="aa66d-102">Service Transaction Behavior</span></span>

<span data-ttu-id="aa66d-103">In questo esempio vengono illustrati l'uso di una transazione coordinata dal client e le impostazioni di ServiceBehaviorAttribute e OperationBehaviorAttribute per controllare il comportamento delle transazioni di un servizio.</span><span class="sxs-lookup"><span data-stu-id="aa66d-103">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="aa66d-104">Questo esempio si basa sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice, ma viene esteso per gestire un log del server delle operazioni eseguite in una tabella di database e un totale di esecuzione con stato per le operazioni della calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="aa66d-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="aa66d-105">Le scritture rese permanenti nella tabella del registro sul server dipendono dal risultato di una transazione coordinata dal client: se la transazione client non viene completata, la transazione del servizio Web assicura che non venga eseguito il commit degli aggiornamenti al database.</span><span class="sxs-lookup"><span data-stu-id="aa66d-105">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>

> [!NOTE]
> <span data-ttu-id="aa66d-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="aa66d-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="aa66d-107">Nel contratto per il servizio è definito che per tutte le operazioni è necessario che una transazione venga propagata con le richieste:</span><span class="sxs-lookup"><span data-stu-id="aa66d-107">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>

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

<span data-ttu-id="aa66d-108">Per abilitare il flusso della transazione in ingresso, il servizio viene configurato con l'wsHttpBinding fornito dal sistema con l'attributo TransactionFlow impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="aa66d-108">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="aa66d-109">Questa associazione utilizza il protocollo WSAtomicTransactionOctober2004 interoperativo:</span><span class="sxs-lookup"><span data-stu-id="aa66d-109">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>

```xml
<bindings>
  <wsHttpBinding>
    <binding name="transactionalBinding" transactionFlow="true" />
  </wsHttpBinding>
</bindings>
```

<span data-ttu-id="aa66d-110">Dopo aver iniziato una connessione al servizio e a una transazione, il client accede a numerose operazioni del servizio all'interno dell'ambito di tale transazione e quindi completa la transazione e chiude la connessione:</span><span class="sxs-lookup"><span data-stu-id="aa66d-110">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>

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

<span data-ttu-id="aa66d-111">Nel servizio sono presenti tre attribuiti che influiscono sul comportamento delle transazioni del servizio nelle modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa66d-111">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>

- <span data-ttu-id="aa66d-112">Per `ServiceBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="aa66d-112">On the `ServiceBehaviorAttribute`:</span></span>

  - <span data-ttu-id="aa66d-113">La proprietà `TransactionTimeout` specifica il periodo di timeout entro il quale una transazione deve essere completata.</span><span class="sxs-lookup"><span data-stu-id="aa66d-113">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="aa66d-114">In questo esempio è impostato su 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="aa66d-114">In this sample it is set to 30 seconds.</span></span>

  - <span data-ttu-id="aa66d-115">La proprietà `TransactionIsolationLevel` specifica il livello di isolamento della transazione supportato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="aa66d-115">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="aa66d-116">Questo valore deve corrispondere al livello di isolamento del client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-116">This is required to match the client's isolation level.</span></span>

  - <span data-ttu-id="aa66d-117">La proprietà `ReleaseServiceInstanceOnTransactionComplete` specifica se l'istanza del servizio sottostante viene riciclata al completamento di una transazione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-117">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="aa66d-118">Impostando questa proprietà su `false`, il servizio gestisce la stessa istanza del servizio tra varie richieste di operazione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-118">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="aa66d-119">Questo aspetto è necessario per gestire il totale parziale.</span><span class="sxs-lookup"><span data-stu-id="aa66d-119">This is required to maintain the running total.</span></span> <span data-ttu-id="aa66d-120">Se la proprietà è impostata su `true`, viene generata una nuova istanza dopo ogni azione completata.</span><span class="sxs-lookup"><span data-stu-id="aa66d-120">If set to `true`, a new instance is generated after each completed action.</span></span>

  - <span data-ttu-id="aa66d-121">La proprietà `TransactionAutoCompleteOnSessionClose` specifica se alla chiusura della sessione corrente vengono completate le transazioni in attesa.</span><span class="sxs-lookup"><span data-stu-id="aa66d-121">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="aa66d-122">Impostando la proprietà su `false`, le singole operazioni sono necessarie per impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> su `true` o per richiedere in modo esplicito una chiamata al metodo <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> per completare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="aa66d-122">By setting it to `false`, the individual operations are required to either set the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> property to `true` or to explicitly require a call to the <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> method to complete transactions.</span></span> <span data-ttu-id="aa66d-123">Nell'esempio vengono illustrati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="aa66d-123">This sample demonstrates both approaches.</span></span>

- <span data-ttu-id="aa66d-124">Per `ServiceContractAttribute`:</span><span class="sxs-lookup"><span data-stu-id="aa66d-124">On the `ServiceContractAttribute`:</span></span>

  - <span data-ttu-id="aa66d-125">La proprietà `SessionMode` specifica se il servizio correla le richieste appropriate in una sessione logica.</span><span class="sxs-lookup"><span data-stu-id="aa66d-125">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="aa66d-126">Poiché questo servizio include operazioni in cui la proprietà OperationBehaviorAttribute TransactionAutoComplete è impostata su `false` (Multiply e Divide), è necessario specificare `SessionMode.Required`.</span><span class="sxs-lookup"><span data-stu-id="aa66d-126">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="aa66d-127">Ad esempio, l'operazione Multiply non completa la relativa transazione e si basa su una chiamata successiva a Divide completarla utilizzando il metodo `SetTransactionComplete`; il servizio deve essere in grado di determinare che queste operazioni sono in esecuzione all'interno della stessa sessione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-127">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>

- <span data-ttu-id="aa66d-128">Per `OperationBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="aa66d-128">On the `OperationBehaviorAttribute`:</span></span>

  - <span data-ttu-id="aa66d-129">La proprietà `TransactionScopeRequired` specifica se le azioni dell'operazione devono essere eseguite all'interno di un ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-129">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="aa66d-130">È impostata su `true` per tutte le operazioni in questo esempio e, poiché il client propaga la relativa transazione a tutte le operazioni, le azioni si verificano all'interno dell'ambito di tale transazione del client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-130">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>

  - <span data-ttu-id="aa66d-131">La proprietà `TransactionAutoComplete` specifica la transazione in cui viene eseguito il metodo viene completata automaticamente se non si verificano eccezioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="aa66d-131">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="aa66d-132">Come descritto in precedenza, questa proprietà è impostata su `true` per le operazioni Add e Subtract, e su `false` per le operazioni Multiply e Divide.</span><span class="sxs-lookup"><span data-stu-id="aa66d-132">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="aa66d-133">Le operazioni Add e Subtract completano automaticamente le azioni, mentre Divide completa le azioni tramite una chiamata esplicita al metodo `SetTransactionComplete`. Multiply non completa le azioni, bensì si basa necessariamente su una chiamata successiva, ad esempio a Divide, per completare le azioni.</span><span class="sxs-lookup"><span data-stu-id="aa66d-133">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>

<span data-ttu-id="aa66d-134">L'implementazione del servizio con gli attributi è illustrata di seguito:</span><span class="sxs-lookup"><span data-stu-id="aa66d-134">The attributed service implementation is as follows:</span></span>

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

<span data-ttu-id="aa66d-135">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-135">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="aa66d-136">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-136">Press ENTER in the client window to shut down the client.</span></span>

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

<span data-ttu-id="aa66d-137">La registrazione delle richieste di operazione del servizio viene visualizzata nella finestra della console del servizio.</span><span class="sxs-lookup"><span data-stu-id="aa66d-137">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="aa66d-138">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-138">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate service.
Creating new service instance...
  Writing row 1 to database: Adding 100 to 0
  Writing row 2 to database: Subtracting 45 from 100
  Writing row 3 to database: Multiplying 55 by 9
  Writing row 4 to database: Dividing 495 by 15
```

<span data-ttu-id="aa66d-139">Si noti che, oltre a gestire il totale parziale dei calcoli, il servizio segnala la creazione di istanze (un'istanza per questo esempio) e registra le richieste di operazione in un database.</span><span class="sxs-lookup"><span data-stu-id="aa66d-139">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="aa66d-140">Poiché tutte le richieste vengono propagate alla transazione del client, qualsiasi errore nel completamento della transazione comporta il rollback di tutte le operazioni del database.</span><span class="sxs-lookup"><span data-stu-id="aa66d-140">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="aa66d-141">Questa situazione può essere dimostrata in vari modi:</span><span class="sxs-lookup"><span data-stu-id="aa66d-141">This can be demonstrated in a number of ways:</span></span>

- <span data-ttu-id="aa66d-142">Commentare la chiamata del client a `tx.Complete`() ed eseguirla di nuovo; questo comporta l'uscita del client dall'ambito della transazione senza completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-142">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>

- <span data-ttu-id="aa66d-143">Commentare la chiamata all'operazione del servizio Divide; questo impedisce il completamento dell'azione iniziata dall'operazione Multiply e, di conseguenza, della transazione del client.</span><span class="sxs-lookup"><span data-stu-id="aa66d-143">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>

- <span data-ttu-id="aa66d-144">Generare un'eccezione non gestita in un punto qualsiasi dell'ambito della transazione del client; anche questa operazione impedisce al client di completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="aa66d-144">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>

<span data-ttu-id="aa66d-145">Il risultato di queste proceduta è che non viene eseguito il commit di nessuna delle operazioni eseguite all'interno di tale ambito e il conteggio delle righe reso persistente nel database non viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="aa66d-145">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>

> [!NOTE]
> <span data-ttu-id="aa66d-146">Nell'ambito del processo di compilazione, il file di database viene copiato nella cartella bin.</span><span class="sxs-lookup"><span data-stu-id="aa66d-146">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="aa66d-147">È necessario esaminare tale copia del file di database per osservare le righe persistenti nel registro anziché il file incluso nel progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa66d-147">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="aa66d-148">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="aa66d-148">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="aa66d-149">Verificare di avere installato SQL Server 2005 Express Edition o SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aa66d-149">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="aa66d-150">Nel file App.config del servizio, può essere impostato il database `connectionString` oppure le interazioni del database possono essere disabilitate impostando il valore `usingSql` di appSettings su `false`.</span><span class="sxs-lookup"><span data-stu-id="aa66d-150">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>

2. <span data-ttu-id="aa66d-151">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aa66d-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="aa66d-152">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aa66d-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="aa66d-153">Se si esegue l'esempio tra più computer, è necessario configurare Microsoft Distributed Transaction Coordinator (MSDTC) per abilitare il flusso delle transazioni di rete e usare lo strumento WsatConfig. exe per abilitare la rete delle transazioni Windows Communication Foundation (WCF) supporto.</span><span class="sxs-lookup"><span data-stu-id="aa66d-153">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>

### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="aa66d-154">Per configurare Microsoft Distributed Transaction Coordinator (MSDTC) allo scopo di supportare l'esecuzione dell'esempio tra diversi computer</span><span class="sxs-lookup"><span data-stu-id="aa66d-154">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>

1. <span data-ttu-id="aa66d-155">Nel computer del servizio configurare MSDTC per consentire le transazioni di rete in ingresso.</span><span class="sxs-lookup"><span data-stu-id="aa66d-155">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>

    1. <span data-ttu-id="aa66d-156">Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-156">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="aa66d-157">Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-157">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="aa66d-158">Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-158">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="aa66d-159">Controllare **l'accesso di rete DTC** e **consentire il traffico in ingresso**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-159">Check **Network DTC Access** and **Allow Inbound**.</span></span>

    5. <span data-ttu-id="aa66d-160">Fare clic su **Sì** per riavviare il servizio MS DTC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-160">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="aa66d-161">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="aa66d-161">Click **OK** to close the dialog box.</span></span>

2. <span data-ttu-id="aa66d-162">Nel computer del servizio e nel computer client configurare Windows Firewall per includere Microsoft Distributed Transaction Coordinator (MSDTC) nell'elenco delle applicazioni accettate:</span><span class="sxs-lookup"><span data-stu-id="aa66d-162">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>

    1. <span data-ttu-id="aa66d-163">Eseguire l'applicazione Windows Firewall dal Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="aa66d-163">Run the Windows Firewall application from Control Panel.</span></span>

    2. <span data-ttu-id="aa66d-164">Nella scheda **eccezioni** fare clic su **Aggiungi programma**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-164">From the **Exceptions** tab, click **Add Program**.</span></span>

    3. <span data-ttu-id="aa66d-165">Passare alla cartella C:\WINDOWS\System32.</span><span class="sxs-lookup"><span data-stu-id="aa66d-165">Browse to the folder C:\WINDOWS\System32.</span></span>

    4. <span data-ttu-id="aa66d-166">Selezionare MSDTC. exe e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-166">Select Msdtc.exe and click **Open**.</span></span>

    5. <span data-ttu-id="aa66d-167">Fare clic su **OK** per chiudere la finestra di dialogo **Aggiungi programma** , quindi fare di nuovo clic su **ok** per chiudere l'applet Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="aa66d-167">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>

3. <span data-ttu-id="aa66d-168">Nel computer client configurare MSDTC per consentire le transazioni di rete in uscita.</span><span class="sxs-lookup"><span data-stu-id="aa66d-168">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>

    1. <span data-ttu-id="aa66d-169">Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="aa66d-170">Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-170">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="aa66d-171">Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-171">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="aa66d-172">Controllare **l'accesso di rete DTC** e **consentire il traffico in uscita**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-172">Check **Network DTC Access** and **Allow Outbound**.</span></span>

    5. <span data-ttu-id="aa66d-173">Fare clic su **Sì** per riavviare il servizio MS DTC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa66d-173">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="aa66d-174">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="aa66d-174">Click **OK** to close the dialog box.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa66d-175">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="aa66d-175">The samples may already be installed on your machine.</span></span> <span data-ttu-id="aa66d-176">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="aa66d-176">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="aa66d-177">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="aa66d-177">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="aa66d-178">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="aa66d-178">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`
