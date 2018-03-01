---
title: 'Procedura dettagliata: generazione di tipi F# da un file DBML (F#)'
description: 'Informazioni su come creare tipi F # per i dati da un database in F # 3.0 quando si dispone di informazioni sullo schema con codificate in un file. dbml.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="11397-104">Procedura dettagliata: generazione di tipi F# da un file DBML</span><span class="sxs-lookup"><span data-stu-id="11397-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="11397-105">Questa guida è stata scritta per F # 3.0 e verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="11397-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="11397-106">Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="11397-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="11397-107">I collegamenti di riferimento API richiederà a MSDN.</span><span class="sxs-lookup"><span data-stu-id="11397-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="11397-108">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="11397-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="11397-109">Questa procedura dettagliata per F # 3.0 viene descritto come creare tipi di dati da un database quando si dispone di informazioni sullo schema con codificate in un file. dbml.</span><span class="sxs-lookup"><span data-stu-id="11397-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="11397-110">LINQ to SQL Usa questo formato di file per rappresentare lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="11397-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="11397-111">È possibile generare un file LINQ to SQL dello schema in Visual Studio utilizzando la finestra di Progettazione relazionale oggetti (O/R).</span><span class="sxs-lookup"><span data-stu-id="11397-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="11397-112">Per ulteriori informazioni, vedere [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) e [generazione di codice in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="11397-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>

<span data-ttu-id="11397-113">Il provider di tipi di Database Markup Language (DBML) consente di scrivere codice che usa i tipi basati su uno schema di database senza che sia necessario specificare una stringa di connessione statica in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="11397-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="11397-114">Che può essere utile se è necessario consentire la possibilità che l'applicazione finale utilizzerà un database diverso, credenziali diverse o una stringa di connessione diverso da quello utilizzato per sviluppare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="11397-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="11397-115">Se si dispone di una connessione diretta del database che è possibile utilizzare in fase di compilazione e questo è lo stesso database e le credenziali che verranno usati nell'applicazione compilata, è inoltre possibile utilizzare il provider di tipi SQLDataConnection.</span><span class="sxs-lookup"><span data-stu-id="11397-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="11397-116">Per ulteriori informazioni, vedere [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="11397-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="11397-117">In questa procedura dettagliata vengono illustrate le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="11397-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="11397-118">È necessario completare in quest'ordine perché la procedura abbia esito positivo:</span><span class="sxs-lookup"><span data-stu-id="11397-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="11397-119">Creazione di un file con estensione dbml</span><span class="sxs-lookup"><span data-stu-id="11397-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="11397-120">Creazione e configurazione di un progetto F #</span><span class="sxs-lookup"><span data-stu-id="11397-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="11397-121">Configurazione del provider di tipo e la generazione di tipi</span><span class="sxs-lookup"><span data-stu-id="11397-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="11397-122">Esecuzione di query nel database</span><span class="sxs-lookup"><span data-stu-id="11397-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="11397-123">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="11397-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="11397-124">Creazione di un file con estensione dbml</span><span class="sxs-lookup"><span data-stu-id="11397-124">Creating a .dbml file</span></span>
<span data-ttu-id="11397-125">Se non si dispone di un database, eseguire i test su, crearne una seguendo le istruzioni riportate in fondo [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="11397-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="11397-126">Se si seguono queste istruzioni, si creerà un database denominato MyDatabase contenente alcuni semplici tabelle e stored procedure in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11397-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="11397-127">Se si dispone già di un file. dbml, è possibile ignorare la sezione **creare e impostare backup di un progetto F #**.</span><span class="sxs-lookup"><span data-stu-id="11397-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="11397-128">In caso contrario, è possibile creare un file con estensione dbml assegnato a un database SQL esistente e tramite la riga di comando dello strumento SqlMetal.exe.</span><span class="sxs-lookup"><span data-stu-id="11397-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="11397-129">Per creare un file con estensione dbml usando SqlMetal.exe</span><span class="sxs-lookup"><span data-stu-id="11397-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="11397-130">Aprire un **prompt dei comandi per sviluppatori**.</span><span class="sxs-lookup"><span data-stu-id="11397-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="11397-131">Assicurarsi di disporre dell'accesso a SqlMetal.exe immettendo `SqlMetal.exe /?` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="11397-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="11397-132">SqlMetal.exe viene in genere installato nel **SDKs** cartella **programmi** o **programmi (x86)**.</span><span class="sxs-lookup"><span data-stu-id="11397-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="11397-133">Eseguire SqlMetal.exe con le seguenti opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="11397-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="11397-134">Sostituire con un percorso appropriato al posto di `c:\destpath` per creare il file con estensione dbml e inserire i valori appropriati per il server di database, istanza, nome e il nome di database.</span><span class="sxs-lookup"><span data-stu-id="11397-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="11397-135">Se SqlMetal.exe dispone di un problema durante la creazione del file a causa di problemi relativi alle autorizzazioni, è possibile modificare la directory corrente in una cartella che si dispone di accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="11397-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="11397-136">È anche possibile esaminare le altre opzioni della riga di comando disponibili.</span><span class="sxs-lookup"><span data-stu-id="11397-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="11397-137">Ad esempio, sono disponibili opzioni che è possibile utilizzare se si desidera viste e funzioni SQL incluse con i tipi generati.</span><span class="sxs-lookup"><span data-stu-id="11397-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="11397-138">Per ulteriori informazioni, vedere [SqlMetal.exe &#40; Lo strumento di generazione di codice &#41; ](https://msdn.microsoft.com/library/bb386987).</span><span class="sxs-lookup"><span data-stu-id="11397-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="11397-139">Creazione e configurazione di un progetto F #</span><span class="sxs-lookup"><span data-stu-id="11397-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="11397-140">In questo passaggio si crea un progetto e aggiungere i riferimenti appropriati per utilizzare il provider di tipi DBML.</span><span class="sxs-lookup"><span data-stu-id="11397-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="11397-141">Per creare e configurare un progetto F#</span><span class="sxs-lookup"><span data-stu-id="11397-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="11397-142">Aggiungere un nuovo progetto applicazione Console c# alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="11397-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="11397-143">In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="11397-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="11397-144">Nel **assembly** area, scegliere il **Framework** nodo, quindi nell'elenco di assembly disponibili, scegliere il **System. Data** e **LINQ**  assembly.</span><span class="sxs-lookup"><span data-stu-id="11397-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="11397-145">Nel **assembly** area scegliere **estensioni**, quindi nell'elenco di assembly disponibili, scegliere **Typeproviders**.</span><span class="sxs-lookup"><span data-stu-id="11397-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="11397-146">Scegliere il **OK** pulsante per aggiungere riferimenti a questi assembly al progetto.</span><span class="sxs-lookup"><span data-stu-id="11397-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="11397-147">(Facoltativo)</span><span class="sxs-lookup"><span data-stu-id="11397-147">(Optional).</span></span> <span data-ttu-id="11397-148">Copiare il file con estensione dbml creato nel passaggio precedente e incollare il file nella cartella principale per il progetto.</span><span class="sxs-lookup"><span data-stu-id="11397-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="11397-149">Questa cartella contiene file di progetto (con estensione fsproj) e i file di codice.</span><span class="sxs-lookup"><span data-stu-id="11397-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="11397-150">Nella barra dei menu, scegliere **progetto**, **Aggiungi elemento esistente**e quindi specificare il file dbml per aggiungerlo al progetto.</span><span class="sxs-lookup"><span data-stu-id="11397-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="11397-151">Dopo aver completato questi passaggi, è possibile omettere il parametro static ResolutionFolder nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="11397-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="11397-152">Configurazione del provider di tipi</span><span class="sxs-lookup"><span data-stu-id="11397-152">Configuring the type provider</span></span>
<span data-ttu-id="11397-153">In questa sezione, creare un provider di tipi e generare tipi dallo schema descritto nel file. dbml.</span><span class="sxs-lookup"><span data-stu-id="11397-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="11397-154">Per configurare il provider di tipi e generare i tipi</span><span class="sxs-lookup"><span data-stu-id="11397-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="11397-155">Aggiungere il codice che apre il **TypeProviders** dello spazio dei nomi e crea il provider di tipi per il file dbml che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="11397-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="11397-156">Se il file. dbml aggiunto al progetto, è possibile omettere il parametro static ResolutionFolder.</span><span class="sxs-lookup"><span data-stu-id="11397-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="11397-157">Il tipo DataContext fornisce l'accesso a tutti i tipi generati ed eredita da `System.Data.Linq.DataContext`.</span><span class="sxs-lookup"><span data-stu-id="11397-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="11397-158">Il provider di tipi DbmlFile ha diversi parametri statici che è possibile impostare.</span><span class="sxs-lookup"><span data-stu-id="11397-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="11397-159">Ad esempio, è possibile utilizzare un nome diverso per il tipo DataContext specificando `DataContext=MyDataContext`.</span><span class="sxs-lookup"><span data-stu-id="11397-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="11397-160">In tal caso, il codice analogo all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="11397-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="11397-161">Esecuzione di query nel database</span><span class="sxs-lookup"><span data-stu-id="11397-161">Querying the database</span></span>
<span data-ttu-id="11397-162">In questa sezione, utilizzare le espressioni di query F # per eseguire query sul database.</span><span class="sxs-lookup"><span data-stu-id="11397-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="11397-163">Per eseguire una query sui dati</span><span class="sxs-lookup"><span data-stu-id="11397-163">To query the data</span></span>

- <span data-ttu-id="11397-164">Aggiungere il codice per eseguire query sul database.</span><span class="sxs-lookup"><span data-stu-id="11397-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="11397-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="11397-165">Next Steps</span></span>
<span data-ttu-id="11397-166">È possibile utilizzare altre espressioni di query, o ottenere una connessione al database del contesto dei dati e di eseguire le normali operazioni di dati ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="11397-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="11397-167">Per i passaggi aggiuntivi, vedere le sezioni dopo "Query dei dati" in [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="11397-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="11397-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11397-168">See Also</span></span>
[<span data-ttu-id="11397-169">Provider di tipi DbmlFile</span><span class="sxs-lookup"><span data-stu-id="11397-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="11397-170">Provider di tipi</span><span class="sxs-lookup"><span data-stu-id="11397-170">Type Providers</span></span>](index.md)

<span data-ttu-id="11397-171">[Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md) (Procedura dettagliata: accesso a un database SQL tramite provider di tipi)</span><span class="sxs-lookup"><span data-stu-id="11397-171">[Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md)</span></span>

[<span data-ttu-id="11397-172">SqlMetal.exe &#40; Lo strumento di generazione di codice &#41;</span><span class="sxs-lookup"><span data-stu-id="11397-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="11397-173">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="11397-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
