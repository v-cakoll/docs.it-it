---
title: "Procedura dettagliata: Accesso a un database SQL tramite entità e provider di tipi (F#)"
description: 'Informazioni su come accedere ai dati tipizzati per un database SQL basato su ADO.NET Entity Data Model in F # 3.0.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="8304a-104">Procedura dettagliata: Accesso a un database SQL tramite entità e provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8304a-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="8304a-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="8304a-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="8304a-106">Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="8304a-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="8304a-107">I collegamenti di riferimento API richiederà a MSDN.</span><span class="sxs-lookup"><span data-stu-id="8304a-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="8304a-108">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="8304a-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="8304a-109">Questa procedura dettagliata per F# 3.0 illustra come accedere ai dati tipizzati per un database SQL basato su ADO.NET Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8304a-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="8304a-110">In questa procedura dettagliata viene illustrato come configurare il provider di tipi `SqlEntityConnection` di F# per l'utilizzo con un database SQL, come scrivere query sui dati, ad esempio stored procedure nel database, e come utilizzare alcuni dei tipi e dei metodi di ADO.NET Entity Framework per aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="8304a-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="8304a-111">In questa procedura dettagliata vengono illustrate le seguenti attività, che è consigliabile eseguire in quest'ordine perché la procedura abbia esito positivo:</span><span class="sxs-lookup"><span data-stu-id="8304a-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="8304a-112">Creare il database School</span><span class="sxs-lookup"><span data-stu-id="8304a-112">Create the School database</span></span>
<br />

- <span data-ttu-id="8304a-113">Creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="8304a-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="8304a-114">Configurare il provider di tipi e connettersi a Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8304a-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="8304a-115">Eseguire query sul database</span><span class="sxs-lookup"><span data-stu-id="8304a-115">Query the database</span></span>
<br />

- <span data-ttu-id="8304a-116">Aggiornamento del database</span><span class="sxs-lookup"><span data-stu-id="8304a-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="8304a-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8304a-117">Prerequisites</span></span>
<span data-ttu-id="8304a-118">Per completare questa procedura, è necessario avere accesso a un server che esegue SQL Server e in cui sia possibile creare un database.</span><span class="sxs-lookup"><span data-stu-id="8304a-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="8304a-119">Creare il database School</span><span class="sxs-lookup"><span data-stu-id="8304a-119">Create the School database</span></span>
<span data-ttu-id="8304a-120">È possibile creare il database School in qualsiasi server che esegue SQL Server a cui si ha accesso come amministratore oppure è possibile utilizzare LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8304a-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="8304a-121">Per creare il database School</span><span class="sxs-lookup"><span data-stu-id="8304a-121">To create the School database</span></span>

1. <span data-ttu-id="8304a-122">In **Esplora Server**, aprire il menu di scelta rapida per il **connessioni dati** nodo, quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="8304a-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="8304a-123">Il **Aggiungi connessione** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8304a-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="8304a-124">Nel **nome Server** casella, specificare il nome di un'istanza di SQL Server a cui si ha accesso amministrativo oppure specificare (localdb\v11.0) se non si dispone di accesso a un server.</span><span class="sxs-lookup"><span data-stu-id="8304a-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="8304a-125">SQL Server Express LocalDB fornisce un server di database semplice per lo sviluppo e il test nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="8304a-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="8304a-126">Per ulteriori informazioni su LocalDB, vedere [procedura dettagliata: creazione di un File di Database locale in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="8304a-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="8304a-127">Viene creato un nuovo nodo **Esplora Server** in **connessioni dati**.</span><span class="sxs-lookup"><span data-stu-id="8304a-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="8304a-128">Aprire il menu di scelta rapida per il nuovo nodo di connessione e quindi scegliere **nuova Query**.</span><span class="sxs-lookup"><span data-stu-id="8304a-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="8304a-129">Aprire [la creazione di Database di esempio School](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) sul sito Web Microsoft e quindi copiare e incollare lo script del database che crea il database School nella finestra dell'editor.</span><span class="sxs-lookup"><span data-stu-id="8304a-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="8304a-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="8304a-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="8304a-131">Creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="8304a-131">Create and configure an F# project</span></span>
<span data-ttu-id="8304a-132">In questo passaggio viene creato un progetto e viene impostato l'utilizzo di un provider di tipi.</span><span class="sxs-lookup"><span data-stu-id="8304a-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="8304a-133">Per creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="8304a-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="8304a-134">Chiudere il progetto precedente, creare un altro progetto e denominarlo **SchoolEDM**.</span><span class="sxs-lookup"><span data-stu-id="8304a-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="8304a-135">In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="8304a-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="8304a-136">Scegliere il **Framework** nodo, quindi il **Framework** scegliere **System. Data**, **System.Data.Entity**e **LINQ**.</span><span class="sxs-lookup"><span data-stu-id="8304a-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="8304a-137">Scegliere il **estensioni** nodo, aggiungere un riferimento al [Typeproviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, quindi scegliere il **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8304a-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="8304a-138">Aggiungere il codice seguente per definire un modulo interno e aprire gli spazi dei nomi appropriati.</span><span class="sxs-lookup"><span data-stu-id="8304a-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="8304a-139">Il provider di tipi può inserire i tipi solo in uno spazio dei nomi privato o interno.</span><span class="sxs-lookup"><span data-stu-id="8304a-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="8304a-140">Per eseguire il codice in questa procedura dettagliata interattivamente come script anziché come un programma compilato, aprire il menu di scelta rapida per il nodo del progetto, scegliere **Aggiungi nuovo elemento**, aggiungere un file di script F # e quindi aggiungere il codice in ogni passaggio allo script.</span><span class="sxs-lookup"><span data-stu-id="8304a-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="8304a-141">Per caricare i riferimenti agli assembly, aggiungere le righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="8304a-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="8304a-142">Evidenziare ogni blocco di codice mentre lo si aggiunge e premere ALT+INVIO per eseguirlo in F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="8304a-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="8304a-143">Configurare il provider di tipi e connettersi a Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8304a-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="8304a-144">In questo passaggio si installa un provider di tipi con una connessione dati e si ottiene un contesto dati che consente di utilizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="8304a-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="8304a-145">Per configurare il provider di tipi e connettersi a Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8304a-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="8304a-146">Digitare il codice seguente per configurare il provider di tipi `SqlEntityConnection` che genera i tipi F# basati su Entity Data Model creato precedentemente.</span><span class="sxs-lookup"><span data-stu-id="8304a-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="8304a-147">Anziché la stringa di connessione EDMX completa utilizzare solo la stringa di connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="8304a-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="8304a-148">Questa azione installa un provider di tipi con la connessione al database creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="8304a-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="8304a-149">La proprietà `MultipleActiveResultSets` è necessaria quando si utilizza ADO.NET Entity Framework poiché questa proprietà consente di eseguire più controlli in modo asincrono nel database in una connessione, cosa che può verificarsi frequentemente nel codice ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8304a-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="8304a-150">Per altre informazioni, vedere [MARS (Multiple Active Result Sets)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span><span class="sxs-lookup"><span data-stu-id="8304a-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="8304a-151">Ottenere il contesto dei dati, un oggetto contenente le tabelle del database come proprietà e le stored procedure e le funzioni del database come metodi.</span><span class="sxs-lookup"><span data-stu-id="8304a-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="8304a-152">Esecuzione di query nel database</span><span class="sxs-lookup"><span data-stu-id="8304a-152">Querying the database</span></span>
<span data-ttu-id="8304a-153">In questo passaggio si utilizzano le espressioni di query F# per eseguire varie query sul database.</span><span class="sxs-lookup"><span data-stu-id="8304a-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="8304a-154">Per eseguire una query sui dati</span><span class="sxs-lookup"><span data-stu-id="8304a-154">To query the data</span></span>

- <span data-ttu-id="8304a-155">Digitare il codice seguente per analizzare i dati provenienti da Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8304a-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="8304a-156">Notare l'effetto Pluralize = true che modifica la tabella del database Course in Courses e la tabella Person in People.</span><span class="sxs-lookup"><span data-stu-id="8304a-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="8304a-157">Aggiornamento del database</span><span class="sxs-lookup"><span data-stu-id="8304a-157">Updating the database</span></span>
<span data-ttu-id="8304a-158">Per aggiornare il database, utilizzare le classi e i metodi di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8304a-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="8304a-159">È possibile utilizzare due tipi di contesti dei dati con il provider di tipi SQLEntityConnection.</span><span class="sxs-lookup"><span data-stu-id="8304a-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="8304a-160">Innanzitutto, `ServiceTypes.SimpleDataContextTypes.EntityContainer` è il contesto dei dati semplificato, che include solo le proprietà specificate che rappresentano le tabelle e le colonne del database.</span><span class="sxs-lookup"><span data-stu-id="8304a-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="8304a-161">In secondo luogo, il contesto dei dati completo è un'istanza della classe Entity Framework `System.Data.Objects.ObjectContext`, che contiene il metodo `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` per aggiungere righe al database.</span><span class="sxs-lookup"><span data-stu-id="8304a-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="8304a-162">Entity Framework riconosce le tabelle e le relazioni tra di esse, pertanto rafforza la coerenza tra database.</span><span class="sxs-lookup"><span data-stu-id="8304a-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="8304a-163">Per aggiornare il database</span><span class="sxs-lookup"><span data-stu-id="8304a-163">To update the database</span></span>

1. <span data-ttu-id="8304a-164">Aggiungere il seguente codice al programma:</span><span class="sxs-lookup"><span data-stu-id="8304a-164">Add the following code to your program.</span></span> <span data-ttu-id="8304a-165">In questo esempio aggiungere due oggetti con una relazione tra di essi e aggiungere un docente e l'assegnazione dell'ufficio.</span><span class="sxs-lookup"><span data-stu-id="8304a-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="8304a-166">La tabella `OfficeAssignments` contiene la colonna `InstructorID` che fa riferimento alla colonna `PersonID` nella tabella `Person`.</span><span class="sxs-lookup"><span data-stu-id="8304a-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="8304a-167">Non viene apportata alcuna modifica al database finché non viene chiamato `System.Data.Objects.ObjectContext.SaveChanges`.</span><span class="sxs-lookup"><span data-stu-id="8304a-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="8304a-168">A questo punto ripristinare il database allo stato iniziale eliminando gli oggetti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="8304a-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="8304a-169">Quando si utilizza un'espressione di query, è necessario ricordare che la query è soggetta alla valutazione differita.</span><span class="sxs-lookup"><span data-stu-id="8304a-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="8304a-170">Pertanto, il database è ancora aperto per la lettura di tutte le valutazioni concatenate, come nei blocchi di espressione lambda dopo ogni espressione di query.</span><span class="sxs-lookup"><span data-stu-id="8304a-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="8304a-171">Qualsiasi operazione di database che in modo esplicito o implicito utilizza una transazione deve avvenire dopo che le operazioni di lettura sono state completate.</span><span class="sxs-lookup"><span data-stu-id="8304a-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="8304a-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8304a-172">Next Steps</span></span>
<span data-ttu-id="8304a-173">Esaminare altre opzioni di query prendendo in considerazione gli operatori di query disponibili nella [espressioni di Query](../../language-reference/query-expressions.md)ed esaminare anche il [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) per comprendere quali funzionalità sono disponibili quando Utilizzare questo tipo provider.</span><span class="sxs-lookup"><span data-stu-id="8304a-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="8304a-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8304a-174">See Also</span></span>
[<span data-ttu-id="8304a-175">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="8304a-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="8304a-176">Provider di tipi SqlEntityConnection</span><span class="sxs-lookup"><span data-stu-id="8304a-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="8304a-177">Procedura dettagliata: Generazione di tipi F # da un File di Schema EDMX</span><span class="sxs-lookup"><span data-stu-id="8304a-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="8304a-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8304a-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="8304a-179">Cenni preliminari sui file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="8304a-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="8304a-180">Generatore EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="8304a-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
