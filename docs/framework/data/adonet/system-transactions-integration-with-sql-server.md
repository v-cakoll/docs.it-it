---
title: Integrazione di System.Transactions con SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 42007dafbdc9f61b9fc0776e0aaa2987551b704a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174238"
---
# <a name="systemtransactions-integration-with-sql-server"></a><span data-ttu-id="85965-102">Integrazione di System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="85965-102">System.Transactions Integration with SQL Server</span></span>
<span data-ttu-id="85965-103">In .NET Framework versione 2.0 è stato introdotto un framework di transazione a cui è possibile accedere tramite lo <xref:System.Transactions> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="85965-103">The .NET Framework version 2.0 introduced a transaction framework that can be accessed through the <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="85965-104">Questo framework espone le transazioni in modo completamente integrato in .NET Framework, incluso ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="85965-104">This framework exposes transactions in a way that is fully integrated in the .NET Framework, including ADO.NET.</span></span>  
  
 <span data-ttu-id="85965-105">Oltre ai miglioramenti apportati <xref:System.Transactions> alla programmabilità e ADO.NET possono collaborare per coordinare le ottimizzazioni quando si lavora con le transazioni.</span><span class="sxs-lookup"><span data-stu-id="85965-105">In addition to the programmability enhancements, <xref:System.Transactions> and ADO.NET can work together to coordinate optimizations when you work with transactions.</span></span> <span data-ttu-id="85965-106">Una transazione promuovibile è una transazione di tipo semplice (locale) che può essere promossa in modo automatico a una transazione completamente distribuita in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="85965-106">A promotable transaction is a lightweight (local) transaction that can be automatically promoted to a fully distributed transaction on an as-needed basis.</span></span>  
  
 <span data-ttu-id="85965-107">A partire da ADO.NET <xref:System.Data.SqlClient> 2.0, supporta le transazioni promare table quando si lavora con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85965-107">Starting with ADO.NET 2.0, <xref:System.Data.SqlClient> supports promotable transactions when you work with SQL Server.</span></span> <span data-ttu-id="85965-108">Una transazione promuovibile non richiama l'overhead aggiunto di una transazione distribuita, a meno che non sia necessario.</span><span class="sxs-lookup"><span data-stu-id="85965-108">A promotable transaction does not invoke the added overhead of a distributed transaction unless the added overhead is required.</span></span> <span data-ttu-id="85965-109">Le transazioni promozionali sono automatiche e non richiedono alcun intervento da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="85965-109">Promotable transactions are automatic and require no intervention from the developer.</span></span>  
  
 <span data-ttu-id="85965-110">Le transazioni prommodificabili sono disponibili solo quando si utilizza`SqlClient`il provider di dati .NET Framework per SQL Server ( ) con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85965-110">Promotable transactions are only available when you use the .NET Framework Data Provider for SQL Server (`SqlClient`) with SQL Server.</span></span>  
  
## <a name="creating-promotable-transactions"></a><span data-ttu-id="85965-111">Creazione di transazioni promuovibili</span><span class="sxs-lookup"><span data-stu-id="85965-111">Creating Promotable Transactions</span></span>  
 <span data-ttu-id="85965-112">Il provider .NET Framework per SQL Server fornisce il supporto per le transazioni promobili, che vengono gestite tramite le classi nello spazio dei nomi .NET Framework. <xref:System.Transactions></span><span class="sxs-lookup"><span data-stu-id="85965-112">The .NET Framework Provider for SQL Server provides support for promotable transactions, which are handled through the classes in the .NET Framework <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="85965-113">Le transazioni promuovibili consentono di ottimizzare le transazioni distribuite rinviandone la creazione finché non è richiesta.</span><span class="sxs-lookup"><span data-stu-id="85965-113">Promotable transactions optimize distributed transactions by deferring creating a distributed transaction until it is needed.</span></span> <span data-ttu-id="85965-114">Se è necessario un solo gestore di risorse, non si verificherà alcuna transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-114">If only one resource manager is required, no distributed transaction occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85965-115">In un scenario ad attendibilità parziale è richiesto <xref:System.Transactions.DistributedTransactionPermission> quando una transazione viene promossa a transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-115">In a partially trusted scenario, the <xref:System.Transactions.DistributedTransactionPermission> is required when a transaction is promoted to a distributed transaction.</span></span>  
  
## <a name="promotable-transaction-scenarios"></a><span data-ttu-id="85965-116">Scenari di transazioni promuovibili</span><span class="sxs-lookup"><span data-stu-id="85965-116">Promotable Transaction Scenarios</span></span>  
 <span data-ttu-id="85965-117">In genere, le transazioni distribuite richiedono un notevole utilizzo delle risorse, in quanto sono gestite da Microsoft Distributed Transaction Coordinator (MS DTC) che integra tutti i gestori delle risorse a cui si accede nella transazione.</span><span class="sxs-lookup"><span data-stu-id="85965-117">Distributed transactions typically consume significant system resources, being managed by Microsoft Distributed Transaction Coordinator (MS DTC), which integrates all the resource managers accessed in the transaction.</span></span> <span data-ttu-id="85965-118">Una transazione promotable è <xref:System.Transactions> una forma speciale di una transazione che delega in modo efficace il lavoro a una semplice transazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85965-118">A promotable transaction is a special form of a <xref:System.Transactions> transaction that effectively delegates the work to a simple SQL Server transaction.</span></span> <span data-ttu-id="85965-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>e SQL Server coordinano il lavoro necessario per la gestione della transazione, promuovendola a transazione distribuita completa in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="85965-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, and SQL Server coordinate the work involved in handling the transaction, promoting it to a full distributed transaction as needed.</span></span>  
  
 <span data-ttu-id="85965-120">Il vantaggio derivante dall'utilizzo delle transazioni promuovibili consiste nel fatto che quando si apre una connessione tramite un transazione <xref:System.Transactions.TransactionScope> attiva e non sono presenti altre transazioni aperte, viene eseguito il commit della transazione come tipo semplice, anziché provocare l'overhead aggiuntivo di una piena transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-120">The benefit of using promotable transactions is that when a connection is opened by using an active <xref:System.Transactions.TransactionScope> transaction, and no other connections are opened, the transaction commits as a lightweight transaction, instead of incurring the additional overhead of a full distributed transaction.</span></span>  
  
### <a name="connection-string-keywords"></a><span data-ttu-id="85965-121">Parole chiave per le stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="85965-121">Connection String Keywords</span></span>  
 <span data-ttu-id="85965-122">La proprietà <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> supporta la parola chiave `Enlist`, che indica se <xref:System.Data.SqlClient> rileverà i contesti transazionali ed elenca automaticamente la connessione in una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-122">The <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property supports a keyword, `Enlist`, which indicates whether <xref:System.Data.SqlClient> will detect transactional contexts and automatically enlist the connection in a distributed transaction.</span></span> <span data-ttu-id="85965-123">Se `Enlist=true`, la connessione verrà automaticamente elencata nel contesto di transazione corrente del thread di apertura.</span><span class="sxs-lookup"><span data-stu-id="85965-123">If `Enlist=true`, the connection is automatically enlisted in the opening thread's current transaction context.</span></span> <span data-ttu-id="85965-124">Se `Enlist=false`, la connessione `SqlClient` non interagirà con una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-124">If `Enlist=false`, the `SqlClient` connection does not interact with a distributed transaction.</span></span> <span data-ttu-id="85965-125">Il valore predefinito per `Enlist` è true.</span><span class="sxs-lookup"><span data-stu-id="85965-125">The default value for `Enlist` is true.</span></span> <span data-ttu-id="85965-126">Se `Enlist` non è specificato nella stringa di connessione e se viene rilevata una transazione distribuita all'apertura della connessione, quest'ultima verrà automaticamente elencata nella transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-126">If `Enlist` is not specified in the connection string, the connection is automatically enlisted in a distributed transaction if one is detected when the connection is opened.</span></span>  
  
 <span data-ttu-id="85965-127">Le parole chiave `Transaction Binding` di una stringa di connessione <xref:System.Data.SqlClient.SqlConnection> controllano l'associazione della connessione a una transazione `System.Transactions` elencata.</span><span class="sxs-lookup"><span data-stu-id="85965-127">The `Transaction Binding` keywords in a <xref:System.Data.SqlClient.SqlConnection> connection string control the connection's association with an enlisted `System.Transactions` transaction.</span></span> <span data-ttu-id="85965-128">È anche disponibile tramite le proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> e <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="85965-128">It is also available through the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> property of a <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="85965-129">Nella tabella seguente sono descritti i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="85965-129">The following table describes the possible values.</span></span>  
  
|<span data-ttu-id="85965-130">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="85965-130">Keyword</span></span>|<span data-ttu-id="85965-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85965-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85965-132">Implicit Unbind</span><span class="sxs-lookup"><span data-stu-id="85965-132">Implicit Unbind</span></span>|<span data-ttu-id="85965-133">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="85965-133">The default.</span></span> <span data-ttu-id="85965-134">La connessione viene scollegata dalla transazione una volta completata e torna alla modalità di commit automatico.</span><span class="sxs-lookup"><span data-stu-id="85965-134">The connection detaches from the transaction when it ends, switching back to autocommit mode.</span></span>|  
|<span data-ttu-id="85965-135">Explicit Unbind</span><span class="sxs-lookup"><span data-stu-id="85965-135">Explicit Unbind</span></span>|<span data-ttu-id="85965-136">La connessione rimane collegata alla transazione fino alla chiusura di quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="85965-136">The connection remains attached to the transaction until the transaction is closed.</span></span> <span data-ttu-id="85965-137">La connessione non verrà eseguita se la transazione associata non è attiva o non corrisponde a <xref:System.Transactions.Transaction.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="85965-137">The connection will fail if the associated transaction is not active or does not match <xref:System.Transactions.Transaction.Current%2A>.</span></span>|  
  
## <a name="using-transactionscope"></a><span data-ttu-id="85965-138">Uso di TransactionScope</span><span class="sxs-lookup"><span data-stu-id="85965-138">Using TransactionScope</span></span>  
 <span data-ttu-id="85965-139">La classe <xref:System.Transactions.TransactionScope> rende transazionale un blocco di codice attraverso un'integrazione implicita delle connessioni in una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-139">The <xref:System.Transactions.TransactionScope> class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="85965-140">È necessario chiamare il metodo <xref:System.Transactions.TransactionScope.Complete%2A> alla fine del blocco <xref:System.Transactions.TransactionScope> prima di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="85965-140">You must call the <xref:System.Transactions.TransactionScope.Complete%2A> method at the end of the <xref:System.Transactions.TransactionScope> block before leaving it.</span></span> <span data-ttu-id="85965-141">Quando si lascia il blocco viene richiamato il metodo <xref:System.Transactions.TransactionScope.Dispose%2A> .</span><span class="sxs-lookup"><span data-stu-id="85965-141">Leaving the block invokes the <xref:System.Transactions.TransactionScope.Dispose%2A> method.</span></span> <span data-ttu-id="85965-142">Se è stata generata un'eccezione che ha provocato l'uscita del codice dall'ambito, la transazione sarà considerata interrotta.</span><span class="sxs-lookup"><span data-stu-id="85965-142">If an exception has been thrown that causes the code to leave scope, the transaction is considered aborted.</span></span>  
  
 <span data-ttu-id="85965-143">Si consiglia di usare un blocco `using` per assicurare che venga chiamato il metodo <xref:System.Transactions.TransactionScope.Dispose%2A> sull'oggetto <xref:System.Transactions.TransactionScope> quando si esce dal blocco using.</span><span class="sxs-lookup"><span data-stu-id="85965-143">We recommend that you use a `using` block to make sure that <xref:System.Transactions.TransactionScope.Dispose%2A> is called on the <xref:System.Transactions.TransactionScope> object when the using block is exited.</span></span> <span data-ttu-id="85965-144">Se non viene eseguito il commit o il rollback delle transazioni in sospeso, è possibile che le prestazioni vengano notevolmente compromesse, in quanto il timeout predefinito per <xref:System.Transactions.TransactionScope> è di un minuto.</span><span class="sxs-lookup"><span data-stu-id="85965-144">Failure to commit or roll back pending transactions can significantly damage performance because the default time-out for the <xref:System.Transactions.TransactionScope> is one minute.</span></span> <span data-ttu-id="85965-145">Se non si utilizza un'istruzione `using`, è necessario eseguire tutto il lavoro in un blocco `Try` e chiamare in modo esplicito il metodo <xref:System.Transactions.TransactionScope.Dispose%2A> all'interno del blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="85965-145">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the <xref:System.Transactions.TransactionScope.Dispose%2A> method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="85965-146">Se viene generata un'eccezione all'interno di <xref:System.Transactions.TransactionScope>, la transazione viene contrassegnata come incoerente e viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="85965-146">If an exception occurs in the <xref:System.Transactions.TransactionScope>, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="85965-147">Il rollback verrà eseguito quando viene eliminato il tipo <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="85965-147">It will be rolled back when the <xref:System.Transactions.TransactionScope> is disposed.</span></span> <span data-ttu-id="85965-148">Se non si verifica alcuna eccezione, viene eseguito il commit delle transazioni partecipanti.</span><span class="sxs-lookup"><span data-stu-id="85965-148">If no exception occurs, participating transactions commit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85965-149">Per impostazione predefinita, la classe `TransactionScope` crea una transazione con un <xref:System.Transactions.Transaction.IsolationLevel%2A> di `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="85965-149">The `TransactionScope` class creates a transaction with a <xref:System.Transactions.Transaction.IsolationLevel%2A> of `Serializable` by default.</span></span> <span data-ttu-id="85965-150">A seconda dell'applicazione, è possibile abbassare il livello di isolamento per evitare che si verifichi un numero elevato di contese.</span><span class="sxs-lookup"><span data-stu-id="85965-150">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85965-151">Si consiglia di eseguire solo operazioni di aggiornamento, inserimento ed eliminazione all'interno delle transazioni distribuite, poiché comportano un utilizzo notevole delle risorse di database.</span><span class="sxs-lookup"><span data-stu-id="85965-151">We recommend that you perform only updates, inserts, and deletes within distributed transactions because they consume significant database resources.</span></span> <span data-ttu-id="85965-152">Le istruzioni SELECT possono bloccare le risorse di database inutilmente e, in alcuni scenari, può essere necessario usare le transazioni per questo tipo di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="85965-152">Select statements may lock database resources unnecessarily, and in some scenarios, you may have to use transactions for selects.</span></span> <span data-ttu-id="85965-153">È necessario eseguire le operazioni non di database al di fuori dell'ambito della transazione, a meno che non richiedano altri gestori di risorse transazionali.</span><span class="sxs-lookup"><span data-stu-id="85965-153">Any non-database work should be done outside the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="85965-154">Sebbene un'eccezione nell'ambito della transazione impedisca l'esecuzione del commit, la classe <xref:System.Transactions.TransactionScope> non è in grado di eseguire il rollback delle modifiche apportate al codice al di fuori dell'ambito della transazione stessa.</span><span class="sxs-lookup"><span data-stu-id="85965-154">Although an exception in the scope of the transaction prevents the transaction from committing, the <xref:System.Transactions.TransactionScope> class has no provision for rolling back any changes your code has made outside the scope of the transaction itself.</span></span> <span data-ttu-id="85965-155">Per eseguire operazioni durante il rollback della transazione, è necessario scrivere la propria implementazione dell'interfaccia <xref:System.Transactions.IEnlistmentNotification> ed elencarla in modo esplicito nella transazione.</span><span class="sxs-lookup"><span data-stu-id="85965-155">If you have to take some action when the transaction is rolled back, you must write your own implementation of the <xref:System.Transactions.IEnlistmentNotification> interface and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85965-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="85965-156">Example</span></span>  
 <span data-ttu-id="85965-157">Per usare <xref:System.Transactions> , è necessario un riferimento a System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="85965-157">Working with <xref:System.Transactions> requires that you have a reference to System.Transactions.dll.</span></span>  
  
 <span data-ttu-id="85965-158">Nella funzione seguente viene illustrato come creare una transazione promuovibile in due istanze diverse di SQL Server, rappresentate da due oggetti <xref:System.Data.SqlClient.SqlConnection> diversi, incapsulati in un blocco <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="85965-158">The following function demonstrates how to create a promotable transaction against two different SQL Server instances, represented by two different <xref:System.Data.SqlClient.SqlConnection> objects, which are wrapped in a <xref:System.Transactions.TransactionScope> block.</span></span> <span data-ttu-id="85965-159">Il codice consente di creare il blocco <xref:System.Transactions.TransactionScope> con un'istruzione `using` , di aprire la prima connessione e di elencarla automaticamente nel tipo <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="85965-159">The code creates the <xref:System.Transactions.TransactionScope> block with a `using` statement and opens the first connection, which automatically enlists it in the <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="85965-160">La transazione viene integrata inizialmente come transazione lightweight, non come transazione completamente distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-160">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="85965-161">La seconda connessione viene inserita in <xref:System.Transactions.TransactionScope> solo se il comando della prima connessione non genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="85965-161">The second connection is enlisted in the <xref:System.Transactions.TransactionScope> only if the command in the first connection does not throw an exception.</span></span> <span data-ttu-id="85965-162">Quando viene aperta la seconda connessione, la transazione viene automaticamente promossa diventando una piena transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="85965-162">When the second connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="85965-163">Viene richiamato il metodo <xref:System.Transactions.TransactionScope.Complete%2A> che esegue il commit della transazione solo se non sono state generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="85965-163">The <xref:System.Transactions.TransactionScope.Complete%2A> method is invoked, which commits the transaction only if no exceptions have been thrown.</span></span> <span data-ttu-id="85965-164">Se è stata generata un'eccezione in qualsiasi punto del blocco <xref:System.Transactions.TransactionScope> , il metodo `Complete` non verrà chiamato e verrà eseguito il rollback della transazione distribuita quando <xref:System.Transactions.TransactionScope> viene eliminato al termine del relativo blocco `using` .</span><span class="sxs-lookup"><span data-stu-id="85965-164">If an exception has been thrown at any point in the <xref:System.Transactions.TransactionScope> block, `Complete` will not be called, and the distributed transaction will roll back when the <xref:System.Transactions.TransactionScope> is disposed at the end of its `using` block.</span></span>  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="85965-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85965-165">See also</span></span>

- [<span data-ttu-id="85965-166">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="85965-166">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="85965-167">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="85965-167">ADO.NET Overview</span></span>](ado-net-overview.md)
