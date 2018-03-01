---
title: 'Procedura dettagliata: generazione di tipi F# da un file di schema EDMX (F#)'
description: "Informazioni su come creare tipi F # per dati rappresentati da Entity Data Model (EDM) in F # 3.0, in cui lo schema è specificato in un file con estensione edmx."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="8f3eb-104">Procedura dettagliata: generazione di tipi F# da un file di schema EDMX</span><span class="sxs-lookup"><span data-stu-id="8f3eb-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="8f3eb-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="8f3eb-106">Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="8f3eb-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="8f3eb-107">I collegamenti di riferimento API richiederà a MSDN.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="8f3eb-108">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="8f3eb-109">Questa procedura dettagliata per F# 3.0 spiega come creare tipi per dati rappresentati da Entity Data Model (EDM), lo schema per il quale è specificato in un file .edmx.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="8f3eb-110">Questa procedura dettagliata illustra inoltre come utilizzare il provider di tipi EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="8f3eb-111">Prima di iniziare, considerare se un provider di tipi SqlEntityConnection sia un'opzione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="8f3eb-112">Il provider di tipi SqlEntityConnection è ideale per scenari in cui si ha un database attivo che è possibile connettere durante la fase di sviluppo del progetto e non ci si ricorda di specificare la stringa di connessione in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="8f3eb-113">Tuttavia, questo provider di tipi è limitato in quanto non espone così tante funzionalità di database come il provider di tipi EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="8f3eb-114">Inoltre, se non si dispone di una connessione attiva per un progetto di database che utilizza Entity Data Model, è possibile utilizzare il file .edmx per scrivere codice rispetto al database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="8f3eb-115">Quando si utilizza il provider di tipi EdmxFile, il compilatore F# esegue EdmGen.exe per generare i tipi che fornisce.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="8f3eb-116">In questa procedura dettagliata vengono illustrate le seguenti attività, che è necessario eseguire in quest'ordine perché la procedura abbia esito positivo:</span><span class="sxs-lookup"><span data-stu-id="8f3eb-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="8f3eb-117">Creazione di un file EDMX</span><span class="sxs-lookup"><span data-stu-id="8f3eb-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="8f3eb-118">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="8f3eb-118">Creating the project</span></span>
<br />

- <span data-ttu-id="8f3eb-119">Ricerca o creazione di una stringa di connessione per Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8f3eb-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="8f3eb-120">Configurazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8f3eb-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="8f3eb-121">Esecuzione di una query sui dati</span><span class="sxs-lookup"><span data-stu-id="8f3eb-121">Querying the data</span></span>
<br />

- <span data-ttu-id="8f3eb-122">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="8f3eb-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="8f3eb-123">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8f3eb-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="8f3eb-124">Creazione di un file EDMX</span><span class="sxs-lookup"><span data-stu-id="8f3eb-124">Creating an EDMX file</span></span>
<span data-ttu-id="8f3eb-125">Se si dispone già di un file EDMX, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="8f3eb-126">Per creare un file EDMX</span><span class="sxs-lookup"><span data-stu-id="8f3eb-126">To create an EDMX file</span></span>

- <span data-ttu-id="8f3eb-127">Se si dispone già di un file EDMX, è possibile seguire le istruzioni alla fine di questa procedura dettagliata nel passaggio [la configurazione di Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span><span class="sxs-lookup"><span data-stu-id="8f3eb-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="8f3eb-128">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="8f3eb-128">Creating the project</span></span>
<span data-ttu-id="8f3eb-129">In questo passaggio viene creato un progetto e vengono aggiunti i riferimenti appropriati per utilizzare il provider di tipi EDMX.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="8f3eb-130">Per creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="8f3eb-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="8f3eb-131">Chiudere il progetto precedente, creare un altro progetto e denominarlo SchoolEDM.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="8f3eb-132">In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="8f3eb-133">Nel **assembly** area, scegliere il **Framework** nodo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="8f3eb-134">Nell'elenco di assembly disponibili, scegliere il **System.Data.Entity** e **LINQ** assembly, quindi scegliere il **Aggiungi** pulsante per aggiungere i riferimenti a queste assembly al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="8f3eb-135">Nel **assembly** area, selezionare il **estensioni** nodo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="8f3eb-136">Nell'elenco delle estensioni disponibili aggiungere un riferimento all'assembly FSharp.Data.TypeProviders.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="8f3eb-137">Aggiungere il codice seguente per aprire gli spazi dei nomi appropriati.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="8f3eb-138">Ricerca o creazione della stringa di connessione per Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8f3eb-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="8f3eb-139">La stringa di connessione per Entity Data Model (stringa di connessione EDMX) non include solo la stringa di connessione per il provider del database ma anche informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="8f3eb-140">Ad esempio, la stringa di connessione EDMX per un semplice database SQL Server è simile al seguente codice.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="8f3eb-141">Per ulteriori informazioni sulle stringhe di connessione EDMX, vedere [le stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="8f3eb-141">For more information about EDMX connection strings, see [Connection Strings](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="8f3eb-142">Per trovare o creare la stringa di connessione per Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8f3eb-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="8f3eb-143">Le stringhe di connessione EDMX possono essere difficili da generare manualmente, pertanto è possibile risparmiare tempo generandola a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="8f3eb-144">Se si conosce la stringa di connessione EDMX, è possibile ignorare questo passaggio e utilizzare semplicemente tale stringa nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="8f3eb-145">In caso contrario, utilizzare il codice seguente per generare la stringa di connessione EDMX da una stringa di connessione del database fornito.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="8f3eb-146">Configurazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8f3eb-146">Configuring the type provider</span></span>
<span data-ttu-id="8f3eb-147">In questo passaggio viene creato e configurato il provider di tipi con la stringa di connessione EDMX e vengono generati i tipi per lo schema definito nel file .edmx.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="8f3eb-148">Per configurare il provider di tipi e generare i tipi</span><span class="sxs-lookup"><span data-stu-id="8f3eb-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="8f3eb-149">Copiare il file .edmx, che è stato generato nel primo passaggio di questa procedura guidata, nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="8f3eb-150">Aprire il menu di scelta rapida per il nodo del progetto nel progetto F #, scegliere **Aggiungi elemento esistente**, quindi scegliere il file. edmx per aggiungerlo al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="8f3eb-151">Digitare il codice seguente per attivare il provider di tipi per il file .edmx.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="8f3eb-152">Sostituire *Server*\*istanza * con il nome del server che esegue SQL Server e il nome dell'istanza e utilizzare il nome del file con estensione edmx dal primo passaggio in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="8f3eb-153">Esecuzione di una query sui dati</span><span class="sxs-lookup"><span data-stu-id="8f3eb-153">Querying the data</span></span>
<span data-ttu-id="8f3eb-154">In questo passaggio utilizzare le espressioni di query F# per eseguire una query sul database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="8f3eb-155">Per eseguire una query sui dati</span><span class="sxs-lookup"><span data-stu-id="8f3eb-155">To query the data</span></span>

- <span data-ttu-id="8f3eb-156">Digitare il codice seguente per eseguire una query sui dati in Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="8f3eb-157">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="8f3eb-157">Calling a stored procedure</span></span>
<span data-ttu-id="8f3eb-158">È possibile chiamare stored procedure usando il provider di tipi EDMX.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="8f3eb-159">Nella procedura seguente, il database School contiene una stored procedure, **UpdatePerson**, che aggiorna un record, specificando i nuovi valori per le colonne.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="8f3eb-160">È possibile seguire questa stored procedure in quanto è esposta come metodo sul tipo DataContext.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="8f3eb-161">Per chiamare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="8f3eb-161">To call a stored procedure</span></span>

- <span data-ttu-id="8f3eb-162">Aggiungere il seguente codice per aggiornare i record.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="8f3eb-163">Il risultato è 1 se si ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="8f3eb-164">Si noti che **exactlyOne** viene utilizzato nell'espressione di query per garantire che un solo risultato sia restituito; in caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="8f3eb-165">Inoltre, per utilizzare valori nullable più facilmente, è possibile utilizzare la semplice **nullable** funzione definita in questo codice per creare un valore nullable da un valore comune.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="8f3eb-166">Configurazione di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8f3eb-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="8f3eb-167">È consigliabile completare questa procedura solo se si desidera sapere come generare un Entity Data Model completo da un database e non si dispone di un database con il quale testarlo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="8f3eb-168">Per configurare Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8f3eb-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="8f3eb-169">Nella barra dei menu, scegliere **SQL**, **Editor Transact-SQL**, **nuova Query** per creare un database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="8f3eb-170">Se richiesto, specificare il server di database e l'istanza.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="8f3eb-171">Copiare e incollare il contenuto dello script del database viene creato il database di studenti, come descritto nel [documentazione di Entity Framework](https://msdn.microsoft.com/data/JJ614587.aspx) nel centro per sviluppatori di dati.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](https://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="8f3eb-172">Eseguire lo script SQL scegliendo il pulsante della barra degli strumenti con il simbolo del triangolo o i tasti Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="8f3eb-173">In **Esplora Server**, aprire il menu di scelta rapida per **connessioni dati**, scegliere **Aggiungi connessione**e quindi immettere il nome del server di database, il nome del nome dell'istanza e il database School.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="8f3eb-174">Creare un progetto c# o applicazione Console Visual Basic, aprire il menu di scelta rapida, scegli **Aggiungi nuovo elemento**, quindi scegliere **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="8f3eb-175">Verrà aperta la Procedura guidata Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="8f3eb-176">Utilizzando questa procedura guidata è possibile scegliere la modalità di creazione di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="8f3eb-177">In **Scegli contenuto Model**, selezionare il **genera da database** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="8f3eb-178">Nella pagina successiva scegliere il database School appena creato come connessione dati.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="8f3eb-179">Questa connessione dovrebbe essere simile  **&lt;servername&gt;.&lt; InstanceName&gt;. School.dbo**.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="8f3eb-180">Copiare la stringa di connessione a entità negli Appunti perché tale stringa potrebbe essere importante successivamente.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="8f3eb-181">Verificare che la casella di controllo per salvare la stringa di connessione di entità per il **app** file sia selezionata e prendere nota del valore stringa nella casella di testo, che consentono di individuare la stringa di connessione in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="8f3eb-182">Nella pagina successiva, scegliere **tabelle** e **Stored procedure e funzioni**.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="8f3eb-183">Scegliendo questi nodi di primo livello, si scelgono tutte le tabelle, le stored procedure e le funzioni.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="8f3eb-184">È anche possibile selezionarle individualmente, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="8f3eb-185">Verificare che le caselle di controllo per le altre impostazioni siano selezionate.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="8f3eb-186">Il primo **Rendi plurali o singolari i nomi degli oggetti generati** casella di controllo indica se modificare le forme singolari in plurale per soddisfare le convenzioni di denominazione degli oggetti che rappresentano le tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="8f3eb-187">Il **Includi colonne chiavi esterne nel modello** casella di controllo determina se includere i campi il cui scopo è di unirsi ad altri campi nei tipi di oggetti che vengono generati per lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="8f3eb-188">La terza casella di controllo indica se includere stored procedure e funzioni nel modello.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="8f3eb-189">Selezionare il **fine** pulsante per generare un file con estensione edmx contenente un Entity Data Model basato sul database School.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="8f3eb-190">Un file, **Model1**, viene aggiunto al progetto e verrà visualizzato un diagramma di database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="8f3eb-191">Nella barra dei menu, scegliere **vista**, **altre finestre**, **Browser Entity Data Model** per visualizzare tutti i dettagli del modello o **Dettagli Mapping Entity Data Model**  per aprire una finestra che mostra come il modello a oggetti generato esegue il mapping nelle colonne e tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="8f3eb-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="8f3eb-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8f3eb-192">Next Steps</span></span>
<span data-ttu-id="8f3eb-193">Esplorare altre query esaminando gli operatori di query disponibili elencate in [espressioni di Query](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8f3eb-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8f3eb-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f3eb-194">See Also</span></span>
[<span data-ttu-id="8f3eb-195">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8f3eb-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="8f3eb-196">Provider di tipi EdmxFile</span><span class="sxs-lookup"><span data-stu-id="8f3eb-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

<span data-ttu-id="8f3eb-197">[Walkthrough: Accessing a SQL Database by Using Type Providers and Entities](accessing-a-sql-database-entities.md) (Procedura dettagliata: accesso a un database SQL tramite entità e provider di tipi)</span><span class="sxs-lookup"><span data-stu-id="8f3eb-197">[Walkthrough: Accessing a SQL Database by Using Type Providers and Entities](accessing-a-sql-database-entities.md)</span></span>

[<span data-ttu-id="8f3eb-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8f3eb-198">Entity Framework</span></span>](https://msdn.microsoft.com/data/ef)

[<span data-ttu-id="8f3eb-199">Cenni preliminari sui file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="8f3eb-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="8f3eb-200">Generatore EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="8f3eb-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

