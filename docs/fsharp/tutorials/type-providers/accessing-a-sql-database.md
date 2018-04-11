---
title: 'Procedura dettagliata: Accesso a un database SQL tramite provider di tipi (F#)'
description: 'Informazioni su come utilizzare il provider di tipi SqlDataConnection (LINQ to SQL) in F # 3.0 per generare i tipi per un database SQL quando si dispone di una connessione di database attivo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: dbc5d889fb7883b4327180fdf34accf45bf519e7
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="e02a2-104">Procedura dettagliata: Accesso a un database SQL tramite provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e02a2-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="e02a2-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e02a2-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="e02a2-106">Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="e02a2-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="e02a2-107">I collegamenti di riferimento API richiederà a MSDN.</span><span class="sxs-lookup"><span data-stu-id="e02a2-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="e02a2-108">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e02a2-109">Questa procedura dettagliata viene illustrato come utilizzare il provider di tipi SqlDataConnection (LINQ to SQL) che è disponibile in F # 3.0 per generare i tipi per i dati in un database SQL quando si dispone di una connessione in tempo reale a un database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="e02a2-110">Se non è una connessione in tempo reale a un database, ma è un LINQ al file di schema SQL (file. DBML), vedere [procedura dettagliata: generazione di tipi F # da un File DBML](generating-fsharp-types-from-dbml.md).</span><span class="sxs-lookup"><span data-stu-id="e02a2-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="e02a2-111">In questa procedura dettagliata vengono illustrate le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="e02a2-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="e02a2-112">In quest'ordine perché la procedura abbia esito positivo, è necessario effettuare queste attività:</span><span class="sxs-lookup"><span data-stu-id="e02a2-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="e02a2-113">Preparazione di un database di test</span><span class="sxs-lookup"><span data-stu-id="e02a2-113">Preparing a test database</span></span>

- <span data-ttu-id="e02a2-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e02a2-114">Creating the project</span></span>

- <span data-ttu-id="e02a2-115">Impostazione di un provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e02a2-115">Setting up a type provider</span></span>

- <span data-ttu-id="e02a2-116">Esecuzione di una query sui dati</span><span class="sxs-lookup"><span data-stu-id="e02a2-116">Querying the data</span></span>

- <span data-ttu-id="e02a2-117">Utilizzo dei campi che ammettono valori null</span><span class="sxs-lookup"><span data-stu-id="e02a2-117">Working with nullable fields</span></span>

- <span data-ttu-id="e02a2-118">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="e02a2-118">Calling a stored procedure</span></span>

- <span data-ttu-id="e02a2-119">Aggiornamento del database</span><span class="sxs-lookup"><span data-stu-id="e02a2-119">Updating the database</span></span>

- <span data-ttu-id="e02a2-120">L'esecuzione del codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e02a2-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="e02a2-121">Utilizzando il contesto dei dati completo</span><span class="sxs-lookup"><span data-stu-id="e02a2-121">Using the full data context</span></span>

- <span data-ttu-id="e02a2-122">L'eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="e02a2-122">Deleting data</span></span>

- <span data-ttu-id="e02a2-123">Creare un database di prova (in base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="e02a2-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="e02a2-124">Preparazione di un Database di Test</span><span class="sxs-lookup"><span data-stu-id="e02a2-124">Preparing a Test Database</span></span>
<span data-ttu-id="e02a2-125">In un server che esegue SQL Server, creare un database a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="e02a2-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="e02a2-126">È possibile utilizzare il database creare script nella parte inferiore della pagina nella sezione [la creazione di un database di prova](#creating-a-test-database) per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="e02a2-127">Per preparare un database di test</span><span class="sxs-lookup"><span data-stu-id="e02a2-127">To prepare a test database</span></span>

<span data-ttu-id="e02a2-128">Per eseguire lo Script di creazione MyDatabase, aprire il **vista** menu, quindi scegliere **Esplora oggetti di SQL Server** oppure scegliere Ctrl +\, tasti Ctrl + S.</span><span class="sxs-lookup"><span data-stu-id="e02a2-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="e02a2-129">In **Esplora oggetti di SQL Server** finestra, aprire il menu di scelta rapida per l'istanza appropriata, scegliere **nuova Query**, copiare lo script nella parte inferiore della pagina e quindi incollare lo script nell'editor.</span><span class="sxs-lookup"><span data-stu-id="e02a2-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="e02a2-130">Per eseguire lo script SQL, scegliere l'icona della barra degli strumenti con il simbolo triangolare oppure premere i tasti Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="e02a2-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="e02a2-131">Per ulteriori informazioni su **Esplora oggetti di SQL Server**, vedere [sviluppo del Database connesso](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span><span class="sxs-lookup"><span data-stu-id="e02a2-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="e02a2-132">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e02a2-132">Creating the project</span></span>
<span data-ttu-id="e02a2-133">Successivamente, si crea un progetto di applicazione di F #.</span><span class="sxs-lookup"><span data-stu-id="e02a2-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="e02a2-134">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="e02a2-134">To create and set up the project</span></span>

1. <span data-ttu-id="e02a2-135">Creare un nuovo progetto di applicazione F #.</span><span class="sxs-lookup"><span data-stu-id="e02a2-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="e02a2-136">Aggiungere riferimenti a [Typeproviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), così come `System.Data`, e `System.Data.Linq`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="e02a2-137">Aprire gli spazi dei nomi appropriato aggiungendo le righe di codice seguente all'inizio dei file di codice F # FS.</span><span class="sxs-lookup"><span data-stu-id="e02a2-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="e02a2-138">Come con molti altri programmi F #, è possibile eseguire il codice in questa procedura dettagliata di un programma compilato, o è possibile eseguirlo in modo interattivo come script.</span><span class="sxs-lookup"><span data-stu-id="e02a2-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="e02a2-139">Se si preferisce utilizzare gli script, aprire il menu di scelta rapida per il nodo del progetto, seleziona **Aggiungi nuovo elemento**, aggiungere un file di script F # e aggiungere il codice in ogni passaggio allo script.</span><span class="sxs-lookup"><span data-stu-id="e02a2-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="e02a2-140">È necessario aggiungere le righe seguenti all'inizio del file da caricare i riferimenti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e02a2-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="e02a2-141">È quindi possibile selezionare ogni blocco di codice, aggiungerlo e premere Alt + INVIO per eseguirlo in F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="e02a2-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="e02a2-142">Impostazione di un provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e02a2-142">Setting up a type provider</span></span>
<span data-ttu-id="e02a2-143">In questo passaggio viene creato un provider di tipi per lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="e02a2-144">Per configurare il provider di tipi da una connessione diretta del database</span><span class="sxs-lookup"><span data-stu-id="e02a2-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="e02a2-145">Esistono due righe critiche del codice necessarie per creare i tipi che è possibile utilizzare per un database SQL tramite il provider di tipi di query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="e02a2-146">Innanzitutto, creare un'istanza del provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="e02a2-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="e02a2-147">A tale scopo, creare l'aspetto seguente abbreviazione di tipo per un `SqlDataConnection` con un parametro generico statico.</span><span class="sxs-lookup"><span data-stu-id="e02a2-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="e02a2-148">`SqlDataConnection` è un provider di tipi SQL e non deve essere confuso con `SqlConnection` tipo che è utilizzato nella programmazione di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e02a2-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="e02a2-149">Se si dispone di un database che si desidera connettersi e dispone di una stringa di connessione, usare il codice seguente per richiamare il provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="e02a2-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="e02a2-150">Sostituire con la propria stringa di connessione per la stringa di esempio specificata.</span><span class="sxs-lookup"><span data-stu-id="e02a2-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="e02a2-151">Ad esempio, se il server MYSERVER e l'istanza del database è l'istanza, il nome del database è MyDatabase e si desidera utilizzare l'autenticazione di Windows per accedere al database, quindi la stringa di connessione sarebbe quello specificato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e02a2-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="e02a2-152">Ora è un tipo, `dbSchema`, che è un tipo padre che contiene tutti i tipi generati che rappresentano le tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="e02a2-153">È anche un oggetto, `db`, che abbia come membri di tutte le tabelle nel database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="e02a2-154">I nomi di tabella sono di proprietà e il tipo di queste proprietà viene generato dal compilatore F #.</span><span class="sxs-lookup"><span data-stu-id="e02a2-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="e02a2-155">Degli stessi tipi vengono visualizzati come i tipi annidati in `dbSchema.ServiceTypes`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="e02a2-156">Di conseguenza, i dati recuperati per le righe delle tabelle è un'istanza del tipo appropriato che è stato generato per la tabella.</span><span class="sxs-lookup"><span data-stu-id="e02a2-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="e02a2-157">Il nome del tipo è `ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="e02a2-158">Per acquisire familiarità con modalità di interpretazione delle query in query SQL linguaggio F #, esaminare la riga che imposta il `Log` proprietà nel contesto dati.</span><span class="sxs-lookup"><span data-stu-id="e02a2-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="e02a2-159">Per esplorare ulteriormente i tipi creati mediante il provider di tipi, aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e02a2-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="e02a2-160">Passare il mouse su `table1` per visualizzare il relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="e02a2-161">Il tipo è `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` e l'argomento generico implica che il tipo di ogni riga è il tipo generato, `dbSchema.ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="e02a2-162">Il compilatore crea un tipo simile per ogni tabella nel database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="e02a2-163">Esecuzione di una query sui dati</span><span class="sxs-lookup"><span data-stu-id="e02a2-163">Querying the data</span></span>
<span data-ttu-id="e02a2-164">In questo passaggio, scrivere una query utilizzando espressioni di query F #.</span><span class="sxs-lookup"><span data-stu-id="e02a2-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="e02a2-165">Per eseguire una query sui dati</span><span class="sxs-lookup"><span data-stu-id="e02a2-165">To query the data</span></span>

1. <span data-ttu-id="e02a2-166">Ora è possibile creare una query per la tabella nel database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="e02a2-167">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e02a2-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="e02a2-168">L'aspetto della parola `query` indica che si tratta di un'espressione di query, un tipo di espressione di calcolo che genera una raccolta di risultati simile di una query sul database tipico.</span><span class="sxs-lookup"><span data-stu-id="e02a2-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="e02a2-169">Se si posiziona sulla query, si noterà che è un'istanza di [classe LINQ. querybuilder](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), un tipo che definisce l'espressione di calcolo di query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="e02a2-170">Se si passa il mouse `query1`, si noterà che è un'istanza di `System.Linq.IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="e02a2-171">Come suggerisce il nome, `System.Linq.IQueryable` rappresenta i dati che possono essere eseguita una query, non il risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="e02a2-172">Una query è soggetta alla valutazione differita, che significa che il database è solo di eseguire una query quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="e02a2-173">La riga finale passa la query tramite `Seq.iter`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="e02a2-174">Le query enumerabile e possono essere Iterate come sequenze.</span><span class="sxs-lookup"><span data-stu-id="e02a2-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="e02a2-175">Per ulteriori informazioni, vedere [espressioni di Query](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e02a2-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="e02a2-176">Ora è possibile aggiungere un operatore di query alla query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-176">Now add a query operator to the query.</span></span> <span data-ttu-id="e02a2-177">Esistono un numero di operatori di query disponibili che è possibile utilizzare per costruire query più complesse.</span><span class="sxs-lookup"><span data-stu-id="e02a2-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="e02a2-178">Questo esempio mostra anche che è possibile eliminare la variabile di query e utilizzare invece un operatore pipeline.</span><span class="sxs-lookup"><span data-stu-id="e02a2-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="e02a2-179">Aggiungere una query più complessa con un join di due tabelle.</span><span class="sxs-lookup"><span data-stu-id="e02a2-179">Add a more complex query with a join of two tables.</span></span>

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. <span data-ttu-id="e02a2-180">Nel codice del mondo reale, i parametri nella query sono in genere valori o le variabili, costanti non in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="e02a2-181">Aggiungere il codice seguente che esegue il wrapping di una query in una funzione che accetta un parametro e quindi chiama tale funzione con il valore 10.</span><span class="sxs-lookup"><span data-stu-id="e02a2-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="e02a2-182">Utilizzo dei campi che ammettono valori null</span><span class="sxs-lookup"><span data-stu-id="e02a2-182">Working with nullable fields</span></span>
<span data-ttu-id="e02a2-183">Nei database, spesso i campi consentono valori null.</span><span class="sxs-lookup"><span data-stu-id="e02a2-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="e02a2-184">Nel sistema di tipi .NET, è possibile utilizzare i tipi di dati numerici normali per i dati che ammette valori null, perché non dispone di tali tipi null come un possibile valore.</span><span class="sxs-lookup"><span data-stu-id="e02a2-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="e02a2-185">Di conseguenza, questi valori sono rappresentati da istanze di `System.Nullable` tipo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="e02a2-186">Anziché il valore di tali campi direttamente con il nome del campo, è necessario eseguire alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e02a2-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="e02a2-187">È possibile utilizzare il `System.Nullable.Value` proprietà per accedere al valore sottostante di un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="e02a2-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="e02a2-188">Il `System.Nullable.Value` proprietà genera un'eccezione se l'oggetto è null anziché un valore.</span><span class="sxs-lookup"><span data-stu-id="e02a2-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="e02a2-189">È possibile utilizzare il `System.Nullable.HasValue` metodo booleano per determinare se esiste un valore oppure utilizzare `System.Nullable.GetValueOrDefault()` per assicurarsi di avere un valore effettivo in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="e02a2-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="e02a2-190">Se si utilizza `System.Nullable.GetValueOrDefault()` è un valore null nel database, quindi viene sostituito con un valore, ad esempio una stringa vuota per i tipi string, 0 per i tipi integrali o 0,0 per Mobile tipi di punti.</span><span class="sxs-lookup"><span data-stu-id="e02a2-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="e02a2-191">Quando è necessario eseguire i test di uguaglianza o confronti tra valori ammette valori null in un `where` clausola in una query, è possibile utilizzare gli operatori che ammette valori null, vedere il [modulo Linq. nullableoperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e02a2-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="e02a2-192">Si tratta ad esempio gli operatori di confronto regolare `=`, `>`, `<=`e così via, ad eccezione del fatto che un punto interrogativo viene visualizzata a sinistra o destra dell'operatore di valori nullable.</span><span class="sxs-lookup"><span data-stu-id="e02a2-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="e02a2-193">Ad esempio, l'operatore `>?` è maggiore-operatore con un valore nullable a destra.</span><span class="sxs-lookup"><span data-stu-id="e02a2-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="e02a2-194">Il funzionamento di questi operatori è che se entrambi i lati dell'espressione sono null, l'espressione restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="e02a2-195">In un `where` clausola, in genere significa che le righe che contengono campi null non sono è selezionate e non è state restituite nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="e02a2-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="e02a2-196">Per funzionare con i campi che ammettono valori null</span><span class="sxs-lookup"><span data-stu-id="e02a2-196">To work with nullable fields</span></span>

<span data-ttu-id="e02a2-197">Il codice seguente illustra l'uso dei valori ammette valori null. Si supponga che **TestData1** è un campo di tipo integer che ammette valori null.</span><span class="sxs-lookup"><span data-stu-id="e02a2-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="e02a2-198">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="e02a2-198">Calling a stored procedure</span></span>
<span data-ttu-id="e02a2-199">Le stored procedure nel database possono essere chiamate da F #.</span><span class="sxs-lookup"><span data-stu-id="e02a2-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="e02a2-200">È necessario impostare il parametro static `StoredProcedures` per `true` nell'istanza del provider di tipo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="e02a2-201">Il provider di tipi `SqlDataConnection` contiene diversi metodi statici che è possibile utilizzare per configurare i tipi generati.</span><span class="sxs-lookup"><span data-stu-id="e02a2-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="e02a2-202">Per una descrizione completa di questi, vedere [Provider di tipi SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e02a2-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="e02a2-203">Viene generato un metodo nel tipo di contesto dati per ogni stored procedure.</span><span class="sxs-lookup"><span data-stu-id="e02a2-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="e02a2-204">Per chiamare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="e02a2-204">To call a stored procedure</span></span>

<span data-ttu-id="e02a2-205">Se le stored procedure accetta parametri che ammettono valori null, è necessario passare un oggetto appropriato `System.Nullable` valore.</span><span class="sxs-lookup"><span data-stu-id="e02a2-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="e02a2-206">Il valore restituito di un metodo di stored procedure che restituisce un valore scalare o una tabella è `System.Data.Linq.ISingleResult`, che contiene le proprietà che consentono di accedere ai dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="e02a2-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="e02a2-207">L'argomento tipo per `System.Data.Linq.ISingleResult` dipende la procedura specifica e viene anche uno dei tipi generati dal provider di tipo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="e02a2-208">Per una stored procedure denominata `Procedure1`, il tipo è `Procedure1Result`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="e02a2-209">Il tipo `Procedure1Result` contiene i nomi delle colonne in una tabella restituita, o, per una stored procedure che restituisce un valore scalare, che rappresenta il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="e02a2-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="e02a2-210">Il codice seguente si presuppone che esista una stored procedure `Procedure1` sul database che accetta due numeri interi che ammette valori null come parametri, viene eseguita una query che restituisce una colonna denominata `TestData1`e restituisce un intero.</span><span class="sxs-lookup"><span data-stu-id="e02a2-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a><span data-ttu-id="e02a2-211">Aggiornamento del database</span><span class="sxs-lookup"><span data-stu-id="e02a2-211">Updating the database</span></span>
<span data-ttu-id="e02a2-212">Il tipo DataContext LINQ contiene metodi che rendono più semplice eseguire gli aggiornamenti di database transazionali in modo completamente tipizzato con i tipi generati.</span><span class="sxs-lookup"><span data-stu-id="e02a2-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="e02a2-213">Per aggiornare il database</span><span class="sxs-lookup"><span data-stu-id="e02a2-213">To update the database</span></span>

1. <span data-ttu-id="e02a2-214">Nel codice seguente, più righe vengono aggiunte al database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="e02a2-215">Se si aggiunge solo una riga, è possibile utilizzare `System.Data.Linq.Table.InsertOnSubmit()` per specificare la nuova riga da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e02a2-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="e02a2-216">Se si inseriscono più righe, è consigliabile posizionare in una raccolta e chiamare `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span><span class="sxs-lookup"><span data-stu-id="e02a2-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="e02a2-217">Quando si chiama uno di questi metodi, il database non viene modificato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e02a2-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="e02a2-218">È necessario chiamare `System.Data.Linq.DataContext.SubmitChanges` per eseguire il commit delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="e02a2-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="e02a2-219">Per impostazione predefinita, tutte le operazioni eseguite prima di chiamare `System.Data.Linq.DataContext.SubmitChanges` in modo implicito fa parte della stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. <span data-ttu-id="e02a2-220">Ora di pulire le righe chiamando un'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-220">Now clean up the rows by calling a delete operation.</span></span>

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a><span data-ttu-id="e02a2-221">L'esecuzione del codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e02a2-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="e02a2-222">È inoltre possibile specificare Transact-SQL direttamente tramite il `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` metodo la `DataContext` classe.</span><span class="sxs-lookup"><span data-stu-id="e02a2-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="e02a2-223">Per eseguire comandi SQL personalizzati</span><span class="sxs-lookup"><span data-stu-id="e02a2-223">To execute custom SQL commands</span></span>

<span data-ttu-id="e02a2-224">Il codice seguente viene illustrato come inviare comandi SQL per inserire un record in una tabella ed eliminare un record da una tabella.</span><span class="sxs-lookup"><span data-stu-id="e02a2-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a><span data-ttu-id="e02a2-225">Utilizzando il contesto dei dati completo</span><span class="sxs-lookup"><span data-stu-id="e02a2-225">Using the full data context</span></span>
<span data-ttu-id="e02a2-226">Negli esempi precedenti, il `GetDataContext` metodo è stato utilizzato per ottenere ciò che viene chiamato il *contesto dati semplificato* per lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="e02a2-227">Il contesto dati semplificato è più facile da utilizzare durante la creazione di query perché non sono disponibili tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="e02a2-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="e02a2-228">Pertanto, quando si esplorano le proprietà in IntelliSense, è possibile concentrarsi sulla struttura di database, ad esempio le tabelle e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="e02a2-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="e02a2-229">Tuttavia, vi è un limite a cosa si può fare con il contesto dati semplificato.</span><span class="sxs-lookup"><span data-stu-id="e02a2-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="e02a2-230">Un contesto dei dati completo che offre la possibilità di eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="e02a2-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="e02a2-231">è inoltre disponibile il file si trova nel `ServiceTypes` e ha il nome del *DataContext* parametro statico se è stato specificato.</span><span class="sxs-lookup"><span data-stu-id="e02a2-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="e02a2-232">Se non è stato fornito, il nome del tipo di contesto dati viene generato automaticamente da SqlMetal.exe in base all'input di altri.</span><span class="sxs-lookup"><span data-stu-id="e02a2-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="e02a2-233">Eredita il contesto dei dati completo `System.Data.Linq.DataContext` ed espone i membri della relativa classe base, inclusi i riferimenti ai tipi di dati ADO.NET, ad esempio il `Connection` oggetti, metodi, ad esempio `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` e `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` che è possibile utilizzare per scrivere query in SQL, e inoltre un modo per utilizzare le transazioni in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e02a2-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="e02a2-234">Utilizzare il contesto dati completa</span><span class="sxs-lookup"><span data-stu-id="e02a2-234">To use the full data context</span></span>

<span data-ttu-id="e02a2-235">Il codice seguente viene illustrato il recupero di un oggetto di contesto dati completa e utilizzarlo per eseguire comandi direttamente sul database.</span><span class="sxs-lookup"><span data-stu-id="e02a2-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="e02a2-236">In questo caso, due comandi vengono eseguiti come parte della stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-236">In this case, two commands are executed as part of the same transaction.</span></span>

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a><span data-ttu-id="e02a2-237">L'eliminazione dei dati</span><span class="sxs-lookup"><span data-stu-id="e02a2-237">Deleting data</span></span>
<span data-ttu-id="e02a2-238">Questo passaggio illustra come eliminare righe da una tabella dati.</span><span class="sxs-lookup"><span data-stu-id="e02a2-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="e02a2-239">Per eliminare righe dal database</span><span class="sxs-lookup"><span data-stu-id="e02a2-239">To delete rows from the database</span></span>

<span data-ttu-id="e02a2-240">A questo punto, pulizia backup di tutte le righe aggiunte scrivendo una funzione che elimina le righe da una tabella specificata, un'istanza del `System.Data.Linq.Table` classe.</span><span class="sxs-lookup"><span data-stu-id="e02a2-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="e02a2-241">Scrivere una query per trovare tutte le righe che si desidera eliminare, quindi inviare tramite pipe i risultati della query nel `deleteRows` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e02a2-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="e02a2-242">Questo codice consente di sfruttare la possibilità di fornire applicazione parziale degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="e02a2-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a><span data-ttu-id="e02a2-243">Creazione di un database di test</span><span class="sxs-lookup"><span data-stu-id="e02a2-243">Creating a test database</span></span>
<span data-ttu-id="e02a2-244">In questa sezione viene illustrato come configurare il database di test da utilizzare in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="e02a2-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="e02a2-245">Si noti che se si modifica il database in qualche modo, sarà necessario reimpostare il provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="e02a2-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="e02a2-246">Per reimpostare il provider di tipi, ricostruire o pulire il progetto che contiene il tipo provider.</span><span class="sxs-lookup"><span data-stu-id="e02a2-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="e02a2-247">Per creare il database di test</span><span class="sxs-lookup"><span data-stu-id="e02a2-247">To create the test database</span></span>

1. <span data-ttu-id="e02a2-248">In **Esplora Server**, aprire il menu di scelta rapida per il **connessioni dati** nodo e scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="e02a2-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="e02a2-249">Il **Aggiungi connessione** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e02a2-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="e02a2-250">Nel **nome Server** casella, specificare il nome di un'istanza di SQL Server che si hanno accesso amministrativo a o se non si dispone di accesso a un server, specificare (localdb\v11.0).</span><span class="sxs-lookup"><span data-stu-id="e02a2-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="e02a2-251">SQL Express LocalDB fornisce un server di database semplice per lo sviluppo e test nel computer.</span><span class="sxs-lookup"><span data-stu-id="e02a2-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="e02a2-252">Viene creato un nuovo nodo **Esplora Server** in **connessioni dati**.</span><span class="sxs-lookup"><span data-stu-id="e02a2-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="e02a2-253">Per ulteriori informazioni su LocalDB, vedere [procedura dettagliata: creazione di un File di Database locale in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="e02a2-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="e02a2-254">Aprire il menu di scelta rapida per il nuovo nodo di connessione e selezionare **nuova Query**.</span><span class="sxs-lookup"><span data-stu-id="e02a2-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="e02a2-255">Copiare lo script SQL seguente, incollarlo nell'editor di query e quindi scegliere il **Execute** sulla barra degli strumenti o premere i tasti Ctrl + Maiusc + A.</span><span class="sxs-lookup"><span data-stu-id="e02a2-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a><span data-ttu-id="e02a2-256">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e02a2-256">See Also</span></span>
[<span data-ttu-id="e02a2-257">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="e02a2-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="e02a2-258">Provider di tipi SqlDataConnection</span><span class="sxs-lookup"><span data-stu-id="e02a2-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="e02a2-259">Procedura dettagliata: Generazione di tipi F # da un File DBML</span><span class="sxs-lookup"><span data-stu-id="e02a2-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="e02a2-260">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="e02a2-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="e02a2-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e02a2-261">LINQ to SQL</span></span>](../../../../docs/framework/data/adonet/sql/linq/index.md)

[<span data-ttu-id="e02a2-262">SqlMetal.exe &#40;strumento per la generazione di codice&#41;</span><span class="sxs-lookup"><span data-stu-id="e02a2-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
