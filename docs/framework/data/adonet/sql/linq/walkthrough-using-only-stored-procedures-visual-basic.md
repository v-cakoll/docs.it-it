---
title: 'Procedura dettagliata: Usare solo stored procedure (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 1527e3b4b614d4e700ae0c2c0fc555e14c7bc8d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876733"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="8f831-102">Procedura dettagliata: Usare solo stored procedure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f831-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="8f831-103">In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'accesso ai dati usando solo stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8f831-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="8f831-104">Questo approccio viene spesso è usato dagli amministratori di database per limitare l'accesso all'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="8f831-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f831-105">È inoltre possibile usare stored procedure nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override del comportamento predefinito, specialmente per i processi `Create`, `Update` e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="8f831-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="8f831-106">Per altre informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8f831-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="8f831-107">Ai fini di questa procedura dettagliata, si userà due metodi che sono stato eseguito il mapping alle stored procedure nel database di esempio Northwind: CustOrdersDetail e CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="8f831-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="8f831-108">Il mapping si verifica quando si esegue lo strumento da riga di comando SqlMetal per generare un file di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8f831-108">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="8f831-109">Per altre informazioni, vedere la sezione successiva relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="8f831-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="8f831-110">Questa procedura dettagliata non si basa su [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f831-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="8f831-111">Gli sviluppatori che usano Visual Studio consente inoltre di [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per implementare la funzionalità delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8f831-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="8f831-112">Visualizzare [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="8f831-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="8f831-113">Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8f831-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8f831-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8f831-114">Prerequisites</span></span>  
 <span data-ttu-id="8f831-115">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="8f831-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="8f831-116">Una cartella dedicata ("c:\linqtest3") in cui inserire i file usati nella procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="8f831-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="8f831-117">Creare la cartella prima di avviare la procedura.</span><span class="sxs-lookup"><span data-stu-id="8f831-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="8f831-118">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8f831-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="8f831-119">Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f831-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="8f831-120">Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="8f831-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="8f831-121">Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest3.</span><span class="sxs-lookup"><span data-stu-id="8f831-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
-   <span data-ttu-id="8f831-122">Un file di codice Visual Basic generato dal database Northwind.</span><span class="sxs-lookup"><span data-stu-id="8f831-122">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="8f831-123">Questa procedura dettagliata è stata scritta usando lo strumento SqlMetal con la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8f831-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="8f831-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="8f831-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="8f831-125">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="8f831-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="8f831-126">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8f831-126">Overview</span></span>  
 <span data-ttu-id="8f831-127">La procedura dettagliata è costituita da sei attività principali:</span><span class="sxs-lookup"><span data-stu-id="8f831-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="8f831-128">Configurare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8f831-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="8f831-129">Aggiunta dell'assembly System.Data.Linq al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f831-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="8f831-130">Aggiunta del file di codice del database al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f831-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="8f831-131">Creazione di una connessione al database.</span><span class="sxs-lookup"><span data-stu-id="8f831-131">Creating a connection to the database.</span></span>  
  
-   <span data-ttu-id="8f831-132">Impostazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8f831-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="8f831-133">Esecuzione e test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f831-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="8f831-134">Creazione di una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8f831-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="8f831-135">In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="8f831-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="8f831-136">Per creare una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8f831-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="8f831-137">Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8f831-137">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="8f831-138">Nel riquadro **Tipi progetto** della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi fare clic su **Windows**</span><span class="sxs-lookup"><span data-stu-id="8f831-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="8f831-139">Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="8f831-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="8f831-140">Nel **Name** , digitare **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="8f831-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="8f831-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f831-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="8f831-142">Verrà aperto Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8f831-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="8f831-143">Aggiunta del riferimento all'assembly LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8f831-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="8f831-144">L'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è incluso nel modello Applicazione Windows Form standard.</span><span class="sxs-lookup"><span data-stu-id="8f831-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="8f831-145">Sarà pertanto necessario aggiungere l'assembly manualmente, come descritto nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f831-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="8f831-146">Per aggiungere System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="8f831-146">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="8f831-147">Nelle **Esplora soluzioni**, fare clic su **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="8f831-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="8f831-148">Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="8f831-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="8f831-149">Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f831-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8f831-150">L'assembly verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f831-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="8f831-151">Aggiunta del file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="8f831-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="8f831-152">In questa procedura si presuppone che sia stato usato lo strumento SqlMetal per generare un file di codice dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8f831-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="8f831-153">Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="8f831-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="8f831-154">Per aggiungere il file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="8f831-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="8f831-155">Nel **Project** menu, fare clic su **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="8f831-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="8f831-156">Nel **Aggiungi elemento esistente** finestra di dialogo, passare a c:\linqtest3\northwind.vb e quindi fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="8f831-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="8f831-157">Il file northwind.vb viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="8f831-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="8f831-158">Creazione di connessioni a database</span><span class="sxs-lookup"><span data-stu-id="8f831-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="8f831-159">In questo passaggio si definirà la connessione al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8f831-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="8f831-160">Per questa procedura dettagliata viene usato il percorso "c:\linqtest3\northwnd.mdf".</span><span class="sxs-lookup"><span data-stu-id="8f831-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="8f831-161">Per creare la connessione al database</span><span class="sxs-lookup"><span data-stu-id="8f831-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="8f831-162">Nelle **Esplora soluzioni**, fare doppio clic su **Form1.vb**, quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="8f831-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="8f831-163">`Class Form1` verrà visualizzato nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="8f831-163">`Class Form1` appears in the code editor.</span></span>  
  
2. <span data-ttu-id="8f831-164">Digitare il codice riportato di seguito nel blocco di codice `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8f831-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="8f831-165">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8f831-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="8f831-166">In questa attività verrà creata un'interfaccia per consentire agli utenti di eseguire stored procedure per l'accesso ai dati nel database.</span><span class="sxs-lookup"><span data-stu-id="8f831-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="8f831-167">Nell'applicazione creata con questa procedura dettagliata gli utenti potranno accedere ai dati nel database solo usando le stored procedure incorporate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f831-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="8f831-168">Per impostare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8f831-168">To set up the user interface</span></span>  
  
1. <span data-ttu-id="8f831-169">Tornare a di Windows Form della finestra di progettazione (**Form1.vb]**).</span><span class="sxs-lookup"><span data-stu-id="8f831-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="8f831-170">Scegliere **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="8f831-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="8f831-171">Verrà aperta la Casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="8f831-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8f831-172">Scegliere il **Nascondi automaticamente** puntina da disegno per tenere aperta la casella degli strumenti mentre si eseguono i rimanenti passaggi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8f831-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="8f831-173">Trascinare due pulsanti, due caselle di testo e due etichette dalla casella degli strumenti **Form1**.</span><span class="sxs-lookup"><span data-stu-id="8f831-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="8f831-174">Disporre i controlli come raffigurato nell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="8f831-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="8f831-175">Espandere **Form1** in modo che i controlli di adattarsi con facilità.</span><span class="sxs-lookup"><span data-stu-id="8f831-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="8f831-176">Fare doppio clic su **Label1**, quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f831-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="8f831-177">Modifica il **testo** proprietà dal **Label1** al **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="8f831-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="8f831-178">Nello stesso modo per **Label2**, modificare il **testo** proprietà dal **Label2** al **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="8f831-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="8f831-179">Nello stesso modo, modificare il **testo** proprietà per **Button1** al **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="8f831-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="8f831-180">Modifica il **testo** proprietà per **Button2** al **Order History**.</span><span class="sxs-lookup"><span data-stu-id="8f831-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="8f831-181">Ampliare i controlli pulsante in modo che tutto il testo sia visibile.</span><span class="sxs-lookup"><span data-stu-id="8f831-181">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="8f831-182">Per gestire i clic sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="8f831-182">To handle button clicks</span></span>  
  
1. <span data-ttu-id="8f831-183">Fare doppio clic su **Order Details** sul **Form1** per creare il `Button1` gestore eventi e aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="8f831-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="8f831-184">Digitare il codice riportato di seguito nel gestore eventi `Button1`:</span><span class="sxs-lookup"><span data-stu-id="8f831-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="8f831-185">A questo punto fare doppio clic su **Button2** su Form1 per creare il `Button2` gestore eventi e aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="8f831-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="8f831-186">Digitare il codice riportato di seguito nel gestore eventi `Button2`:</span><span class="sxs-lookup"><span data-stu-id="8f831-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="8f831-187">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8f831-187">Testing the Application</span></span>  
 <span data-ttu-id="8f831-188">A questo punto è possibile procedere al test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f831-188">Now it is time to test your application.</span></span> <span data-ttu-id="8f831-189">Notare che il contatto con l'archivio dati è limitato alle azioni supportate dalle due stored procedure</span><span class="sxs-lookup"><span data-stu-id="8f831-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="8f831-190">che, in questo caso, consistono nel restituire i prodotti inclusi per qualsiasi ID ordine immesso o nel restituire una cronologia dei prodotti ordinati per qualsiasi ID cliente immesso.</span><span class="sxs-lookup"><span data-stu-id="8f831-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="8f831-191">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8f831-191">To test the application</span></span>  
  
1. <span data-ttu-id="8f831-192">Premere F5 per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="8f831-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="8f831-193">Viene visualizzato Form1.</span><span class="sxs-lookup"><span data-stu-id="8f831-193">Form1 appears.</span></span>  
  
2. <span data-ttu-id="8f831-194">Nel **Enter OrderID** , digitare **10249** e quindi fare clic su **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="8f831-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="8f831-195">I prodotti inclusi nell'ordine 10249 vengono elencati in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8f831-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="8f831-196">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8f831-196">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="8f831-197">Nel **Enter CustomerID** , digitare `ALFKI`, quindi fare clic su **Order History**.</span><span class="sxs-lookup"><span data-stu-id="8f831-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="8f831-198">In una finestra di messaggio viene elencata la cronologia degli ordini per il cliente ALFKI.</span><span class="sxs-lookup"><span data-stu-id="8f831-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="8f831-199">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8f831-199">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="8f831-200">Nel **Enter OrderID** , digitare `123`, quindi fare clic su **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="8f831-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="8f831-201">Viene visualizzata una finestra di messaggio con l'indicazione che non è stato trovato alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="8f831-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="8f831-202">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8f831-202">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="8f831-203">Nel **Debug** menu, fare clic su **arrestare il debug**.</span><span class="sxs-lookup"><span data-stu-id="8f831-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="8f831-204">La sessione di debug viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="8f831-204">The debug session closes.</span></span>  
  
6. <span data-ttu-id="8f831-205">Se si al termine delle prove, è possibile fare clic su **Chiudi progetto** nel **File** menu e salvare il progetto quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="8f831-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8f831-206">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8f831-206">Next Steps</span></span>  
 <span data-ttu-id="8f831-207">Questo progetto può essere migliorato apportandovi alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="8f831-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="8f831-208">Ad esempio, è possibile elencare le stored procedure disponibili in una casella di riepilogo, in modo che l'utente possa selezionare quella da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8f831-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="8f831-209">È inoltre possibile trasmettere l'output dei rapporti a un file di testo.</span><span class="sxs-lookup"><span data-stu-id="8f831-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f831-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f831-210">See also</span></span>

- [<span data-ttu-id="8f831-211">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="8f831-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="8f831-212">stored procedure</span><span class="sxs-lookup"><span data-stu-id="8f831-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
