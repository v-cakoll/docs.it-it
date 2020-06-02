---
title: "Procedura dettagliata: uso di BatchBlock e BatchedJoinBlock per migliorare l'efficienza"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: e572c5a14958ccc069ae7649af8c8ed4eb967dc1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284585"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="127a9-102">Procedura dettagliata: uso di BatchBlock e BatchedJoinBlock per migliorare l'efficienza</span><span class="sxs-lookup"><span data-stu-id="127a9-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>

<span data-ttu-id="127a9-103">La libreria del flusso di dati TPL fornisce le classi <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> che consentono di ricevere e memorizzare nel buffer i dati di una o più origini e quindi propagare tali dati come unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="127a9-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="127a9-104">Questo meccanismo di invio in batch è utile quando si raccolgono dati da una o più origini e quindi si elaborano più elementi dati come batch.</span><span class="sxs-lookup"><span data-stu-id="127a9-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="127a9-105">Ad esempio, si consideri un'applicazione che usa un flusso di dati per inserire record in un database.</span><span class="sxs-lookup"><span data-stu-id="127a9-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="127a9-106">Questa operazione può essere più efficiente se nello stesso momento vengono inseriti più elementi anziché uno alla volta, in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="127a9-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="127a9-107">Questo documento descrive come usare la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> per migliorare l'efficienza di tali operazioni di inserimento nel database.</span><span class="sxs-lookup"><span data-stu-id="127a9-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="127a9-108">Descrive anche come usare la classe <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> per acquisire sia i risultati che le eventuali eccezioni che si verificano durante la lettura da database da parte del programma.</span><span class="sxs-lookup"><span data-stu-id="127a9-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a><span data-ttu-id="127a9-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="127a9-109">Prerequisites</span></span>

1. <span data-ttu-id="127a9-110">Prima di iniziare questa procedura dettagliata, leggere la sezione sui blocchi join nel documento [Flusso di dati](dataflow-task-parallel-library.md).</span><span class="sxs-lookup"><span data-stu-id="127a9-110">Read the Join Blocks section in the [Dataflow](dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>

2. <span data-ttu-id="127a9-111">Verificare di avere una copia del database Northwind, Northwind.sdf, disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="127a9-111">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="127a9-112">Questo file si trova in genere nella cartella %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span><span class="sxs-lookup"><span data-stu-id="127a9-112">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="127a9-113">In alcune versioni di Windows non è possibile connettersi a Northwind.sdf se Visual Studio è in esecuzione in modalità senza privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="127a9-113">In some versions of Windows, you cannot connect to Northwind.sdf if Visual Studio is running in a non-administrator mode.</span></span> <span data-ttu-id="127a9-114">Per connettersi a Northwind.sdf, avviare Visual Studio o un Prompt dei comandi per gli sviluppatori per Visual Studio in modalità **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="127a9-114">To connect to Northwind.sdf, start Visual Studio or a Developer Command Prompt for Visual Studio in the **Run as administrator** mode.</span></span>

<span data-ttu-id="127a9-115">Questa procedura dettagliata contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="127a9-115">This walkthrough contains the following sections:</span></span>

- [<span data-ttu-id="127a9-116">Creazione dell'applicazione console</span><span class="sxs-lookup"><span data-stu-id="127a9-116">Creating the Console Application</span></span>](#creating)

- [<span data-ttu-id="127a9-117">Definizione della classe Employee</span><span class="sxs-lookup"><span data-stu-id="127a9-117">Defining the Employee Class</span></span>](#employeeClass)

- [<span data-ttu-id="127a9-118">Definizione delle operazioni dei dipendenti sul database</span><span class="sxs-lookup"><span data-stu-id="127a9-118">Defining Employee Database Operations</span></span>](#operations)

- [<span data-ttu-id="127a9-119">Aggiunta di dati dei dipendenti al database senza usare la memorizzazione nel buffer</span><span class="sxs-lookup"><span data-stu-id="127a9-119">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)

- [<span data-ttu-id="127a9-120">Uso della memorizzazione nel buffer per aggiungere dati dei dipendenti nel database</span><span class="sxs-lookup"><span data-stu-id="127a9-120">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)

- [<span data-ttu-id="127a9-121">Uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database</span><span class="sxs-lookup"><span data-stu-id="127a9-121">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)

- [<span data-ttu-id="127a9-122">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="127a9-122">The Complete Example</span></span>](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a><span data-ttu-id="127a9-123">Creazione dell'applicazione console</span><span class="sxs-lookup"><span data-stu-id="127a9-123">Creating the Console Application</span></span>

1. <span data-ttu-id="127a9-124">In Visual Studio creare un progetto di **applicazione console** di Visual C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="127a9-124">In Visual Studio, create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="127a9-125">In questo documento, il progetto viene denominato `DataflowBatchDatabase`.</span><span class="sxs-lookup"><span data-stu-id="127a9-125">In this document, the project is named `DataflowBatchDatabase`.</span></span>

2. <span data-ttu-id="127a9-126">Nel progetto aggiungere un riferimento a System.Data.SqlServerCe.dll e un riferimento a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="127a9-126">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>

3. <span data-ttu-id="127a9-127">Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="127a9-127">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` (`Imports` in Visual Basic) statements.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. <span data-ttu-id="127a9-128">Aggiungere i membri dei dati seguenti alla classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="127a9-128">Add the following data members to the `Program` class.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a><span data-ttu-id="127a9-129">Definizione della classe Employee</span><span class="sxs-lookup"><span data-stu-id="127a9-129">Defining the Employee Class</span></span>

<span data-ttu-id="127a9-130">Aggiungere alla classe `Program` la classe `Employee`.</span><span class="sxs-lookup"><span data-stu-id="127a9-130">Add to the `Program` class the `Employee` class.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

<span data-ttu-id="127a9-131">La classe `Employee` contiene tre proprietà, `EmployeeID`, `LastName` e `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="127a9-131">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="127a9-132">Queste proprietà corrispondono alle colonne `Employee ID`, `Last Name` e `First Name` nella tabella `Employees` del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="127a9-132">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="127a9-133">Per questa dimostrazione, la classe `Employee` definisce anche il metodo `Random`, che crea un oggetto `Employee` con valori casuali per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="127a9-133">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a><span data-ttu-id="127a9-134">Definizione delle operazioni dei dipendenti sul database</span><span class="sxs-lookup"><span data-stu-id="127a9-134">Defining Employee Database Operations</span></span>

<span data-ttu-id="127a9-135">Aggiungere alla classe `Program` i metodi `InsertEmployees`, `GetEmployeeCount` e `GetEmployeeID`.</span><span class="sxs-lookup"><span data-stu-id="127a9-135">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

<span data-ttu-id="127a9-136">Il metodo `InsertEmployees` aggiunge nuovi record di dipendenti nel database.</span><span class="sxs-lookup"><span data-stu-id="127a9-136">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="127a9-137">Il metodo `GetEmployeeCount` recupera il numero di voci nella tabella `Employees`.</span><span class="sxs-lookup"><span data-stu-id="127a9-137">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="127a9-138">Il metodo `GetEmployeeID` recupera l'identificatore del primo dipendente con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="127a9-138">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="127a9-139">Ognuno di questi metodi accetta una stringa di connessione al database Northwind e usa la funzionalità nello spazio dei nomi `System.Data.SqlServerCe` per comunicare con il database.</span><span class="sxs-lookup"><span data-stu-id="127a9-139">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="127a9-140">Aggiunta di dati dei dipendenti al database senza usare la memorizzazione nel buffer</span><span class="sxs-lookup"><span data-stu-id="127a9-140">Adding Employee Data to the Database Without Using Buffering</span></span>

<span data-ttu-id="127a9-141">Aggiungere alla classe `Program` i metodi `AddEmployees` e `PostRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="127a9-141">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

<span data-ttu-id="127a9-142">Il metodo `AddEmployees` aggiunge dati di dipendenti casuali al database usando un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="127a9-142">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="127a9-143">Crea un oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> che chiama il metodo `InsertEmployees` per aggiungere una voce di dipendente al database.</span><span class="sxs-lookup"><span data-stu-id="127a9-143">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="127a9-144">Il metodo `AddEmployees` chiama quindi il metodo `PostRandomEmployees` per registrare più oggetti `Employee` nell'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="127a9-144">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="127a9-145">Il metodo `AddEmployees` attende quindi il completamento di tutte le operazioni di inserimento.</span><span class="sxs-lookup"><span data-stu-id="127a9-145">The `AddEmployees` method then waits for all insert operations to finish.</span></span>

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="127a9-146">Uso della memorizzazione nel buffer per aggiungere dati dei dipendenti nel database</span><span class="sxs-lookup"><span data-stu-id="127a9-146">Using Buffering to Add Employee Data to the Database</span></span>

<span data-ttu-id="127a9-147">Aggiungere alla classe `Program` il metodo `AddEmployeesBatched`.</span><span class="sxs-lookup"><span data-stu-id="127a9-147">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

<span data-ttu-id="127a9-148">Questo metodo è simile ad `AddEmployees`, ad eccezione del fatto che usa anche la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> per memorizzare nel buffer più oggetti `Employee` prima di inviare questi ultimi all'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="127a9-148">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="127a9-149">Poiché la classe <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> propaga più elementi come raccolta, l'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> viene modificato in modo da operare su una matrice di oggetti `Employee`.</span><span class="sxs-lookup"><span data-stu-id="127a9-149">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="127a9-150">Come nel metodo `AddEmployees`, `AddEmployeesBatched` chiama il metodo `PostRandomEmployees` per registrare più oggetti `Employee`. `AddEmployeesBatched` tuttavia invia questi oggetti nell'oggetto <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="127a9-150">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="127a9-151">Il metodo `AddEmployeesBatched` attende anche il completamento di tutte le operazioni di inserimento.</span><span class="sxs-lookup"><span data-stu-id="127a9-151">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="127a9-152">Uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database</span><span class="sxs-lookup"><span data-stu-id="127a9-152">Using Buffered Join to Read Employee Data from the Database</span></span>

<span data-ttu-id="127a9-153">Aggiungere alla classe `Program` il metodo `GetRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="127a9-153">Add to the `Program` class the `GetRandomEmployees` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

<span data-ttu-id="127a9-154">Questo metodo visualizza informazioni su dipendenti casuali nella console.</span><span class="sxs-lookup"><span data-stu-id="127a9-154">This method prints information about random employees to the console.</span></span> <span data-ttu-id="127a9-155">Crea diversi oggetti `Employee` casuali e chiama il metodo `GetEmployeeID` per recuperare l'identificatore univoco per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="127a9-155">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="127a9-156">Poiché il metodo `GetEmployeeID` genera un'eccezione se non esiste alcun dipendente corrispondenti al nome e al cognome specificati, il metodo `GetRandomEmployees` usa la classe <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> per archiviare oggetti `Employee` per le chiamate a `GetEmployeeID` con esito positivo e oggetti <xref:System.Exception?displayProperty=nameWithType> per le chiamate con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="127a9-156">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="127a9-157">L'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> in questo esempio opera su un oggetto <xref:System.Tuple%602> contenente un elenco di oggetti `Employee` e un elenco di oggetti <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="127a9-157">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="127a9-158">L'oggetto <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> propaga questi dati quando la somma del numero degli oggetti `Employee` e <xref:System.Exception> ricevuti è uguale alla dimensione del batch.</span><span class="sxs-lookup"><span data-stu-id="127a9-158">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>

<a name="complete"></a>

## <a name="the-complete-example"></a><span data-ttu-id="127a9-159">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="127a9-159">The Complete Example</span></span>

<span data-ttu-id="127a9-160">L'esempio seguente mostra il codice completo.</span><span class="sxs-lookup"><span data-stu-id="127a9-160">The following example shows the complete code.</span></span> <span data-ttu-id="127a9-161">Il metodo `Main` confronta il tempo necessario per eseguire operazioni di inserimento in batch nel database rispetto al tempo necessario per eseguire operazioni di inserimento non in batch nel database stesso.</span><span class="sxs-lookup"><span data-stu-id="127a9-161">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="127a9-162">Viene anche illustrato l'uso di un join memorizzato nel buffer per leggere dati dei dipendenti dal database e anche segnalare eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="127a9-162">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a><span data-ttu-id="127a9-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127a9-163">See also</span></span>

- [<span data-ttu-id="127a9-164">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="127a9-164">Dataflow</span></span>](dataflow-task-parallel-library.md)
