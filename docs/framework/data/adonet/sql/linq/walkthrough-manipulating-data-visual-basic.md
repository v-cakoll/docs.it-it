---
title: 'Procedura dettagliata: Modifica dei dati (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: 9e6039feb68d18ff5ce16b7a0532710d672c296e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946956"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="75279-102">Procedura dettagliata: Modifica dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75279-102">Walkthrough: Manipulating Data (Visual Basic)</span></span>
<span data-ttu-id="75279-103">In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'aggiunta, la modifica e l'eliminazione dei dati in un database.</span><span class="sxs-lookup"><span data-stu-id="75279-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="75279-104">Si utilizzerà una copia del database di esempio Northwind per aggiungere un cliente, modificare il nome di un cliente ed eliminare un ordine.</span><span class="sxs-lookup"><span data-stu-id="75279-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="75279-105">Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="75279-105">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="75279-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="75279-106">Prerequisites</span></span>  
 <span data-ttu-id="75279-107">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="75279-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="75279-108">Una cartella dedicata ("c:\linqtest2") in cui inserire i file usati nella procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="75279-108">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="75279-109">Creare la cartella prima di avviare la procedura.</span><span class="sxs-lookup"><span data-stu-id="75279-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="75279-110">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="75279-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="75279-111">Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75279-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="75279-112">Per istruzioni, vedere [download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="75279-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="75279-113">Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest2.</span><span class="sxs-lookup"><span data-stu-id="75279-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
- <span data-ttu-id="75279-114">Un file di codice Visual Basic generato dal database Northwind.</span><span class="sxs-lookup"><span data-stu-id="75279-114">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="75279-115">È possibile generare questo file usando il Object Relational Designer o lo strumento SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="75279-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="75279-116">Questa procedura dettagliata è stata scritta usando lo strumento SQLMetal con la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="75279-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="75279-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="75279-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="75279-118">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="75279-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="75279-119">Panoramica</span><span class="sxs-lookup"><span data-stu-id="75279-119">Overview</span></span>  
 <span data-ttu-id="75279-120">La procedura dettagliata è costituita da sei attività principali:</span><span class="sxs-lookup"><span data-stu-id="75279-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="75279-121">Creazione della [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75279-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="75279-122">Aggiunta del file di codice del database al progetto.</span><span class="sxs-lookup"><span data-stu-id="75279-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="75279-123">Creazione di un nuovo oggetto Customer</span><span class="sxs-lookup"><span data-stu-id="75279-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="75279-124">Modifica del nome di contatto di un cliente.</span><span class="sxs-lookup"><span data-stu-id="75279-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="75279-125">Eliminazione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="75279-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="75279-126">Invio delle modifiche al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="75279-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="75279-127">Creazione di una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="75279-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="75279-128">In questa prima attività viene creata una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="75279-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="75279-129">Per creare una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="75279-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="75279-130">Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75279-130">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="75279-131">Nel riquadro **Tipi progetto** della finestra di dialogo **nuovo progetto** fare clic su **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="75279-131">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="75279-132">Nel riquadro **Modelli** fare clic su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="75279-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="75279-133">Nella casella **nome** digitare **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="75279-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="75279-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="75279-134">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="75279-135">Aggiunta di riferimenti e direttive LINQ</span><span class="sxs-lookup"><span data-stu-id="75279-135">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="75279-136">In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto.</span><span class="sxs-lookup"><span data-stu-id="75279-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="75279-137">Se `System.Data.Linq` non è elencato come riferimento nel progetto (fare clic su **Mostra tutti i file** in **Esplora soluzioni** ed espandere il nodo **riferimenti** ), aggiungerlo, come illustrato nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="75279-137">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="75279-138">Per aggiungere System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="75279-138">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="75279-139">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **riferimenti**, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="75279-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="75279-140">Nella finestra di dialogo **Aggiungi riferimento** fare clic su **.NET**, selezionare l'assembly System. Data. Linq, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="75279-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="75279-141">L'assembly verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="75279-141">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="75279-142">Nell'editor di codice aggiungere le direttive seguenti sopra **Module1**:</span><span class="sxs-lookup"><span data-stu-id="75279-142">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="75279-143">Aggiunta del file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="75279-143">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="75279-144">In questa procedura si presuppone che sia stato usato lo strumento SQLMetal per generare un file di codice dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="75279-144">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="75279-145">Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="75279-145">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="75279-146">Per aggiungere il file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="75279-146">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="75279-147">Scegliere **Aggiungi elemento esistente**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="75279-147">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="75279-148">Nella finestra di dialogo **Aggiungi elemento esistente** passare a c:\linqtest2\northwind.vb e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="75279-148">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="75279-149">Il file northwind.vb viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="75279-149">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="75279-150">Impostazione della connessione al database</span><span class="sxs-lookup"><span data-stu-id="75279-150">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="75279-151">Eseguire innanzitutto il test della connessione al database.</span><span class="sxs-lookup"><span data-stu-id="75279-151">First, test your connection to the database.</span></span> <span data-ttu-id="75279-152">Notare in particolare che nel nome del database, Northwnd, non è presente il carattere i.</span><span class="sxs-lookup"><span data-stu-id="75279-152">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="75279-153">Se vengono generati errori nei passaggi successivi, esaminare il file northwind.vb per determinare come è digitata la classe parziale Northwind.</span><span class="sxs-lookup"><span data-stu-id="75279-153">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="75279-154">Per impostare e testare la connessione al database</span><span class="sxs-lookup"><span data-stu-id="75279-154">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="75279-155">Digitare o incollare il codice che segue in `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="75279-155">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. <span data-ttu-id="75279-156">A questo punto premere F5 per eseguire il test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75279-156">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="75279-157">Viene visualizzata una finestra della **console** .</span><span class="sxs-lookup"><span data-stu-id="75279-157">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="75279-158">Chiudere l'applicazione premendo INVIO nella finestra della **console** oppure facendo clic su **Interrompi debug** nel menu **debug** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75279-158">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="75279-159">Creazione di una nuova entità</span><span class="sxs-lookup"><span data-stu-id="75279-159">Creating a New Entity</span></span>  
 <span data-ttu-id="75279-160">La creazione di una nuova entità è un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="75279-160">Creating a new entity is straightforward.</span></span> <span data-ttu-id="75279-161">È possibile creare oggetti, ad esempio `Customer`, usando la parola chiave `New`.</span><span class="sxs-lookup"><span data-stu-id="75279-161">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="75279-162">In questa e nelle sezioni seguenti vengono apportate modifiche solo alla cache locale.</span><span class="sxs-lookup"><span data-stu-id="75279-162">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="75279-163">Non viene inviata alcuna modifica al database finché, verso la fine di questa procedura dettagliata, non si chiamerà <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="75279-163">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="75279-164">Per aggiungere un nuovo oggetto dell'entità Customer</span><span class="sxs-lookup"><span data-stu-id="75279-164">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="75279-165">Creare un nuovo oggetto `Customer` aggiungendo il codice riportato di seguito prima di `Console.ReadLine` in `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="75279-165">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="75279-166">Premere F5 per eseguire il debug della soluzione.</span><span class="sxs-lookup"><span data-stu-id="75279-166">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="75279-167">Di seguito sono riportati i risultati visualizzati nella finestra della console:</span><span class="sxs-lookup"><span data-stu-id="75279-167">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="75279-168">Notare che la nuova riga non è visualizzata nei risultati.</span><span class="sxs-lookup"><span data-stu-id="75279-168">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="75279-169">I nuovi dati non sono ancora stati inviati al database.</span><span class="sxs-lookup"><span data-stu-id="75279-169">The new data has not yet been submitted to the database.</span></span>  
  
3. <span data-ttu-id="75279-170">Premere INVIO nella finestra della **console** per arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="75279-170">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="75279-171">Aggiornamento di un'entità</span><span class="sxs-lookup"><span data-stu-id="75279-171">Updating an Entity</span></span>  
 <span data-ttu-id="75279-172">Nei passaggi seguenti si recupererà un oggetto `Customer` e si modificherà una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="75279-172">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="75279-173">Per modificare il nome di un oggetto Customer</span><span class="sxs-lookup"><span data-stu-id="75279-173">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="75279-174">Aggiungere il codice seguente sopra `Console.ReadLine()`:</span><span class="sxs-lookup"><span data-stu-id="75279-174">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="75279-175">Eliminazione di un'entità</span><span class="sxs-lookup"><span data-stu-id="75279-175">Deleting an Entity</span></span>  
 <span data-ttu-id="75279-176">Usando lo stesso oggetto Customer, è possibile eliminare il primo ordine.</span><span class="sxs-lookup"><span data-stu-id="75279-176">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="75279-177">Nel codice seguente viene illustrato come interrompere le relazioni tra le righe e come eliminare una riga dal database.</span><span class="sxs-lookup"><span data-stu-id="75279-177">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="75279-178">Per eliminare una riga</span><span class="sxs-lookup"><span data-stu-id="75279-178">To delete a row</span></span>  
  
- <span data-ttu-id="75279-179">Aggiungere il codice seguente sopra `Console.ReadLine()`:</span><span class="sxs-lookup"><span data-stu-id="75279-179">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="75279-180">Invio di modifiche al database</span><span class="sxs-lookup"><span data-stu-id="75279-180">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="75279-181">Il passaggio finale necessario per la creazione, l'aggiornamento e l'eliminazione di oggetti consiste nell'inviare effettivamente le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="75279-181">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="75279-182">Senza questo passaggio le modifiche vengono applicate solo localmente e non saranno visualizzate nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="75279-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="75279-183">Per inviare le modifiche al database</span><span class="sxs-lookup"><span data-stu-id="75279-183">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="75279-184">Inserire il codice seguente sopra `Console.ReadLine`:</span><span class="sxs-lookup"><span data-stu-id="75279-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="75279-185">Inserire il codice seguente dopo `SubmitChanges` per mostrare gli effetti precedenti e successivi all'invio delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="75279-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. <span data-ttu-id="75279-186">Premere F5 per eseguire il debug della soluzione.</span><span class="sxs-lookup"><span data-stu-id="75279-186">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="75279-187">Viene visualizzata la finestra di console come segue:</span><span class="sxs-lookup"><span data-stu-id="75279-187">The console window appears as follows:</span></span>  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. <span data-ttu-id="75279-188">Premere INVIO nella finestra della **console** per arrestare il debug.</span><span class="sxs-lookup"><span data-stu-id="75279-188">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75279-189">Dopo avere aggiunto il nuovo oggetto Customer mediante l'invio delle modifiche, non sarà possibile eseguire nuovamente questa soluzione così com'è, poiché non è possibile aggiungere di nuovo lo stesso oggetto Customer.</span><span class="sxs-lookup"><span data-stu-id="75279-189">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="75279-190">Per eseguire nuovamente la soluzione, modificare il valore dell'ID dell'oggetto Customer da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="75279-190">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75279-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75279-191">See also</span></span>

- [<span data-ttu-id="75279-192">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="75279-192">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
