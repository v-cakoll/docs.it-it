---
title: Domande frequenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634703"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="fa7e8-102">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="fa7e8-102">Frequently Asked Questions</span></span>

<span data-ttu-id="fa7e8-103">Le sezioni seguenti rispondono ad alcuni problemi comuni che possono verificarsi quando si implementa LINQ.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-103">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="fa7e8-104">Ulteriori problemi vengono risolti nella [risoluzione dei](troubleshooting.md)problemi.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-104">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="fa7e8-105">Connessione non possibile</span><span class="sxs-lookup"><span data-stu-id="fa7e8-105">Cannot Connect</span></span>

<span data-ttu-id="fa7e8-106">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-106">Q.</span></span> <span data-ttu-id="fa7e8-107">Non è possibile connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-107">I cannot connect to my database.</span></span>

<span data-ttu-id="fa7e8-108">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-108">A.</span></span> <span data-ttu-id="fa7e8-109">Verificare che la stringa di connessione sia corretta e che l'istanza di SQL Server sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="fa7e8-110">Tenere inoltre presente che [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] richiede che sia abilitato il protocollo Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="fa7e8-111">Per ulteriori informazioni, vedere [learning by Walkthroughs](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-111">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="fa7e8-112">Perdita delle modifiche al database</span><span class="sxs-lookup"><span data-stu-id="fa7e8-112">Changes to Database Lost</span></span>

<span data-ttu-id="fa7e8-113">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-113">Q.</span></span> <span data-ttu-id="fa7e8-114">Quando si riesegue l'applicazione dopo avere apportato una modifica ai dati presenti nel database, la modifica va persa.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="fa7e8-115">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-115">A.</span></span> <span data-ttu-id="fa7e8-116">Accertarsi di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per salvare i risultati nel database.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="fa7e8-117">Durata di una connessione di database aperta</span><span class="sxs-lookup"><span data-stu-id="fa7e8-117">Database Connection: Open How Long?</span></span>

<span data-ttu-id="fa7e8-118">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-118">Q.</span></span> <span data-ttu-id="fa7e8-119">Per quanto tempo rimane aperta la connessione di database?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-119">How long does my database connection remain open?</span></span>

<span data-ttu-id="fa7e8-120">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-120">A.</span></span> <span data-ttu-id="fa7e8-121">Una connessione rimane in genere aperta finché non si usano i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="fa7e8-122">Se si prevede di impiegare tempo per elaborare tutti i risultati ed è possibile memorizzare nella cache i risultati, applicare <xref:System.Linq.Enumerable.ToList%2A> alla query.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="fa7e8-123">Negli scenari comuni dove ogni oggetto viene elaborato solo una volta, il modello di flusso è superiore in `DataReader` e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa7e8-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="fa7e8-124">I dettagli esatti di utilizzo della connessione dipendono dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-124">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="fa7e8-125">Stato della connessione se <xref:System.Data.Linq.DataContext> viene costruito con un oggetto connessione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="fa7e8-126">Impostazioni della stringa di connessione, ad esempio abilitando MARS (Multiple Active Result Sets).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="fa7e8-127">Per altre informazioni, vedere [MARS (Multiple Active Result Sets)](../multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-127">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="fa7e8-128">Aggiornamento senza query</span><span class="sxs-lookup"><span data-stu-id="fa7e8-128">Updating Without Querying</span></span>

<span data-ttu-id="fa7e8-129">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-129">Q.</span></span> <span data-ttu-id="fa7e8-130">È possibile aggiornare i dati della tabella senza prima eseguire una query sul database?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-130">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="fa7e8-131">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-131">A.</span></span> <span data-ttu-id="fa7e8-132">Sebbene [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non disponga di comandi di aggiornamento basati su set, è possibile usare le tecniche seguenti per aggiornare senza prima eseguire una query:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="fa7e8-133">Usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per inviare il codice SQL.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="fa7e8-134">Creare una nuova istanza dell'oggetto e inizializzare tutti i valori (campi) correnti che influiscono sull'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="fa7e8-135">Associare quindi l'oggetto a <xref:System.Data.Linq.DataContext> usando <xref:System.Data.Linq.Table%601.Attach%2A> e modificare il campo desiderato.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="fa7e8-136">Risultati imprevisti delle query</span><span class="sxs-lookup"><span data-stu-id="fa7e8-136">Unexpected Query Results</span></span>

<span data-ttu-id="fa7e8-137">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-137">Q.</span></span> <span data-ttu-id="fa7e8-138">La query restituisce risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-138">My query is returning unexpected results.</span></span> <span data-ttu-id="fa7e8-139">Come è possibile controllare quello che si sta verificando?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-139">How can I inspect what is occurring?</span></span>

<span data-ttu-id="fa7e8-140">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-141">fornisce molti strumenti per controllare il codice SQL generato.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="fa7e8-142">Uno dei più importanti è <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="fa7e8-143">Per ulteriori informazioni, vedere [supporto](debugging-support.md)per il debug.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-143">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="fa7e8-144">Risultati imprevisti delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="fa7e8-144">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="fa7e8-145">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-145">Q.</span></span> <span data-ttu-id="fa7e8-146">Il valore restituito di una stored procedure viene calcolato da `MAX()`.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="fa7e8-147">Quando si trascina il stored procedure nell'area di progettazione O/R, il valore restituito non è corretto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-147">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="fa7e8-148">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-149">fornisce due modalità per restituire i valori generati dal database tramite le stored procedure:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-149">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="fa7e8-150">Assegnando un nome al risultato di output.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-150">By naming the output result.</span></span>

- <span data-ttu-id="fa7e8-151">Specificando in modo esplicito un parametro di output.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-151">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="fa7e8-152">Di seguito viene riportato un esempio di output non corretto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="fa7e8-153">Poiché in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è possibile eseguire il mapping dei risultati, viene restituito sempre 0:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="fa7e8-154">Di seguito viene riportato un esempio di output corretto usando un parametro di output:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-154">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="fa7e8-155">Di seguito viene riportato un esempio di output corretto assegnando un nome al risultato di output:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-155">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="fa7e8-156">Per ulteriori informazioni, vedere [personalizzazione di operazioni utilizzando stored procedure](customizing-operations-by-using-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-156">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="fa7e8-157">Errori di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="fa7e8-157">Serialization Errors</span></span>

<span data-ttu-id="fa7e8-158">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-158">Q.</span></span> <span data-ttu-id="fa7e8-159">Quando si tenta di serializzare, viene ricevuto l'errore seguente: "tipo ' System. Data. Linq. ChangeTracker + StandardChangeTracker '... non è contrassegnato come serializzabile ".</span><span class="sxs-lookup"><span data-stu-id="fa7e8-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="fa7e8-160">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-160">A.</span></span> <span data-ttu-id="fa7e8-161">La generazione del codice in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta la serializzazione <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="fa7e8-162">Non supporta <xref:System.Xml.Serialization.XmlSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="fa7e8-163">Per altre informazioni, vedere [Serializzazione](serialization.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-163">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="fa7e8-164">Più file DBML</span><span class="sxs-lookup"><span data-stu-id="fa7e8-164">Multiple DBML Files</span></span>

<span data-ttu-id="fa7e8-165">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-165">Q.</span></span> <span data-ttu-id="fa7e8-166">Quando si dispone di più file DBML che condividono alcune tabelle, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="fa7e8-167">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-167">A.</span></span> <span data-ttu-id="fa7e8-168">Impostare le proprietà dello **spazio dei** nomi del contesto e **dello spazio dei nomi dell'entità** dal Object Relational Designer a un valore distinto per ogni file dbml.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-168">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="fa7e8-169">Questo approccio elimina il conflitto di nome/spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-169">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="fa7e8-170">Come evitare l'impostazione esplicita dei valori generati dal database nelle operazioni di inserimento o aggiornamento</span><span class="sxs-lookup"><span data-stu-id="fa7e8-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="fa7e8-171">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-171">Q.</span></span> <span data-ttu-id="fa7e8-172">Quando in una tabella di database con una colonna `DateCreated` la cui impostazione predefinita è SQL `Getdate()`</span><span class="sxs-lookup"><span data-stu-id="fa7e8-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="fa7e8-173">si tenta di inserire un nuovo record usando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], il valore viene impostato su `NULL`</span><span class="sxs-lookup"><span data-stu-id="fa7e8-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="fa7e8-174">anziché sul valore predefinito del database.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-174">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="fa7e8-175">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-176">gestisce automaticamente questa situazione per le colonne Identity (incremento automatico) e rowguidcol (GUID generato dal database) e timestamp.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="fa7e8-177">In altri casi, è necessario impostare manualmente <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` e <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="fa7e8-178">Più valori DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="fa7e8-178">Multiple DataLoadOptions</span></span>

<span data-ttu-id="fa7e8-179">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-179">Q.</span></span> <span data-ttu-id="fa7e8-180">È possibile specificare opzioni di caricamento aggiuntive senza sovrascrivere la prima?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-180">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="fa7e8-181">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-181">A.</span></span> <span data-ttu-id="fa7e8-182">Sì.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-182">Yes.</span></span> <span data-ttu-id="fa7e8-183">La prima opzione non viene sovrascritta, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-183">The first is not overwritten, as in the following example:</span></span>

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="fa7e8-184">Errori durante l'uso di SQL Compact 3.5</span><span class="sxs-lookup"><span data-stu-id="fa7e8-184">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="fa7e8-185">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-185">Q.</span></span> <span data-ttu-id="fa7e8-186">Si verifica un errore quando si trascinano le tabelle da un database SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-186">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="fa7e8-187">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-187">A.</span></span> <span data-ttu-id="fa7e8-188">Il Object Relational Designer non supporta SQL Server Compact 3,5, sebbene il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa7e8-188">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="fa7e8-189">In questa situazione, è necessario creare classi dell'entità personalizzate e aggiungere gli attributi adatti.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="fa7e8-190">Errori nelle relazioni di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="fa7e8-190">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="fa7e8-191">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-191">Q.</span></span> <span data-ttu-id="fa7e8-192">Nella Object Relational Designer è stata utilizzata la forma di ereditarietà della casella degli strumenti per connettere due entità, ma si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-192">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="fa7e8-193">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-193">A.</span></span> <span data-ttu-id="fa7e8-194">Non è sufficiente creare la relazione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="fa7e8-195">È necessario fornire informazioni quali la colonna del discriminatore, il valore del discriminatore della classe base e il valore del discriminatore della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="fa7e8-196">Modello provider</span><span class="sxs-lookup"><span data-stu-id="fa7e8-196">Provider Model</span></span>

<span data-ttu-id="fa7e8-197">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-197">Q.</span></span> <span data-ttu-id="fa7e8-198">È disponibile un modello provider pubblico?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-198">Is a public provider model available?</span></span>

<span data-ttu-id="fa7e8-199">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-199">A.</span></span> <span data-ttu-id="fa7e8-200">Non è disponibile alcun un modello provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-200">No public provider model is available.</span></span> <span data-ttu-id="fa7e8-201">A questo punto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta solo SQL Server e SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="fa7e8-202">Attacchi SQL injection</span><span class="sxs-lookup"><span data-stu-id="fa7e8-202">SQL-Injection Attacks</span></span>

<span data-ttu-id="fa7e8-203">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-203">Q.</span></span> <span data-ttu-id="fa7e8-204">Come viene protetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dagli attacchi SQL injection?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="fa7e8-205">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-205">A.</span></span> <span data-ttu-id="fa7e8-206">L'intrusione nel codice SQL ha rappresentato un pericolo significativo per le query SQL tradizionali formate concatenando l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-207">evita tale intrusione usando <xref:System.Data.SqlClient.SqlParameter> nelle query.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-207">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="fa7e8-208">L'input dell'utente viene convertito in valori di parametro.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-208">User input is turned into parameter values.</span></span> <span data-ttu-id="fa7e8-209">Questo approccio impedisce l'uso di comandi dannosi dall'input del cliente.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-209">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="fa7e8-210">Modifica del flag di sola lettura nei file DBML</span><span class="sxs-lookup"><span data-stu-id="fa7e8-210">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="fa7e8-211">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-211">Q.</span></span> <span data-ttu-id="fa7e8-212">Come è possibile eliminare i metodi di impostazione da alcune proprietà quando si crea un modello a oggetti da un file DBML?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="fa7e8-213">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-213">A.</span></span> <span data-ttu-id="fa7e8-214">Attenersi alla procedura riportata di seguito per questo scenario avanzato:</span><span class="sxs-lookup"><span data-stu-id="fa7e8-214">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="fa7e8-215">Nel file con estensione dbml modificare la proprietà impostando il flag <xref:System.Data.Linq.ITable.IsReadOnly%2A> su `True`.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="fa7e8-216">Aggiungere una classe parziale.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-216">Add a partial class.</span></span> <span data-ttu-id="fa7e8-217">Creare un costruttore con i parametri per i membri di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-217">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="fa7e8-218">Esaminare il valore <xref:System.Data.Linq.Mapping.UpdateCheck> predefinito (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) per determinare se questo valore è corretto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="fa7e8-219">Se si usa il Object Relational Designer in Visual Studio, le modifiche potrebbero essere sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-219">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="fa7e8-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="fa7e8-220">APTCA</span></span>

<span data-ttu-id="fa7e8-221">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-221">Q.</span></span> <span data-ttu-id="fa7e8-222">System.Data.Linq è contrassegnato per l'uso da codice parzialmente attendibile?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="fa7e8-223">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-223">A.</span></span> <span data-ttu-id="fa7e8-224">Sì, l'assembly System. Data. Linq. dll è tra gli assembly .NET Framework contrassegnati con l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-224">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="fa7e8-225">Senza questo contrassegno, gli assembly nel .NET Framework devono essere usati solo da codice completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-225">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="fa7e8-226">Lo scenario principale in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per consentire chiamanti parzialmente attendibili è quello di consentire l'accesso all'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] da applicazioni Web, in cui la configurazione del *trust* è media.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="fa7e8-227">Esecuzione del mapping dei dati da più tabelle</span><span class="sxs-lookup"><span data-stu-id="fa7e8-227">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="fa7e8-228">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-228">Q.</span></span> <span data-ttu-id="fa7e8-229">I dati dell'entità derivano da più tabelle.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="fa7e8-230">Come è possibile eseguirne il mapping?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-230">How do I map it?</span></span>

<span data-ttu-id="fa7e8-231">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-231">A.</span></span> <span data-ttu-id="fa7e8-232">È possibile creare una visualizzazione in un database ed eseguire il mapping dell'entità alla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-233">genera lo stesso codice SQL per le visualizzazioni come per le tabelle.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-233">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="fa7e8-234">L'utilizzo di visualizzazioni in questo scenario presenta delle limitazioni.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="fa7e8-235">Questo approccio funziona in modo più sicuro quando le operazioni eseguite su <xref:System.Data.Linq.Table%601> vengono supportate dalla visualizzazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="fa7e8-236">Solo l'utente conosce le operazioni desiderate da eseguire.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-236">Only you know which operations are intended.</span></span> <span data-ttu-id="fa7e8-237">Ad esempio, la maggior parte delle applicazioni è di sola lettura e un altro numero notevole esegue `Create`/`Update`/operazioni di `Delete` solo utilizzando le stored procedure sulle viste.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="fa7e8-238">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="fa7e8-238">Connection Pooling</span></span>

<span data-ttu-id="fa7e8-239">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-239">Q.</span></span> <span data-ttu-id="fa7e8-240">È disponibile un costrutto che possa facilitare il pool <xref:System.Data.Linq.DataContext>?</span><span class="sxs-lookup"><span data-stu-id="fa7e8-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="fa7e8-241">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-241">A.</span></span> <span data-ttu-id="fa7e8-242">Non tentare di riutilizzare le istanze di <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="fa7e8-243">Ogni oggetto <xref:System.Data.Linq.DataContext> conserva lo stato (inclusa una cache delle identità) per una determinata sessione di modifica/query.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="fa7e8-244">Per ottenere nuove istanze basate sullo stato corrente del database, usare un nuovo oggetto <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="fa7e8-245">È comunque possibile usare il pool di connessioni ADO.NET sottostanti.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-245">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="fa7e8-246">Per altre informazioni, vedere [Pool di connessioni SQL Server (ADO.NET)](../../sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="fa7e8-247">Il secondo oggetto DataContext non viene aggiornato</span><span class="sxs-lookup"><span data-stu-id="fa7e8-247">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="fa7e8-248">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-248">Q.</span></span> <span data-ttu-id="fa7e8-249">Un'istanza di <xref:System.Data.Linq.DataContext> è stata usata per archiviare i valori nel database.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="fa7e8-250">Tuttavia, un secondo oggetto <xref:System.Data.Linq.DataContext> nello stesso database non riflette i valori aggiornati.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="fa7e8-251">La seconda istanza <xref:System.Data.Linq.DataContext> sembra restituire i valori memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="fa7e8-252">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-252">A.</span></span> <span data-ttu-id="fa7e8-253">Questo comportamento è previsto dalla progettazione.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fa7e8-254">continua a restituire gli stessi valori o le stesse istanze specificate nella prima istanza.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="fa7e8-255">Quando si effettuano gli aggiornamenti, usare la concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="fa7e8-256">I dati originali vengono usati per controllare lo stato corrente del database in modo da asserire che risulta ancora invariato.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="fa7e8-257">Se è stato modificato, si verifica un conflitto e l'applicazione deve risolverlo.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="fa7e8-258">Un'opzione dell'applicazione è reimpostare lo stato originale allo stato corrente del database e provare nuovamente l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="fa7e8-259">Per altre informazioni, vedere [procedura: gestire i conflitti di modifica](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e8-259">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="fa7e8-260">È anche possibile impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su false, in modo da disattivare la memorizzazione nella cache e la ricerca delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="fa7e8-261">È quindi possibile recuperare gli ultimi valori ogni volta che si esegue una query.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-261">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="fa7e8-262">Impossibile chiamare SubmitChanges in modalità di sola lettura</span><span class="sxs-lookup"><span data-stu-id="fa7e8-262">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="fa7e8-263">D.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-263">Q.</span></span> <span data-ttu-id="fa7e8-264">Quando si tenta di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in modalità di sola lettura, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="fa7e8-265">Oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-265">A.</span></span> <span data-ttu-id="fa7e8-266">La modalità di sola lettura non consente al contesto di tenere traccia delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="fa7e8-266">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa7e8-267">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa7e8-267">See also</span></span>

- [<span data-ttu-id="fa7e8-268">Reference</span><span class="sxs-lookup"><span data-stu-id="fa7e8-268">Reference</span></span>](reference.md)
- [<span data-ttu-id="fa7e8-269">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="fa7e8-269">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="fa7e8-270">Sicurezza in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fa7e8-270">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
