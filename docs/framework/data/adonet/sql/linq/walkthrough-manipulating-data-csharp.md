---
title: 'Procedura dettagliata: modifica dei dati (C#)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ac02ea6c07797c600fe9ce9c7b197a95fc84da61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="2d282-102">Procedura dettagliata: modifica dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="2d282-102">Walkthrough: Manipulating Data (C#)</span></span>
<span data-ttu-id="2d282-103">In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'aggiunta, la modifica e l'eliminazione dei dati in un database.</span><span class="sxs-lookup"><span data-stu-id="2d282-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="2d282-104">Si utilizzerà una copia del database di esempio Northwind per aggiungere un cliente, modificare il nome di un cliente ed eliminare un ordine.</span><span class="sxs-lookup"><span data-stu-id="2d282-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="2d282-105">Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.</span><span class="sxs-lookup"><span data-stu-id="2d282-105">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d282-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2d282-106">Prerequisites</span></span>  
 <span data-ttu-id="2d282-107">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="2d282-107">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="2d282-108">Una cartella dedicata ("c:\linqtest6") in cui inserire i file usati nella procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="2d282-108">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="2d282-109">Creare la cartella prima di avviare la procedura.</span><span class="sxs-lookup"><span data-stu-id="2d282-109">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="2d282-110">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="2d282-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="2d282-111">Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d282-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="2d282-112">Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2d282-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="2d282-113">Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest6.</span><span class="sxs-lookup"><span data-stu-id="2d282-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
-   <span data-ttu-id="2d282-114">Un file di codice C# generato dal database Northwind.</span><span class="sxs-lookup"><span data-stu-id="2d282-114">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="2d282-115">È possibile generare questo file usando [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o lo strumento SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="2d282-115">You can generate this file by using either the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or the SQLMetal tool.</span></span> <span data-ttu-id="2d282-116">Questa procedura dettagliata è stata scritta usando lo strumento SQLMetal con la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2d282-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="2d282-117">**SQLMetal /code:"c:\linqtest6\northwind.cs" c:\ "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="2d282-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="2d282-118">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2d282-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="2d282-119">Panoramica</span><span class="sxs-lookup"><span data-stu-id="2d282-119">Overview</span></span>  
 <span data-ttu-id="2d282-120">La procedura dettagliata è costituita da sei attività principali:</span><span class="sxs-lookup"><span data-stu-id="2d282-120">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="2d282-121">Creazione della soluzione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d282-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="2d282-122">Aggiunta del file di codice del database al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d282-122">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="2d282-123">Creazione di un nuovo oggetto Customer</span><span class="sxs-lookup"><span data-stu-id="2d282-123">Creating a new customer object.</span></span>  
  
-   <span data-ttu-id="2d282-124">Modifica del nome di contatto di un cliente.</span><span class="sxs-lookup"><span data-stu-id="2d282-124">Modifying the contact name of a customer.</span></span>  
  
-   <span data-ttu-id="2d282-125">Eliminazione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="2d282-125">Deleting an order.</span></span>  
  
-   <span data-ttu-id="2d282-126">Invio delle modifiche al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="2d282-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="2d282-127">Creazione di una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2d282-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="2d282-128">In questa prima attività verrà creata una soluzione [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] che contiene i riferimenti necessari per compilare ed eseguire un progetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d282-128">In this first task, you create a [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="2d282-129">Per creare una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2d282-129">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="2d282-130">Nel [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** dal menu **New**, quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="2d282-130">On the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2d282-131">Nel **tipi di progetto** riquadro il **nuovo progetto** la finestra di dialogo, fare clic su **Visual c#**.</span><span class="sxs-lookup"><span data-stu-id="2d282-131">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="2d282-132">Nel riquadro **Modelli** fare clic su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="2d282-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="2d282-133">Nel **nome** digitare **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="2d282-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5.  <span data-ttu-id="2d282-134">Nel **percorso** verificare in cui si desidera archiviare i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2d282-134">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="2d282-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d282-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="2d282-136">Aggiunta di riferimenti e direttive LINQ</span><span class="sxs-lookup"><span data-stu-id="2d282-136">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="2d282-137">In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto.</span><span class="sxs-lookup"><span data-stu-id="2d282-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="2d282-138">Se System.Data.Linq non è elencato come un riferimento nel progetto, aggiungerlo seguendo le indicazioni fornite nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d282-138">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="2d282-139">Per aggiungere System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="2d282-139">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="2d282-140">In **Esplora**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="2d282-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="2d282-141">Nel **Aggiungi riferimento** la finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly LINQ e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d282-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2d282-142">L'assembly verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d282-142">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="2d282-143">Aggiungere le seguenti direttive all'inizio di Program.cs:</span><span class="sxs-lookup"><span data-stu-id="2d282-143">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="2d282-144">Aggiunta del file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="2d282-144">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="2d282-145">In questa procedura si presuppone che sia stato usato lo strumento SQLMetal per generare un file di codice dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="2d282-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="2d282-146">Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="2d282-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="2d282-147">Per aggiungere il file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="2d282-147">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="2d282-148">Nel **progetto** menu, fare clic su **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="2d282-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="2d282-149">Nel **Aggiungi elemento esistente** la finestra di dialogo, passare a c:\linqtest6\northwind.cs e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2d282-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="2d282-150">Il file northwind.cs viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d282-150">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="2d282-151">Impostazione della connessione al database</span><span class="sxs-lookup"><span data-stu-id="2d282-151">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="2d282-152">Eseguire innanzitutto il test della connessione al database.</span><span class="sxs-lookup"><span data-stu-id="2d282-152">First, test your connection to the database.</span></span> <span data-ttu-id="2d282-153">Notare in particolare che nel nome del database, Northwnd, non è presente il carattere i.</span><span class="sxs-lookup"><span data-stu-id="2d282-153">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="2d282-154">Se vengono generati errori nei passaggi successivi, esaminare il file northwind.cs per determinare come è digitata la classe parziale Northwind.</span><span class="sxs-lookup"><span data-stu-id="2d282-154">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="2d282-155">Per impostare e testare la connessione al database</span><span class="sxs-lookup"><span data-stu-id="2d282-155">To set up and test the database connection</span></span>  
  
1.  <span data-ttu-id="2d282-156">Digitare o incollare il codice che segue nel metodo `Main` della classe Program:</span><span class="sxs-lookup"><span data-stu-id="2d282-156">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2.  <span data-ttu-id="2d282-157">A questo punto premere F5 per eseguire il test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d282-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="2d282-158">Oggetto **Console** verrà visualizzata la finestra.</span><span class="sxs-lookup"><span data-stu-id="2d282-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="2d282-159">È possibile chiudere l'applicazione premendo INVIO nel **Console** finestra, oppure facendo clic **Termina debug** sul [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Debug** menu.</span><span class="sxs-lookup"><span data-stu-id="2d282-159">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="2d282-160">Creazione di una nuova entità</span><span class="sxs-lookup"><span data-stu-id="2d282-160">Creating a New Entity</span></span>  
 <span data-ttu-id="2d282-161">La creazione di una nuova entità è un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="2d282-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="2d282-162">È possibile creare oggetti, ad esempio `Customer`, usando la parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="2d282-162">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="2d282-163">In questa e nelle sezioni seguenti vengono apportate modifiche solo alla cache locale.</span><span class="sxs-lookup"><span data-stu-id="2d282-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="2d282-164">Non viene inviata alcuna modifica al database finché, verso la fine di questa procedura dettagliata, non si chiamerà <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d282-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="2d282-165">Per aggiungere un nuovo oggetto dell'entità Customer</span><span class="sxs-lookup"><span data-stu-id="2d282-165">To add a new Customer entity object</span></span>  
  
1.  <span data-ttu-id="2d282-166">Creare un nuovo oggetto `Customer` aggiungendo il codice riportato di seguito prima di `Console.ReadLine();` nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d282-166">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2.  <span data-ttu-id="2d282-167">Premere F5 per eseguire il debug della soluzione.</span><span class="sxs-lookup"><span data-stu-id="2d282-167">Press F5 to debug the solution.</span></span>  
  
3.  <span data-ttu-id="2d282-168">Premere INVIO nella **Console** finestra per arrestare il debug e continuare la procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="2d282-168">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="2d282-169">Aggiornamento di un'entità</span><span class="sxs-lookup"><span data-stu-id="2d282-169">Updating an Entity</span></span>  
 <span data-ttu-id="2d282-170">Nei passaggi seguenti si recupererà un oggetto `Customer` e si modificherà una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d282-170">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="2d282-171">Per modificare il nome di un oggetto Customer</span><span class="sxs-lookup"><span data-stu-id="2d282-171">To change the name of a Customer</span></span>  
  
-   <span data-ttu-id="2d282-172">Aggiungere il codice seguente sopra `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="2d282-172">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="2d282-173">Eliminazione di un'entità</span><span class="sxs-lookup"><span data-stu-id="2d282-173">Deleting an Entity</span></span>  
 <span data-ttu-id="2d282-174">Usando lo stesso oggetto Customer, è possibile eliminare il primo ordine.</span><span class="sxs-lookup"><span data-stu-id="2d282-174">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="2d282-175">Nel codice seguente viene illustrato come interrompere le relazioni tra le righe e come eliminare una riga dal database.</span><span class="sxs-lookup"><span data-stu-id="2d282-175">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="2d282-176">Aggiungere il codice seguente prima di `Console.ReadLine` per vedere come è possibile eliminare oggetti:</span><span class="sxs-lookup"><span data-stu-id="2d282-176">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="2d282-177">Per eliminare una riga</span><span class="sxs-lookup"><span data-stu-id="2d282-177">To delete a row</span></span>  
  
-   <span data-ttu-id="2d282-178">Aggiungere il codice seguente sopra `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="2d282-178">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="2d282-179">Invio di modifiche al database</span><span class="sxs-lookup"><span data-stu-id="2d282-179">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="2d282-180">Il passaggio finale necessario per la creazione, l'aggiornamento e l'eliminazione di oggetti consiste nell'inviare effettivamente le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="2d282-180">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="2d282-181">Senza questo passaggio le modifiche vengono applicate solo localmente e non saranno visualizzate nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="2d282-181">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="2d282-182">Per inviare le modifiche al database</span><span class="sxs-lookup"><span data-stu-id="2d282-182">To submit changes to the database</span></span>  
  
1.  <span data-ttu-id="2d282-183">Inserire il codice seguente sopra `Console.ReadLine`:</span><span class="sxs-lookup"><span data-stu-id="2d282-183">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2.  <span data-ttu-id="2d282-184">Inserire il codice seguente dopo `SubmitChanges` per mostrare gli effetti precedenti e successivi all'invio delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="2d282-184">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3.  <span data-ttu-id="2d282-185">Premere F5 per eseguire il debug della soluzione.</span><span class="sxs-lookup"><span data-stu-id="2d282-185">Press F5 to debug the solution.</span></span>  
  
4.  <span data-ttu-id="2d282-186">Premere INVIO nella **Console** finestra per chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d282-186">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d282-187">Dopo avere aggiunto il nuovo oggetto Customer mediante l'invio delle modifiche, non sarà possibile eseguire nuovamente questa soluzione così com'è.</span><span class="sxs-lookup"><span data-stu-id="2d282-187">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="2d282-188">Per eseguire nuovamente la soluzione, modificare il nome del cliente e l'ID dell'oggetto Customer da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2d282-188">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d282-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d282-189">See Also</span></span>  
 [<span data-ttu-id="2d282-190">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="2d282-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
