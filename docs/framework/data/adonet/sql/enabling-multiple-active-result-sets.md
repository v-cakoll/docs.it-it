---
title: Abilitazione di MARS (Multiple Active Result Set)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b2b1e3ccfe162b6d4903aaf162673ba476296d8b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="enabling-multiple-active-result-sets"></a><span data-ttu-id="d9ac4-102">Abilitazione di MARS (Multiple Active Result Set)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-102">Enabling Multiple Active Result Sets</span></span>
<span data-ttu-id="d9ac4-103">MARS (Multiple Active Result Set) è un servizio che funziona in combinazione con SQL Server per consentire l'esecuzione di più batch in un'unica connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-103">Multiple Active Result Sets (MARS) is a feature that works with SQL Server to allow the execution of multiple batches on a single connection.</span></span> <span data-ttu-id="d9ac4-104">Quando MARS è abilitato per l'uso con SQL Server, ciascun oggetto comando usato aggiunge una sessione alla connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-104">When MARS is enabled for use with SQL Server, each command object used adds a session to the connection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9ac4-105">Una singola sessione MARS apre un'unica connessione logica per MARS e quindi un'unica connessione logica per ogni comando attivo.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-105">A single MARS session opens one logical connection for MARS to use and then one logical connection for each active command.</span></span>  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a><span data-ttu-id="d9ac4-106">Abilitazione e disabilitazione di MARS nella stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="d9ac4-106">Enabling and Disabling MARS in the Connection String</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9ac4-107">L'esempio di utilizzare le seguenti stringhe di connessione **AdventureWorks** database incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-107">The following connection strings use the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="d9ac4-108">e presuppongono che il database sia installato in un server denominato MSSQL1.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-108">The connection strings provided assume that the database is installed on a server named MSSQL1.</span></span> <span data-ttu-id="d9ac4-109">Modificare la stringa di connessione per adattarla all'ambiente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-109">Modify the connection string as necessary for your environment.</span></span>  
  
 <span data-ttu-id="d9ac4-110">Per impostazione predefinita la funzionalità MARS è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-110">The MARS feature is disabled by default.</span></span> <span data-ttu-id="d9ac4-111">Può essere abilitata aggiungendo la coppia di parole chiave "MultipleActiveResultSets=True" alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-111">It can be enabled by adding the "MultipleActiveResultSets=True" keyword pair to your connection string.</span></span> <span data-ttu-id="d9ac4-112">"True" è l'unico valore valido per l'attivazione di MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-112">"True" is the only valid value for enabling MARS.</span></span> <span data-ttu-id="d9ac4-113">Nell'esempio seguente viene mostrato come eseguire la connessione a un'istanza di SQL Server e come specificare l'abilitazione di MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-113">The following example demonstrates how to connect to an instance of SQL Server and how to specify that MARS should be enabled.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 <span data-ttu-id="d9ac4-114">È possibile disabilitare MARS aggiungendo la coppia di parole chiave "MultipleActiveResultSets=False" alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-114">You can disable MARS by adding the "MultipleActiveResultSets=False" keyword pair to your connection string.</span></span> <span data-ttu-id="d9ac4-115">"False" è l'unico valore valido per la disattivazione di MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-115">"False" is the only valid value for disabling MARS.</span></span> <span data-ttu-id="d9ac4-116">Nella stringa di connessione seguente viene mostrato come disabilitare MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-116">The following connection string demonstrates how to disable MARS.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a><span data-ttu-id="d9ac4-117">Considerazioni specifiche sull'utilizzo di MARS</span><span class="sxs-lookup"><span data-stu-id="d9ac4-117">Special Considerations When Using MARS</span></span>  
 <span data-ttu-id="d9ac4-118">In generale, le applicazioni esistenti non necessitano di alcuna modifica per usare una connessione con MARS abilitato.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-118">In general, existing applications should not need modification to use a MARS-enabled connection.</span></span> <span data-ttu-id="d9ac4-119">Tuttavia, se si desidera usare le funzionalità di MARS in determinate applicazioni, è necessario comprendere le considerazioni specifiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-119">However, if you wish to use MARS features in your applications, you should understand the following special considerations.</span></span>  
  
### <a name="statement-interleaving"></a><span data-ttu-id="d9ac4-120">Interfoliazione delle istruzioni</span><span class="sxs-lookup"><span data-stu-id="d9ac4-120">Statement Interleaving</span></span>  
 <span data-ttu-id="d9ac4-121">Le operazioni MARS vengono eseguite sul server in modalità sincrona.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-121">MARS operations execute synchronously on the server.</span></span> <span data-ttu-id="d9ac4-122">L'interfoliazione delle istruzioni SELECT e BULK INSERT è consentita.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-122">Statement interleaving of SELECT and BULK INSERT statements is allowed.</span></span> <span data-ttu-id="d9ac4-123">Tuttavia, le istruzioni DML (Data Manipulation Language) e DDL (Data Definition Language) vengono eseguite atomicamente.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-123">However, data manipulation language (DML) and data definition language (DDL) statements execute atomically.</span></span> <span data-ttu-id="d9ac4-124">Eventuali istruzioni eseguite durante l'esecuzione di un batch atomico vengono bloccate.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-124">Any statements attempting to execute while an atomic batch is executing are blocked.</span></span> <span data-ttu-id="d9ac4-125">L'esecuzione parallela sul server non è una funzionalità MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-125">Parallel execution at the server is not a MARS feature.</span></span>  
  
 <span data-ttu-id="d9ac4-126">Se i due batch vengono inviati in una connessione MARS, uno con un'istruzione SELECT e l'altro con un'istruzione DML, l'esecuzione dell'istruzione DML può iniziare contemporaneamente all'esecuzione dell'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-126">If two batches are submitted under a MARS connection, one of them containing a SELECT statement, the other containing a DML statement, the DML can begin execution within execution of the SELECT statement.</span></span> <span data-ttu-id="d9ac4-127">Tuttavia, l'istruzione DML deve essere eseguita completamente prima che venga eseguita l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-127">However, the DML statement must run to completion before the SELECT statement can make progress.</span></span> <span data-ttu-id="d9ac4-128">Se entrambe le istruzioni sono in esecuzione nella stessa transazione, eventuali modifiche apportate da un'istruzione DML dopo che è stata avviata l'esecuzione dell'istruzione SELECT non risultano visibili per l'operazione di lettura.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-128">If both statements are running under the same transaction, any changes made by a DML statement after the SELECT statement has started execution are not visible to the read operation.</span></span>  
  
 <span data-ttu-id="d9ac4-129">Un'istruzione WAITFOR all'interno di un'istruzione SELECT non restituisce la transazione in fase di attesa, ovvero, finché non viene generata la prima riga.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-129">A WAITFOR statement inside a SELECT statement does not yield the transaction while it is waiting, that is, until the first row is produced.</span></span> <span data-ttu-id="d9ac4-130">Ciò implica che durante l'attesa di un'istruzione WAITFOR non possono essere eseguiti altri batch all'interno della connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-130">This implies that no other batches can execute within the same connection while a WAITFOR statement is waiting.</span></span>  
  
### <a name="mars-session-cache"></a><span data-ttu-id="d9ac4-131">Cache della sessione MARS</span><span class="sxs-lookup"><span data-stu-id="d9ac4-131">MARS Session Cache</span></span>  
 <span data-ttu-id="d9ac4-132">Quando viene aperta una connessione con MARS abilitato, viene creata una sessione logica, che consente di aggiungere overhead.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-132">When a connection is opened with MARS enabled, a logical session is created, which adds additional overhead.</span></span> <span data-ttu-id="d9ac4-133">Per ridurre l'overhead e migliorare le prestazioni, **SqlClient** memorizza nella cache la sessione MARS all'interno di una connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-133">To minimize overhead and enhance performance, **SqlClient** caches the MARS session within a connection.</span></span> <span data-ttu-id="d9ac4-134">La cache può contenere fino a 10 sessioni MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-134">The cache contains at most 10 MARS sessions.</span></span> <span data-ttu-id="d9ac4-135">Questo valore non può essere regolato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-135">This value is not user adjustable.</span></span> <span data-ttu-id="d9ac4-136">Se viene raggiunto il limite, viene creata una nuova sessione senza che vengano generati errori.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-136">If the session limit is reached, a new session is created—an error is not generated.</span></span> <span data-ttu-id="d9ac4-137">La cache e le sessioni in essa contenute sono per connessione e non sono condivise tra le connessioni.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-137">The cache and sessions contained in it are per-connection; they are not shared across connections.</span></span> <span data-ttu-id="d9ac4-138">Quando viene rilasciata, la sessione viene restituita al pool a meno che non sia stato raggiunto il limite superiore del pool.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-138">When a session is released, it is returned to the pool unless the pool's upper limit has been reached.</span></span> <span data-ttu-id="d9ac4-139">Se il pool della cache è pieno, la sessione è chiusa.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-139">If the cache pool is full, the session is closed.</span></span> <span data-ttu-id="d9ac4-140">Le sessioni MARS non scadono,</span><span class="sxs-lookup"><span data-stu-id="d9ac4-140">MARS sessions do not expire.</span></span> <span data-ttu-id="d9ac4-141">ma vengono eliminate quando l'oggetto connessione viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-141">They are only cleaned up when the connection object is disposed.</span></span> <span data-ttu-id="d9ac4-142">La cache della sessione MARS non è precaricata,</span><span class="sxs-lookup"><span data-stu-id="d9ac4-142">The MARS session cache is not preloaded.</span></span> <span data-ttu-id="d9ac4-143">ma viene caricata quando vengono richieste più sessioni dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-143">It is loaded as the application requires more sessions.</span></span>  
  
### <a name="thread-safety"></a><span data-ttu-id="d9ac4-144">Thread safety</span><span class="sxs-lookup"><span data-stu-id="d9ac4-144">Thread Safety</span></span>  
 <span data-ttu-id="d9ac4-145">Le operazioni MARS non sono thread-safe.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-145">MARS operations are not thread-safe.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="d9ac4-146">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="d9ac4-146">Connection Pooling</span></span>  
 <span data-ttu-id="d9ac4-147">Le connessioni con MARS abilitato sono in pool come qualsiasi altra connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-147">MARS-enabled connections are pooled like any other connection.</span></span> <span data-ttu-id="d9ac4-148">Se un'applicazione apre due connessioni, una con MARS abilitato e un'altra con MARS disabilitato, le due connessioni risulteranno in pool diversi.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-148">If an application opens two connections, one with MARS enabled and one with MARS disabled, the two connections are in separate pools.</span></span> <span data-ttu-id="d9ac4-149">Per ulteriori informazioni, vedere [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="d9ac4-149">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
### <a name="sql-server-batch-execution-environment"></a><span data-ttu-id="d9ac4-150">Ambiente di esecuzione in batch di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d9ac4-150">SQL Server Batch Execution Environment</span></span>  
 <span data-ttu-id="d9ac4-151">Quando si apre una connessione, viene definito un ambiente predefinito</span><span class="sxs-lookup"><span data-stu-id="d9ac4-151">When a connection is opened, a default environment is defined.</span></span> <span data-ttu-id="d9ac4-152">che viene quindi copiato in una sessione MARS logica.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-152">This environment is then copied into a logical MARS session.</span></span>  
  
 <span data-ttu-id="d9ac4-153">L'ambiente di esecuzione in batch include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9ac4-153">The batch execution environment includes the following components:</span></span>  
  
-   <span data-ttu-id="d9ac4-154">Opzioni di impostazione (ad esempio, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-154">Set options (for example, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span></span>  
  
-   <span data-ttu-id="d9ac4-155">Contesto di sicurezza (ruolo utente/applicazione)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-155">Security context (user/application role)</span></span>  
  
-   <span data-ttu-id="d9ac4-156">Contesto database (database corrente)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-156">Database context (current database)</span></span>  
  
-   <span data-ttu-id="d9ac4-157">Le variabili di stato di esecuzione (ad esempio, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-157">Execution state variables (for example, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span></span>  
  
-   <span data-ttu-id="d9ac4-158">Tabelle temporanee principali</span><span class="sxs-lookup"><span data-stu-id="d9ac4-158">Top-level temporary tables</span></span>  
  
 <span data-ttu-id="d9ac4-159">Con MARS, un ambiente di esecuzione predefinito viene associato a una connessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-159">With MARS, a default execution environment is associated to a connection.</span></span> <span data-ttu-id="d9ac4-160">Ogni nuovo batch che viene eseguito in una determinata connessione riceve una copia dell'ambiente predefinito.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-160">Every new batch that starts executing under a given connection receives a copy of the default environment.</span></span> <span data-ttu-id="d9ac4-161">Quando il codice viene eseguito in un determinato batch, tutte le modifiche apportate all'ambiente sono limitate al batch specifico.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-161">Whenever code is executed under a given batch, all changes made to the environment are scoped to the specific batch.</span></span> <span data-ttu-id="d9ac4-162">Al termine dell'esecuzione, le impostazioni di esecuzione vengono copiate nell'ambiente predefinito.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-162">Once execution finishes, the execution settings are copied into the default environment.</span></span> <span data-ttu-id="d9ac4-163">Nel caso di un singolo batch in cui vengono generati diversi comandi da eseguire in ordine sequenziale nella stessa transazione, la semantica è identica a quella esposta dalle connessioni che implicano client e server con versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-163">In the case of a single batch issuing several commands to be executed sequentially under the same transaction, semantics are the same as those exposed by connections involving earlier clients or servers.</span></span>  
  
### <a name="parallel-execution"></a><span data-ttu-id="d9ac4-164">Esecuzione parallela</span><span class="sxs-lookup"><span data-stu-id="d9ac4-164">Parallel Execution</span></span>  
 <span data-ttu-id="d9ac4-165">Il servizio MARS non è progettato per eliminare tutte le esigenze relative a più connessioni in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-165">MARS is not designed to remove all requirements for multiple connections in an application.</span></span> <span data-ttu-id="d9ac4-166">Se per un'applicazione è necessaria l'esecuzione parallela effettiva di comandi su un server, è necessario usare più connessioni.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-166">If an application needs true parallel execution of commands against a server, multiple connections should be used.</span></span>  
  
 <span data-ttu-id="d9ac4-167">Ad esempio, si consideri il seguente scenario.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-167">For example, consider the following scenario.</span></span> <span data-ttu-id="d9ac4-168">Vengono creati due oggetti comando, uno per l'elaborazione di un set di risultati e un altro per l'aggiornamento dei dati. Entrambi gli oggetti condividono una connessione comune tramite MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-168">Two command objects are created, one for processing a result set and another for updating data; they share a common connection via MARS.</span></span> <span data-ttu-id="d9ac4-169">In questo scenario, il `Transaction`.`Commit`</span><span class="sxs-lookup"><span data-stu-id="d9ac4-169">In this scenario, the `Transaction`.`Commit`</span></span> <span data-ttu-id="d9ac4-170">ha esito negativo dell'aggiornamento fino a quando non sono stati letti tutti i risultati sul primo oggetto comando, restituendo l'eccezione seguente:</span><span class="sxs-lookup"><span data-stu-id="d9ac4-170">fails on the update until all the results have been read on the first command object, yielding the following exception:</span></span>  
  
 <span data-ttu-id="d9ac4-171">Messaggio: Il contesto della transazione è in uso in un'altra sessione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-171">Message: Transaction context in use by another session.</span></span>  
  
 <span data-ttu-id="d9ac4-172">Fonte: "Provider di dati .Net SqlClient"</span><span class="sxs-lookup"><span data-stu-id="d9ac4-172">Source: .Net SqlClient Data Provider</span></span>  
  
 <span data-ttu-id="d9ac4-173">Previsto: (null)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-173">Expected: (null)</span></span>  
  
 <span data-ttu-id="d9ac4-174">Ricevuto: System.Data.SqlClient.SqlException</span><span class="sxs-lookup"><span data-stu-id="d9ac4-174">Received: System.Data.SqlClient.SqlException</span></span>  
  
 <span data-ttu-id="d9ac4-175">Sono disponibili tre opzioni per la gestione di questo scenario:</span><span class="sxs-lookup"><span data-stu-id="d9ac4-175">There are three options for handling this scenario:</span></span>  
  
1.  <span data-ttu-id="d9ac4-176">Avviare la transazione dopo aver creato il lettore, affinché non sia parte della transazione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-176">Start the transaction after the reader is created, so that it is not part of the transaction.</span></span> <span data-ttu-id="d9ac4-177">Ogni aggiornamento diventa quindi la propria transazione.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-177">Every update then becomes its own transaction.</span></span>  
  
2.  <span data-ttu-id="d9ac4-178">Eseguire il commit di tutto il lavoro dopo aver chiuso il lettore.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-178">Commit all work after the reader is closed.</span></span> <span data-ttu-id="d9ac4-179">Questa operazione ha il potenziale per un batch sostanziale di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-179">This has the potential for a substantial batch of updates.</span></span>  
  
3.  <span data-ttu-id="d9ac4-180">Non usare MARS, ma una connessione diversa per ciascun oggetto comando come se non si disponesse di MARS.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-180">Don't use MARS; instead use a separate connection for each command object as you would have before MARS.</span></span>  
  
### <a name="detecting-mars-support"></a><span data-ttu-id="d9ac4-181">Rilevamento del supporto di MARS</span><span class="sxs-lookup"><span data-stu-id="d9ac4-181">Detecting MARS Support</span></span>  
 <span data-ttu-id="d9ac4-182">L'applicazione può verificare il supporto di MARS mediante la lettura del valore `SqlConnection.ServerVersion`.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-182">An application can check for MARS support by reading the `SqlConnection.ServerVersion` value.</span></span> <span data-ttu-id="d9ac4-183">Il valore massimo deve essere 9 per SQL Server 2005 e 10 per SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d9ac4-183">The major number should be 9 for SQL Server 2005 and 10 for SQL Server 2008.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ac4-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9ac4-184">See Also</span></span>  
 [<span data-ttu-id="d9ac4-185">MARS (Multiple Active Result Set)</span><span class="sxs-lookup"><span data-stu-id="d9ac4-185">Multiple Active Result Sets (MARS)</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [<span data-ttu-id="d9ac4-186">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d9ac4-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
