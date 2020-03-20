---
title: Concorrenza ottimistica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: e8d24a3998ca97fdf45e647bc40c1f7d6018ec20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149453"
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="0f487-102">Concorrenza ottimistica</span><span class="sxs-lookup"><span data-stu-id="0f487-102">Optimistic Concurrency</span></span>
<span data-ttu-id="0f487-103">In un ambiente con più utenti sono disponibili due modelli per l'aggiornamento di dati in un database: la concorrenza ottimistica e la concorrenza pessimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-103">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="0f487-104">L'oggetto <xref:System.Data.DataSet> è stato progettato per favorire l'uso della concorrenza ottimistica per attività di lunga durata, quali la gestione in remoto dei dati e l'interazione con i dati.</span><span class="sxs-lookup"><span data-stu-id="0f487-104">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="0f487-105">La concorrenza pessimistica implica il blocco di righe nell'origine dati per impedire agli altri utenti di apportare modifiche ai dati che possano influire sugli utenti correnti.</span><span class="sxs-lookup"><span data-stu-id="0f487-105">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="0f487-106">In un modello pessimistico, quando un utente esegue un'azione che provoca l'applicazione di un blocco, agli altri utenti non sarà consentito eseguire azioni che possano entrare in conflitto con tale blocco, fino a quando tale blocco non verrà rilasciato dal relativo proprietario.</span><span class="sxs-lookup"><span data-stu-id="0f487-106">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="0f487-107">Questo tipo di modello viene usato principalmente in ambienti in cui il conflitto per l'uso di dati è elevato e il dispendio di memoria dovuto alla protezione di dati tramite blocchi è inferiore al dispendio relativo all'annullamento di transazioni in caso di conflitti di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="0f487-107">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="0f487-108">Pertanto, in un modello di concorrenza pessimistica, un blocco viene stabilito da un utente che aggiorna una riga.</span><span class="sxs-lookup"><span data-stu-id="0f487-108">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="0f487-109">Fino a che tale utente non completa l'aggiornamento e non rilascia il blocco, nessun altro utente sarà in grado di modificare tale riga.</span><span class="sxs-lookup"><span data-stu-id="0f487-109">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="0f487-110">La concorrenza pessimistica è quindi consigliabile in caso di durate limitate dei blocchi, ad esempio nell'elaborazione a livello di programmazione dei record,</span><span class="sxs-lookup"><span data-stu-id="0f487-110">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="0f487-111">ma non è un'opzione scalabile nel caso in cui gli utenti interagiscano con i dati e provochino il blocco dei record per periodi di tempo relativamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="0f487-111">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f487-112">Se è necessario aggiornare più righe nella stessa operazione, la creazione di una transazione garantisce una maggior scalabilità rispetto al blocco associato alla concorrenza pessimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-112">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="0f487-113">Al contrario, gli utenti che usano la concorrenza ottimistica sono in grado di leggere una riga senza bloccarla.</span><span class="sxs-lookup"><span data-stu-id="0f487-113">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="0f487-114">Quando un utente desidera aggiornare una riga, è necessario che l'applicazione stabilisca se tale riga è stata modificata da un altro utente successivamente alla lettura.</span><span class="sxs-lookup"><span data-stu-id="0f487-114">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="0f487-115">La concorrenza ottimistica viene solitamente usata in ambienti in cui il conflitto per l'uso dei dati non è elevato.</span><span class="sxs-lookup"><span data-stu-id="0f487-115">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="0f487-116">Questo tipo di concorrenza consente un miglioramento delle prestazioni, poiché non è richiesto alcun blocco dei record, operazione che richiede risorse di server aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0f487-116">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="0f487-117">Per mantenere i blocchi dei record, inoltre, è necessaria una connessione permanente al server database.</span><span class="sxs-lookup"><span data-stu-id="0f487-117">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="0f487-118">Poiché tali blocchi non sono necessari se si usa un modello di concorrenza ottimistica, le connessioni al server sono in grado di soddisfare un numero superiore di client in un intervallo di tempo minore.</span><span class="sxs-lookup"><span data-stu-id="0f487-118">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="0f487-119">In un modello di concorrenza ottimistica si verifica una violazione nel caso in cui, dopo che un utente riceve un valore dal database, tale valore viene modificato da un altro utente prima che il primo utente abbia effettuato un tentativo di modifica.</span><span class="sxs-lookup"><span data-stu-id="0f487-119">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="0f487-120">L'esempio seguente consente di illustrare in modo migliore come viene risolta una violazione di concorrenza da parte del server.</span><span class="sxs-lookup"><span data-stu-id="0f487-120">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="0f487-121">Nella tabella seguente viene mostrato un esempio di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-121">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="0f487-122">Alle ore 13.00 l'Utente1 legge una riga dal database contenente i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="0f487-122">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="0f487-123">**CustID     LastName     FirstName**</span><span class="sxs-lookup"><span data-stu-id="0f487-123">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="0f487-124">101          Dalzi             Maria</span><span class="sxs-lookup"><span data-stu-id="0f487-124">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="0f487-125">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0f487-125">Column name</span></span>|<span data-ttu-id="0f487-126">Valore originale</span><span class="sxs-lookup"><span data-stu-id="0f487-126">Original value</span></span>|<span data-ttu-id="0f487-127">Valore corrente</span><span class="sxs-lookup"><span data-stu-id="0f487-127">Current value</span></span>|<span data-ttu-id="0f487-128">Valore nel database</span><span class="sxs-lookup"><span data-stu-id="0f487-128">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="0f487-129">CustID</span><span class="sxs-lookup"><span data-stu-id="0f487-129">CustID</span></span>|<span data-ttu-id="0f487-130">101</span><span class="sxs-lookup"><span data-stu-id="0f487-130">101</span></span>|<span data-ttu-id="0f487-131">101</span><span class="sxs-lookup"><span data-stu-id="0f487-131">101</span></span>|<span data-ttu-id="0f487-132">101</span><span class="sxs-lookup"><span data-stu-id="0f487-132">101</span></span>|  
|<span data-ttu-id="0f487-133">LastName</span><span class="sxs-lookup"><span data-stu-id="0f487-133">LastName</span></span>|<span data-ttu-id="0f487-134">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-134">Smith</span></span>|<span data-ttu-id="0f487-135">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-135">Smith</span></span>|<span data-ttu-id="0f487-136">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-136">Smith</span></span>|  
|<span data-ttu-id="0f487-137">FirstName</span><span class="sxs-lookup"><span data-stu-id="0f487-137">FirstName</span></span>|<span data-ttu-id="0f487-138">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-138">Bob</span></span>|<span data-ttu-id="0f487-139">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-139">Bob</span></span>|<span data-ttu-id="0f487-140">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-140">Bob</span></span>|  
  
 <span data-ttu-id="0f487-141">Alle ore 13.01 l'Utente2 legge la stessa colonna.</span><span class="sxs-lookup"><span data-stu-id="0f487-141">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="0f487-142">Alle 13:03, User2 modifica **FirstName** da "Bob" a "Robert" e aggiorna il database.</span><span class="sxs-lookup"><span data-stu-id="0f487-142">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="0f487-143">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0f487-143">Column name</span></span>|<span data-ttu-id="0f487-144">Valore originale</span><span class="sxs-lookup"><span data-stu-id="0f487-144">Original value</span></span>|<span data-ttu-id="0f487-145">Valore corrente</span><span class="sxs-lookup"><span data-stu-id="0f487-145">Current value</span></span>|<span data-ttu-id="0f487-146">Valore nel database</span><span class="sxs-lookup"><span data-stu-id="0f487-146">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="0f487-147">CustID</span><span class="sxs-lookup"><span data-stu-id="0f487-147">CustID</span></span>|<span data-ttu-id="0f487-148">101</span><span class="sxs-lookup"><span data-stu-id="0f487-148">101</span></span>|<span data-ttu-id="0f487-149">101</span><span class="sxs-lookup"><span data-stu-id="0f487-149">101</span></span>|<span data-ttu-id="0f487-150">101</span><span class="sxs-lookup"><span data-stu-id="0f487-150">101</span></span>|  
|<span data-ttu-id="0f487-151">LastName</span><span class="sxs-lookup"><span data-stu-id="0f487-151">LastName</span></span>|<span data-ttu-id="0f487-152">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-152">Smith</span></span>|<span data-ttu-id="0f487-153">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-153">Smith</span></span>|<span data-ttu-id="0f487-154">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-154">Smith</span></span>|  
|<span data-ttu-id="0f487-155">FirstName</span><span class="sxs-lookup"><span data-stu-id="0f487-155">FirstName</span></span>|<span data-ttu-id="0f487-156">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-156">Bob</span></span>|<span data-ttu-id="0f487-157">Maria Teresa</span><span class="sxs-lookup"><span data-stu-id="0f487-157">Robert</span></span>|<span data-ttu-id="0f487-158">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-158">Bob</span></span>|  
  
 <span data-ttu-id="0f487-159">L'aggiornamento viene effettuato correttamente, poiché i valori presenti nel database al momento dell'aggiornamento corrispondono ai valori originali a disposizione dell'Utente2.</span><span class="sxs-lookup"><span data-stu-id="0f487-159">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="0f487-160">Alle ore 13.05 l'Utente1 cambia il nome di "Maria" in "Teresa" e cerca di aggiornare la riga.</span><span class="sxs-lookup"><span data-stu-id="0f487-160">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="0f487-161">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0f487-161">Column name</span></span>|<span data-ttu-id="0f487-162">Valore originale</span><span class="sxs-lookup"><span data-stu-id="0f487-162">Original value</span></span>|<span data-ttu-id="0f487-163">Valore corrente</span><span class="sxs-lookup"><span data-stu-id="0f487-163">Current value</span></span>|<span data-ttu-id="0f487-164">Valore nel database</span><span class="sxs-lookup"><span data-stu-id="0f487-164">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="0f487-165">CustID</span><span class="sxs-lookup"><span data-stu-id="0f487-165">CustID</span></span>|<span data-ttu-id="0f487-166">101</span><span class="sxs-lookup"><span data-stu-id="0f487-166">101</span></span>|<span data-ttu-id="0f487-167">101</span><span class="sxs-lookup"><span data-stu-id="0f487-167">101</span></span>|<span data-ttu-id="0f487-168">101</span><span class="sxs-lookup"><span data-stu-id="0f487-168">101</span></span>|  
|<span data-ttu-id="0f487-169">LastName</span><span class="sxs-lookup"><span data-stu-id="0f487-169">LastName</span></span>|<span data-ttu-id="0f487-170">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-170">Smith</span></span>|<span data-ttu-id="0f487-171">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-171">Smith</span></span>|<span data-ttu-id="0f487-172">Smith</span><span class="sxs-lookup"><span data-stu-id="0f487-172">Smith</span></span>|  
|<span data-ttu-id="0f487-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="0f487-173">FirstName</span></span>|<span data-ttu-id="0f487-174">Bob</span><span class="sxs-lookup"><span data-stu-id="0f487-174">Bob</span></span>|<span data-ttu-id="0f487-175">Teresa</span><span class="sxs-lookup"><span data-stu-id="0f487-175">James</span></span>|<span data-ttu-id="0f487-176">Maria Teresa</span><span class="sxs-lookup"><span data-stu-id="0f487-176">Robert</span></span>|  
  
 <span data-ttu-id="0f487-177">A questo punto l'Utente1 rileva una violazione della concorrenza ottimistica, poiché i valori del database ("Maria Teresa") non corrispondono più ai valori originali previsti dall'Utente1 ("Maria").</span><span class="sxs-lookup"><span data-stu-id="0f487-177">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="0f487-178">La violazione della concorrenza consente di essere informati del mancato aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0f487-178">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="0f487-179">È quindi necessario decidere se sovrascrivere le modifiche apportate dall'Utente2 con le modifiche apportate dall'Utente1 o annullare le modifiche dell'Utente1.</span><span class="sxs-lookup"><span data-stu-id="0f487-179">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="0f487-180">Verifica di violazioni alla concorrenza ottimistica</span><span class="sxs-lookup"><span data-stu-id="0f487-180">Testing for Optimistic Concurrency Violations</span></span>  
 <span data-ttu-id="0f487-181">Per verificare eventuali violazioni alla concorrenza ottimistica, sono disponibili diverse tecniche.</span><span class="sxs-lookup"><span data-stu-id="0f487-181">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="0f487-182">Una di queste prevede l'inclusione di una colonna timestamp nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0f487-182">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="0f487-183">In genere, la funzionalità timestamp, che consente di identificare la data e l'ora dell'ultimo aggiornamento apportato al record, viene fornita dai database.</span><span class="sxs-lookup"><span data-stu-id="0f487-183">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="0f487-184">Se si usa questa tecnica, una colonna timestamp viene inclusa nella definizione della tabella.</span><span class="sxs-lookup"><span data-stu-id="0f487-184">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="0f487-185">Il timestamp viene aggiornato a ogni aggiornamento del record, in modo da riflettere la data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="0f487-185">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="0f487-186">Quando si esegue una verifica di eventuali violazioni alla concorrenza ottimistica, la colonna timestamp viene restituita con una query relativa ai contenuti della tabella.</span><span class="sxs-lookup"><span data-stu-id="0f487-186">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="0f487-187">A ogni tentativo di aggiornamento, il valore timestamp del database viene confrontato con il valore timestamp originale contenuto nella riga modificata.</span><span class="sxs-lookup"><span data-stu-id="0f487-187">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="0f487-188">Se tali valori corrispondono, l'aggiornamento viene eseguito e la colonna timestamp viene aggiornata con l'ora corrente, in modo da riflettere l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0f487-188">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="0f487-189">Se i valori non corrispondono, si è verificata una violazione della concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-189">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="0f487-190">Un'altra tecnica per rilevare eventuali violazioni alla concorrenza ottimistica consiste nel verificare che tutti i valori di colonna originali corrispondano ancora ai valori presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="0f487-190">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="0f487-191">Si consideri ad esempio la query seguente:</span><span class="sxs-lookup"><span data-stu-id="0f487-191">For example, consider the following query:</span></span>  
  
```sql
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="0f487-192">Per verificare la verificare la disponibilità di una violazione della concorrenza ottimistica durante l'aggiornamento di una riga in **Table1**, è necessario eseguire la seguente istruzione UPDATE:</span><span class="sxs-lookup"><span data-stu-id="0f487-192">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="0f487-193">Se i valori originali corrispondono ai valori del database, sarà possibile effettuare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0f487-193">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="0f487-194">Se un valore è stato modificato, la riga non verrà modificata dall'aggiornamento, poiché la clausola WHERE non sarà in grado di trovare alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="0f487-194">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="0f487-195">Notare che è sempre consigliabile restituire un valore univoco di chiave primaria nella query.</span><span class="sxs-lookup"><span data-stu-id="0f487-195">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="0f487-196">In caso contrario, è possibile che la precedente istruzione UPDATE provochi l'aggiornamento non desiderato di più righe.</span><span class="sxs-lookup"><span data-stu-id="0f487-196">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="0f487-197">Se in una colonna dell'origine dati sono consentiti valori null, è necessario estendere la clausola WHERE, in modo che ricerchi un riferimento null corrispondente nella tabella locale e nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0f487-197">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="0f487-198">La seguente istruzione UPDATE, ad esempio, consente di verificare la corrispondenza tra un riferimento null nella riga locale e un riferimento null nell'origine dati o la corrispondenza tra un valore nella riga locale e il valore nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0f487-198">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="0f487-199">Quando si usa il modello di concorrenza ottimistica, è possibile applicare anche criteri meno restrittivi.</span><span class="sxs-lookup"><span data-stu-id="0f487-199">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="0f487-200">Ad esempio, se si usano solo le colonne di chiave primaria nella clausola WHERE, i dati verranno sovrascritti, indipendentemente dagli eventuali aggiornamenti apportati alle altre colonne successivamente all'ultima query.</span><span class="sxs-lookup"><span data-stu-id="0f487-200">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="0f487-201">È inoltre possibile applicare una clausola WHERE solo a colonne specifiche, in modo che i dati vengano sovrascritti a meno che particolari campi non siano stati aggiornati successivamente all'ultima query.</span><span class="sxs-lookup"><span data-stu-id="0f487-201">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="0f487-202">Evento DataAdapter.RowUpdated</span><span class="sxs-lookup"><span data-stu-id="0f487-202">The DataAdapter.RowUpdated Event</span></span>  
 <span data-ttu-id="0f487-203">Il **RowUpdated** evento <xref:System.Data.Common.DataAdapter> dell'oggetto può essere utilizzato in combinazione con le tecniche descritte in precedenza, per fornire notifica all'applicazione di violazioni della concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-203">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="0f487-204">**RowUpdated** si verifica dopo ogni tentativo di aggiornare una riga **modificata** da un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0f487-204">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="0f487-205">È quindi possibile aggiungere un particolare codice di gestione, che includa l'elaborazione nel caso in cui si verifichi un'eccezione, l'aggiunta di informazioni personalizzate relative agli errori, l'aggiunta di logica relativa ai nuovi tentativi e così via.</span><span class="sxs-lookup"><span data-stu-id="0f487-205">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="0f487-206">L'oggetto <xref:System.Data.Common.RowUpdatedEventArgs> restituisce una proprietà **RecordsAffected** contenente il numero di righe interessate da un particolare comando di aggiornamento per una riga modificata in una tabella.</span><span class="sxs-lookup"><span data-stu-id="0f487-206">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="0f487-207">Impostando il comando update per verificare la concorrenza ottimistica, la proprietà **RecordsAffected** restituirà, di conseguenza, un valore pari a 0 quando si è verificata una violazione della concorrenza ottimistica, poiché non è stato aggiornato alcun record.</span><span class="sxs-lookup"><span data-stu-id="0f487-207">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="0f487-208">In questo caso viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0f487-208">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="0f487-209">L'evento **RowUpdated** consente di gestire questa occorrenza ed evitare l'eccezione impostando un valore **RowUpdatedEventArgs.Status** appropriato, ad esempio **UpdateStatus.SkipCurrentRow**.</span><span class="sxs-lookup"><span data-stu-id="0f487-209">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="0f487-210">Per ulteriori informazioni sull'evento **RowUpdated** , vedere [Gestione degli eventi DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="0f487-210">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="0f487-211">Facoltativamente, è possibile impostare **DataAdapter.ContinueUpdateOnError** su **true**prima di chiamare **Update**e rispondere alle informazioni sull'errore archiviate nella proprietà **RowError** di una determinata riga al completamento dell'aggiornamento. **Update**</span><span class="sxs-lookup"><span data-stu-id="0f487-211">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="0f487-212">Per ulteriori informazioni, vedere [Informazioni sugli errori](./dataset-datatable-dataview/row-error-information.md)di riga .</span><span class="sxs-lookup"><span data-stu-id="0f487-212">For more information, see [Row Error Information](./dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="0f487-213">Esempio di concorrenza ottimistica</span><span class="sxs-lookup"><span data-stu-id="0f487-213">Optimistic Concurrency Example</span></span>  
 <span data-ttu-id="0f487-214">Di seguito è riportato un semplice esempio che imposta il **UpdateCommand** di un **DataAdapter** per testare la concorrenza ottimistica e quindi utilizza il **RowUpdated** evento per testare le violazioni di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-214">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="0f487-215">Quando viene rilevata una violazione della concorrenza ottimistica, l'applicazione imposta il **RowError** della riga per cui è stato emesso l'aggiornamento per riflettere una violazione della concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0f487-215">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="0f487-216">Si noti che i valori dei parametri passati alla clausola WHERE del comando UPDATE vengono mappati ai valori **Original** delle rispettive colonne.</span><span class="sxs-lookup"><span data-stu-id="0f487-216">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f487-217">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f487-217">See also</span></span>

- [<span data-ttu-id="0f487-218">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0f487-218">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="0f487-219">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="0f487-219">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="0f487-220">Informazioni sugli errori di riga</span><span class="sxs-lookup"><span data-stu-id="0f487-220">Row Error Information</span></span>](./dataset-datatable-dataview/row-error-information.md)
- [<span data-ttu-id="0f487-221">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="0f487-221">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="0f487-222">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0f487-222">ADO.NET Overview</span></span>](ado-net-overview.md)
