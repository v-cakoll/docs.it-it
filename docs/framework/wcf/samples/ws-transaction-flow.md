---
title: Flusso delle transazioni WS
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 1fbde53289c147d8ea273b9c86e65cbb8e262b30
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596410"
---
# <a name="ws-transaction-flow"></a><span data-ttu-id="c8da5-102">Flusso delle transazioni WS</span><span class="sxs-lookup"><span data-stu-id="c8da5-102">WS Transaction Flow</span></span>
<span data-ttu-id="c8da5-103">Questo esempio dimostra l'uso di una transazione coordinata dal client e le opzioni client e server per il flusso delle transazioni mediante il protocollo WS-Atomic Transaction o OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="c8da5-103">This sample demonstrates the use of a client-coordinated transaction and the client and server options for transaction flow using either the WS-Atomic Transaction or OleTransactions protocol.</span></span> <span data-ttu-id="c8da5-104">Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice, ma le operazioni sono attribuite per illustrare l'uso di `TransactionFlowAttribute` con l'enumerazione **TransactionFlowOption** per determinare in quale misura il flusso delle transazioni è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c8da5-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service but the operations are attributed to demonstrate the use of the `TransactionFlowAttribute` with the **TransactionFlowOption** enumeration to determine to what degree transaction flow is enabled.</span></span> <span data-ttu-id="c8da5-105">All'interno dell'ambito della transazione propagata, viene scritto un log delle operazioni richieste in un database che persiste fino a che la transazione coordinata dal client non è stata completata; se la transazione client non viene completata, la transazione del servizio Web assicura che non venga eseguito il commit degli aggiornamenti appropriati al database.</span><span class="sxs-lookup"><span data-stu-id="c8da5-105">Within the scope of the flowed transaction, a log of the requested operations is written to a database and persists until the client coordinated transaction has completed - if the client transaction does not complete, the Web service transaction ensures that the appropriate updates to the database are not committed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8da5-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c8da5-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c8da5-107">Dopo avere avviato una connessione con il servizio e una transazione, il client accede ad alcune operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-107">After initiating a connection to the service and a transaction, the client accesses several service operations.</span></span> <span data-ttu-id="c8da5-108">Il contratto per il servizio è definito come segue, con ognuna delle operazioni che dimostra un'impostazione diversa per `TransactionFlowOption`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-108">The contract for the service is defined as follows with each of the operations demonstrating a different setting for the `TransactionFlowOption`.</span></span>  

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

 <span data-ttu-id="c8da5-109">Questo definisce le operazioni nell'ordine in cui devono essere elaborate:</span><span class="sxs-lookup"><span data-stu-id="c8da5-109">This defines the operations in the order they are to be processed:</span></span>  
  
- <span data-ttu-id="c8da5-110">Una richiesta di operazione `Add` deve includere una transazione propagata.</span><span class="sxs-lookup"><span data-stu-id="c8da5-110">An `Add` operation request must include a flowed transaction.</span></span>  
  
- <span data-ttu-id="c8da5-111">Una richiesta di operazione `Subtract` può includere una transazione propagata.</span><span class="sxs-lookup"><span data-stu-id="c8da5-111">A `Subtract` operation request may include a flowed transaction.</span></span>  
  
- <span data-ttu-id="c8da5-112">Una richiesta di operazione `Multiply` non deve includere una transazione propagata mediante l'impostazione esplicita NotAllowed.</span><span class="sxs-lookup"><span data-stu-id="c8da5-112">A `Multiply` operation request must not include a flowed transaction through the explicit NotAllowed setting.</span></span>  
  
- <span data-ttu-id="c8da5-113">Una richiesta di operazione `Divide` non deve includere una transazione propagata mediante l'omissione di un attributo `TransactionFlow`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-113">A `Divide` operation request must not include a flowed transaction through the omission of a `TransactionFlow` attribute.</span></span>  
  
 <span data-ttu-id="c8da5-114">Per abilitare il flusso delle transazioni, è necessario utilizzare le associazioni con la [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) proprietà abilitata in aggiunta agli attributi dell'operazione appropriati.</span><span class="sxs-lookup"><span data-stu-id="c8da5-114">To enable transaction flow, bindings with the [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) property enabled must be used in addition to the appropriate operation attributes.</span></span> <span data-ttu-id="c8da5-115">In questo esempio, la configurazione del servizio espone un endpoint TCP e un endpoint HTTP oltre a un endpoint di scambio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c8da5-115">In this sample, the service's configuration exposes a TCP endpoint and an HTTP endpoint in addition to a Metadata Exchange endpoint.</span></span> <span data-ttu-id="c8da5-116">L'endpoint TCP e l'endpoint HTTP utilizzano le associazioni seguenti, entrambe le quali hanno la [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) proprietà abilitata.</span><span class="sxs-lookup"><span data-stu-id="c8da5-116">The TCP endpoint and the HTTP endpoint use the following bindings, both of which have the [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) property enabled.</span></span>  
  
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
> <span data-ttu-id="c8da5-117">L'associazione netTcpBinding fornita dal sistema consente di specificare il transactionProtocol mentre la wsHttpBinding fornita dal sistema usa solo il protocollo WSAtomicTransactionOctober2004 più interoperabile.</span><span class="sxs-lookup"><span data-stu-id="c8da5-117">The system-provided netTcpBinding allows specification of the transactionProtocol whereas the system-provided wsHttpBinding uses only the more interoperable WSAtomicTransactionOctober2004 protocol.</span></span> <span data-ttu-id="c8da5-118">Il protocollo OleTransactions è disponibile solo per l'uso da parte dei client Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c8da5-118">The OleTransactions protocol is only available for use by Windows Communication Foundation (WCF) clients.</span></span>  
  
 <span data-ttu-id="c8da5-119">Per la classe che implementa l'interfaccia `ICalculator`, a tutti i metodi viene attribuita la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-119">For the class that implements the `ICalculator` interface, all of the methods are attributed with <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property set to `true`.</span></span> <span data-ttu-id="c8da5-120">Questa impostazione dichiara che tutte le azioni intraprese all'interno del metodo avvengono all'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="c8da5-120">This setting declares that all actions taken within the method occur within the scope of a transaction.</span></span> <span data-ttu-id="c8da5-121">In questo caso, le azioni intraprese includono la registrazione sul database del log.</span><span class="sxs-lookup"><span data-stu-id="c8da5-121">In this case, the actions taken include recording to the log database.</span></span> <span data-ttu-id="c8da5-122">Se la richiesta dell'operazione include una transazione propagata allora le azioni avvengono all'interno dell'ambito della transazione in ingresso o viene generato automaticamente un nuovo ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="c8da5-122">If the operation request includes a flowed transaction then the actions occur within the scope of the incoming transaction or a new transaction scope is automatically generated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8da5-123">La proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> definisce il comportamento locale alle implementazioni del metodo del servizio e non definisce la capacità o la necessità del client di propagare una transazione.</span><span class="sxs-lookup"><span data-stu-id="c8da5-123">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property defines behavior local to the service method implementations and does not define the client's ability to or requirement for flowing a transaction.</span></span>  

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

 <span data-ttu-id="c8da5-124">Nel client, le impostazioni `TransactionFlowOption` del servizio sulle operazioni vengono riflesse nella definizione generata del client relativa all'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-124">On the client, the service's `TransactionFlowOption` settings on the operations are reflected in the client's generated definition of the `ICalculator` interface.</span></span> <span data-ttu-id="c8da5-125">Inoltre, le impostazioni della proprietà di `transactionFlow` del servizio sono riflesse nella configurazione dell'applicazione del client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-125">Also, the service's `transactionFlow` property settings are reflected in the client's application configuration.</span></span> <span data-ttu-id="c8da5-126">Il client può determinare il trasporto e il protocollo selezionando l'endpoint `endpointConfigurationName` appropriato.</span><span class="sxs-lookup"><span data-stu-id="c8da5-126">The client can select the transport and protocol by selecting the appropriate `endpointConfigurationName`.</span></span>  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> <span data-ttu-id="c8da5-127">Il comportamento osservato di questo esempio è lo stesso indipendentemente dal protocollo o dal trasporto scelto.</span><span class="sxs-lookup"><span data-stu-id="c8da5-127">The observed behavior of this sample is the same no matter which protocol or transport is chosen.</span></span>  
  
 <span data-ttu-id="c8da5-128">Dopo avere avviato la connessione al servizio, il client crea un nuovo `TransactionScope` intorno alle chiamate alle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-128">Having initiated the connection to the service, the client creates a new `TransactionScope` around the calls to the service operations.</span></span>  

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

 <span data-ttu-id="c8da5-129">Le chiamate alle operazioni sono come segue:</span><span class="sxs-lookup"><span data-stu-id="c8da5-129">The calls to the operations are as follows:</span></span>  
  
- <span data-ttu-id="c8da5-130">La richiesta `Add` propaga la transazione richiesta al servizio e le azioni del servizio si verificano all'interno dell'ambito della transazione del client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-130">The `Add` request flows the required transaction to the service and the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="c8da5-131">Anche la prima richiesta `Subtract` propaga la transazione consentita al servizio e di nuovo le azioni del servizio si verificano all'interno dell'ambito della transazione del client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-131">The first `Subtract` request also flows the allowed transaction to the service and again the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="c8da5-132">La seconda richiesta `Subtract` viene eseguita all'interno di un nuovo ambito della transazione dichiarato con l'opzione `TransactionScopeOption.Suppress`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-132">The second `Subtract` request is performed within a new transaction scope declared with the `TransactionScopeOption.Suppress` option.</span></span> <span data-ttu-id="c8da5-133">Questo sopprime la transazione esterna iniziale del client e la richiesta non propaga una transazione al servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-133">This suppresses the client's initial outer transaction and the request does not flow a transaction to the service.</span></span> <span data-ttu-id="c8da5-134">Questo approccio consente a un client di rinunciare esplicitamente e protegge dalla propagazione di una transazione a un servizio quando non viene richiesta.</span><span class="sxs-lookup"><span data-stu-id="c8da5-134">This approach allows a client to explicitly opt-out of and protect against flowing a transaction to a service when that is not required.</span></span> <span data-ttu-id="c8da5-135">Le azioni del servizio avvengono all'interno dell'ambito di una nuova transazione non connessa.</span><span class="sxs-lookup"><span data-stu-id="c8da5-135">The service's actions occur within the scope of a new and unconnected transaction.</span></span>  
  
- <span data-ttu-id="c8da5-136">La richiesta `Multiply` non propaga una transazione al servizio, in quanto la definizione generata del client relativa all'interfaccia `ICalculator` include un oggetto <xref:System.ServiceModel.TransactionFlowAttribute> impostato su <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-136">The `Multiply` request does not flow a transaction to the service because the client's generated definition of the `ICalculator` interface includes a <xref:System.ServiceModel.TransactionFlowAttribute> set to <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.</span></span>  
  
- <span data-ttu-id="c8da5-137">La richiesta `Divide` non propaga una transazione al servizio, in quanto di nuovo la definizione generata del client relativa all'interfaccia `ICalculator` non include un oggetto `TransactionFlowAttribute`.</span><span class="sxs-lookup"><span data-stu-id="c8da5-137">The `Divide` request does not flow a transaction to the service because again the client's generated definition of the `ICalculator` interface does not include a `TransactionFlowAttribute`.</span></span> <span data-ttu-id="c8da5-138">Le azioni del servizio avvengono nuovamente all'interno dell'ambito di un'altra nuova transazione non connessa.</span><span class="sxs-lookup"><span data-stu-id="c8da5-138">The service's actions again occur within the scope of another new and unconnected transaction.</span></span>  
  
 <span data-ttu-id="c8da5-139">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-139">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c8da5-140">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-140">Press ENTER in the client window to shut down the client.</span></span>  
  
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
  
 <span data-ttu-id="c8da5-141">La registrazione delle richieste di operazione del servizio viene visualizzata nella finestra della console del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-141">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="c8da5-142">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-142">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 <span data-ttu-id="c8da5-143">Dopo un'esecuzione corretta, l'ambito della transazione del client viene completato e viene eseguito il commit di tutte le azioni intraprese all'interno di quel ambito.</span><span class="sxs-lookup"><span data-stu-id="c8da5-143">After a successful execution, the client's transaction scope completes and all actions taken within that scope are committed.</span></span> <span data-ttu-id="c8da5-144">In particolare, i 5 record menzionati vengono resi permanenti nel database del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-144">Specifically, the noted 5 records are persisted in the service's database.</span></span> <span data-ttu-id="c8da5-145">I primi 2 di questi si sono verificati all'interno dell'ambito della transazione del client.</span><span class="sxs-lookup"><span data-stu-id="c8da5-145">The first 2 of these have occurred within the scope of the client's transaction.</span></span>  
  
 <span data-ttu-id="c8da5-146">Se si verifica un'eccezione in un punto qualsiasi all'interno dell'oggetto `TransactionScope` del client, la transazione non potrà essere completata.</span><span class="sxs-lookup"><span data-stu-id="c8da5-146">If an exception occurred anywhere within the client's `TransactionScope` then the transaction cannot complete.</span></span> <span data-ttu-id="c8da5-147">Ciò impedisce il commit nel database dei record registrati all'interno di quell'ambito.</span><span class="sxs-lookup"><span data-stu-id="c8da5-147">This causes the records logged within that scope to not be committed to the database.</span></span> <span data-ttu-id="c8da5-148">Questo effetto può essere osservato ripetendo l'esecuzione dell'esempio dopo avere impostato come commento la chiamata per il completamento dell'oggetto `TransactionScope` esterno.</span><span class="sxs-lookup"><span data-stu-id="c8da5-148">This effect can be observed by repeating the sample run after commenting out the call to complete the outer `TransactionScope`.</span></span> <span data-ttu-id="c8da5-149">In una tale esecuzione, vengono registrate solo le ultime 3 azioni (dalla seconda richiesta `Subtract` e le richieste `Multiply` e `Divide`), in quanto la transazione client non si è propagata fino a tali azioni.</span><span class="sxs-lookup"><span data-stu-id="c8da5-149">On such a run, only the last 3 actions (from the second `Subtract`, the `Multiply` and the `Divide` requests) are logged because the client transaction did not flow to those.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c8da5-150">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="c8da5-150">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c8da5-151">Per compilare la versione C# o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="c8da5-151">To build the C# or Visual Basic .NET version of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md)</span></span>  
  
2. <span data-ttu-id="c8da5-152">Verificare che sia stato installato SQL Server Express Edition o SQL Server e che la stringa di connessione sia stata impostata correttamente nel file di configurazione dell'applicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8da5-152">Ensure that you have installed SQL Server Express Edition or SQL Server, and that the connection string has been correctly set in the service’s application configuration file.</span></span> <span data-ttu-id="c8da5-153">Per eseguire l'esempio senza usare un database, impostare il valore `usingSql` nel file di configurazione dell'applicazione del servizio su `false`</span><span class="sxs-lookup"><span data-stu-id="c8da5-153">To run the sample without using a database, set the `usingSql` value in the service’s application configuration file to `false`</span></span>  
  
3. <span data-ttu-id="c8da5-154">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8da5-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c8da5-155">Nella configurazione con più computer abilitare Distributed Transaction Coordinator usando le istruzioni seguenti e usare lo strumento WsatConfig.exe di Windows SDK per abilitare il supporto di rete delle transazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="c8da5-155">For cross-machine configuration, enable the Distributed Transaction Coordinator using the instructions below, and use the WsatConfig.exe tool from the Windows SDK to enable WCF Transactions network support.</span></span> <span data-ttu-id="c8da5-156">Per informazioni sulla configurazione di WsatConfig. exe, vedere [configurazione del supporto per le transazioni WS-Atomic](../feature-details/configuring-ws-atomic-transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="c8da5-156">For information on setting up WsatConfig.exe, see [Configuring WS-Atomic Transaction Support](../feature-details/configuring-ws-atomic-transaction-support.md).</span></span>  
  
 <span data-ttu-id="c8da5-157">Sia che si esegua l'esempio nello stesso computer o in computer diversi, è necessario configurare Microsoft Distributed Transaction Coordinator (MSDTC) per abilitare il flusso delle transazioni di rete e utilizzare lo strumento WsatConfig. exe per abilitare il supporto di rete delle transazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="c8da5-157">Whether you run the sample on the same computer or on different computers, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable WCF transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a><span data-ttu-id="c8da5-158">Per configurare Microsoft Distributed Transaction Coordinator (MSDTC) per supportare l'esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="c8da5-158">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample</span></span>  
  
1. <span data-ttu-id="c8da5-159">In un computer del servizio che esegue Windows Server 2003 o Windows XP configurare MSDTC per consentire transazioni di rete in ingresso seguendo queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8da5-159">On a service machine running Windows Server 2003 or Windows XP, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="c8da5-160">Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-160">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="c8da5-161">Espandere **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-161">Expand **Component Services**.</span></span> <span data-ttu-id="c8da5-162">Aprire la cartella **computer** .</span><span class="sxs-lookup"><span data-stu-id="c8da5-162">Open the **Computers** folder.</span></span>  
  
    3. <span data-ttu-id="c8da5-163">Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-163">Right-click **My Computer** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="c8da5-164">Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-164">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    5. <span data-ttu-id="c8da5-165">Controllare **l'accesso di rete DTC** e **consentire il traffico in ingresso**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-165">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    6. <span data-ttu-id="c8da5-166">Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="c8da5-166">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    7. <span data-ttu-id="c8da5-167">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c8da5-167">Click **OK** to close the dialog box.</span></span>  
  
2. <span data-ttu-id="c8da5-168">In un computer del servizio che esegue Windows Server 2008 o Windows Vista configurare MSDTC per consentire transazioni di rete in ingresso seguendo queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8da5-168">On a service machine running Windows Server 2008 or Windows Vista, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="c8da5-169">Dal menu **Start** passare a pannello di **controllo**, quindi **strumenti di amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="c8da5-170">Espandere **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-170">Expand **Component Services**.</span></span> <span data-ttu-id="c8da5-171">Aprire la cartella **computer** .</span><span class="sxs-lookup"><span data-stu-id="c8da5-171">Open the **Computers** folder.</span></span> <span data-ttu-id="c8da5-172">Selezionare **Distributed Transaction Coordinator**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-172">Select **Distributed Transaction Coordinator**.</span></span>  
  
    3. <span data-ttu-id="c8da5-173">Fare doppio clic su **coordinatore DTC** e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-173">Right-click **DTC Coordinator** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="c8da5-174">Nella scheda **sicurezza** selezionare accesso di **rete DTC** e **Consenti connessioni in ingresso**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-174">On the **Security** tab, check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5. <span data-ttu-id="c8da5-175">Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="c8da5-175">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="c8da5-176">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c8da5-176">Click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="c8da5-177">Nel computer client configurare MSDTC per consentire le transazioni di rete in uscita.</span><span class="sxs-lookup"><span data-stu-id="c8da5-177">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1. <span data-ttu-id="c8da5-178">Dal menu **Start** passare a `Control Panel` , quindi strumenti di **Amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-178">From the **Start** menu, navigate to `Control Panel`, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="c8da5-179">Fare clic con il pulsante destro del mouse su **computer locale** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-179">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3. <span data-ttu-id="c8da5-180">Nella scheda **MSDTC** fare clic su **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-180">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4. <span data-ttu-id="c8da5-181">Controllare **l'accesso di rete DTC** e **consentire il traffico in uscita**.</span><span class="sxs-lookup"><span data-stu-id="c8da5-181">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5. <span data-ttu-id="c8da5-182">Fare clic su **OK**e quindi su **Sì** per riavviare il servizio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="c8da5-182">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="c8da5-183">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c8da5-183">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c8da5-184">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c8da5-184">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8da5-185">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c8da5-185">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c8da5-186">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="c8da5-186">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8da5-187">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="c8da5-187">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
