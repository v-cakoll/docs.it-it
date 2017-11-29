---
title: 'Procedura dettagliata: utilizzo solo di stored procedure (C#)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 52c9cfeab362a1603c1d18a9caa1601cd76711b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="12952-102">Procedura dettagliata: utilizzo solo di stored procedure (C#)</span><span class="sxs-lookup"><span data-stu-id="12952-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>
<span data-ttu-id="12952-103">In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'accesso ai dati eseguendo solo stored procedure.</span><span class="sxs-lookup"><span data-stu-id="12952-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="12952-104">Questo approccio viene spesso è usato dagli amministratori di database per limitare l'accesso all'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="12952-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12952-105">È inoltre possibile usare stored procedure nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override del comportamento predefinito, specialmente per i processi `Create`, `Update` e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="12952-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="12952-106">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="12952-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="12952-107">Per le finalità di questa procedura dettagliata si utilizzeranno due metodi di cui è stato eseguito il mapping alle stored procedure CustOrdersDetail e CustOrderHist nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="12952-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="12952-108">Il mapping viene applicato quando si esegue lo strumento della riga di comando SqlMetal per generare un file C#.</span><span class="sxs-lookup"><span data-stu-id="12952-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="12952-109">Per altre informazioni, vedere la sezione successiva relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="12952-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="12952-110">Questa procedura dettagliata non si basa su [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12952-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="12952-111">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono inoltre usare [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per implementare la funzionalità delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="12952-111">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="12952-112">Vedere [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="12952-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="12952-113">Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.</span><span class="sxs-lookup"><span data-stu-id="12952-113">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12952-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="12952-114">Prerequisites</span></span>  
 <span data-ttu-id="12952-115">Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="12952-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="12952-116">Per i file usati nella procedura dettagliata viene usata una cartella dedicata ("c:\linqtest7").</span><span class="sxs-lookup"><span data-stu-id="12952-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="12952-117">Creare la cartella prima di avviare la procedura.</span><span class="sxs-lookup"><span data-stu-id="12952-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="12952-118">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="12952-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="12952-119">Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12952-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="12952-120">Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="12952-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="12952-121">Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest7 .</span><span class="sxs-lookup"><span data-stu-id="12952-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>  
  
-   <span data-ttu-id="12952-122">Un file di codice C# generato dal database Northwind.</span><span class="sxs-lookup"><span data-stu-id="12952-122">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="12952-123">Questa procedura dettagliata è stata scritta usando lo strumento SqlMetal con la riga di comando seguente:</span><span class="sxs-lookup"><span data-stu-id="12952-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="12952-124">**SQLMetal /code:"c:\linqtest7\northwind.cs" c:\ "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="12952-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="12952-125">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="12952-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="12952-126">Panoramica</span><span class="sxs-lookup"><span data-stu-id="12952-126">Overview</span></span>  
 <span data-ttu-id="12952-127">La procedura dettagliata è costituita da sei attività principali:</span><span class="sxs-lookup"><span data-stu-id="12952-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="12952-128">Impostazione della soluzione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12952-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="12952-129">Aggiunta dell'assembly System.Data.Linq al progetto.</span><span class="sxs-lookup"><span data-stu-id="12952-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="12952-130">Aggiunta del file di codice del database al progetto.</span><span class="sxs-lookup"><span data-stu-id="12952-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="12952-131">Creazione di una connessione con il database.</span><span class="sxs-lookup"><span data-stu-id="12952-131">Creating a connection with the database.</span></span>  
  
-   <span data-ttu-id="12952-132">Impostazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="12952-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="12952-133">Esecuzione e test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="12952-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="12952-134">Creazione di una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="12952-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="12952-135">In questa prima attività verrà creata una soluzione [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] che contiene i riferimenti necessari per compilare ed eseguire un progetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12952-135">In this first task, you create a [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="12952-136">Per creare una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="12952-136">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="12952-137">Nel [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** dal menu **New**, quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="12952-137">On the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="12952-138">Nel **tipi di progetto** riquadro il **nuovo progetto** la finestra di dialogo, fare clic su **Visual c#**.</span><span class="sxs-lookup"><span data-stu-id="12952-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="12952-139">Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="12952-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="12952-140">Nel **nome** digitare **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="12952-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5.  <span data-ttu-id="12952-141">Nel **percorso** verificare in cui si desidera archiviare i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="12952-141">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="12952-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="12952-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="12952-143">Verrà aperto Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="12952-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="12952-144">Aggiunta del riferimento all'assembly LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="12952-144">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="12952-145">L'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è incluso nel modello Applicazione Windows Form standard.</span><span class="sxs-lookup"><span data-stu-id="12952-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="12952-146">Sarà pertanto necessario aggiungere l'assembly manualmente, come descritto nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12952-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="12952-147">Per aggiungere System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="12952-147">To add System.Data.Linq.dll</span></span>  
  
1.  <span data-ttu-id="12952-148">In **Esplora**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="12952-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="12952-149">Nel **Aggiungi riferimento** la finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly LINQ e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="12952-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="12952-150">L'assembly verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="12952-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="12952-151">Aggiunta del file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="12952-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="12952-152">In questa procedura si presuppone che sia stato usato lo strumento SqlMetal per generare un file di codice dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="12952-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="12952-153">Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="12952-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="12952-154">Per aggiungere il file di codice di Northwind al progetto</span><span class="sxs-lookup"><span data-stu-id="12952-154">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="12952-155">Nel **progetto** menu, fare clic su **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="12952-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="12952-156">Nel **Aggiungi elemento esistente** la finestra di dialogo, passare a c:\linqtest7\northwind.cs, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="12952-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="12952-157">Il file northwind.cs viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="12952-157">The northwind.cs file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="12952-158">Creazione di connessioni a database</span><span class="sxs-lookup"><span data-stu-id="12952-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="12952-159">In questo passaggio si definirà la connessione al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="12952-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="12952-160">Per questa procedura dettagliata viene usato il percorso "c:\linqtest7\northwnd.mdf".</span><span class="sxs-lookup"><span data-stu-id="12952-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="12952-161">Per creare la connessione al database</span><span class="sxs-lookup"><span data-stu-id="12952-161">To create the database connection</span></span>  
  
1.  <span data-ttu-id="12952-162">In **Esplora**, fare doppio clic su **Form1. cs**, quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="12952-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="12952-163">Digitare il codice riportato di seguito nella classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="12952-163">Type the following code into the `Form1` class:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="12952-164">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="12952-164">Setting up the User Interface</span></span>  
 <span data-ttu-id="12952-165">In questa attività verrà impostata un'interfaccia per consentire agli utenti di eseguire stored procedure per l'accesso ai dati nel database.</span><span class="sxs-lookup"><span data-stu-id="12952-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="12952-166">Nelle applicazioni create con questa procedura dettagliata gli utenti potranno accedere ai dati nel database solo usando le stored procedure incorporate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="12952-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="12952-167">Per impostare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="12952-167">To set up the user interface</span></span>  
  
1.  <span data-ttu-id="12952-168">Tornare alle finestre di progettazione form (**Form1]**).</span><span class="sxs-lookup"><span data-stu-id="12952-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>  
  
2.  <span data-ttu-id="12952-169">Scegliere **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="12952-169">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="12952-170">Verrà aperta la Casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="12952-170">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12952-171">Fare clic su di **Nascondi automaticamente** puntina da disegno per tenere aperta la casella degli strumenti quando si eseguono i rimanenti passaggi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="12952-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3.  <span data-ttu-id="12952-172">Trascinare due pulsanti, due caselle di testo e due etichette dalla casella degli strumenti **Form1**.</span><span class="sxs-lookup"><span data-stu-id="12952-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="12952-173">Disporre i controlli come raffigurato nell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="12952-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="12952-174">Espandere **Form1** in modo che i controlli adattamento.</span><span class="sxs-lookup"><span data-stu-id="12952-174">Expand **Form1** so that the controls fit easily.</span></span>  
  
4.  <span data-ttu-id="12952-175">Fare doppio clic su **label1**, quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="12952-175">Right-click **label1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="12952-176">Modifica il **testo** proprietà **label1** a **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="12952-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>  
  
6.  <span data-ttu-id="12952-177">Nello stesso modo per **label2**, modificare il **testo** proprietà **label2** a **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="12952-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>  
  
7.  <span data-ttu-id="12952-178">Nello stesso modo, è possibile modificare il **testo** proprietà **button1** a **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="12952-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>  
  
8.  <span data-ttu-id="12952-179">Modifica il **testo** proprietà **button2** a **cronologia degli ordini**.</span><span class="sxs-lookup"><span data-stu-id="12952-179">Change the **Text** property for **button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="12952-180">Ampliare i controlli pulsante in modo che tutto il testo sia visibile.</span><span class="sxs-lookup"><span data-stu-id="12952-180">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="12952-181">Per gestire i clic sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="12952-181">To handle button clicks</span></span>  
  
1.  <span data-ttu-id="12952-182">Fare doppio clic su **Order Details** su **Form1** per aprire il gestore eventi button1 nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="12952-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>  
  
2.  <span data-ttu-id="12952-183">Digitare il codice riportato di seguito nel gestore eventi `button1`:</span><span class="sxs-lookup"><span data-stu-id="12952-183">Type the following code into the `button1` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  <span data-ttu-id="12952-184">Fare doppio clic sul **button2** su **Form1** per aprire la `button2` gestore</span><span class="sxs-lookup"><span data-stu-id="12952-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>  
  
4.  <span data-ttu-id="12952-185">Digitare il codice riportato di seguito nel gestore eventi `button2`:</span><span class="sxs-lookup"><span data-stu-id="12952-185">Type the following code into the `button2` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="12952-186">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="12952-186">Testing the Application</span></span>  
 <span data-ttu-id="12952-187">A questo punto è possibile procedere al test dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="12952-187">Now it is time to test your application.</span></span> <span data-ttu-id="12952-188">Notare che il contatto con l'archivio dati è limitato alle azioni supportate dalle due stored procedure</span><span class="sxs-lookup"><span data-stu-id="12952-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="12952-189">che, in questo caso, consistono nel restituire i prodotti inclusi per qualsiasi ID ordine immesso o nel restituire una cronologia dei prodotti ordinati per qualsiasi ID cliente immesso.</span><span class="sxs-lookup"><span data-stu-id="12952-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="12952-190">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="12952-190">To test the application</span></span>  
  
1.  <span data-ttu-id="12952-191">Premere F5 per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="12952-191">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="12952-192">Viene visualizzato Form1.</span><span class="sxs-lookup"><span data-stu-id="12952-192">Form1 appears.</span></span>  
  
2.  <span data-ttu-id="12952-193">Nel **Enter OrderID** digitare `10249`, quindi fare clic su **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="12952-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="12952-194">I prodotti inclusi nell'ordine 10249 vengono elencati in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="12952-194">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="12952-195">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="12952-195">Click **OK** to close the message box.</span></span>  
  
3.  <span data-ttu-id="12952-196">Nel **Enter CustomerID** digitare `ALFKI`, quindi fare clic su **cronologia degli ordini**.</span><span class="sxs-lookup"><span data-stu-id="12952-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="12952-197">Viene visualizzata una finestra di messaggio con l'elenco della cronologia degli ordini per il cliente ALFKI.</span><span class="sxs-lookup"><span data-stu-id="12952-197">A message box appears that lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="12952-198">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="12952-198">Click **OK** to close the message box.</span></span>  
  
4.  <span data-ttu-id="12952-199">Nel **Enter OrderID** digitare `123`, quindi fare clic su **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="12952-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="12952-200">Viene visualizzata una finestra di messaggio con l'indicazione che non è stato trovato alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="12952-200">A message box appears that displays "No results."</span></span>  
  
     <span data-ttu-id="12952-201">Fare clic su **OK** per chiudere la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="12952-201">Click **OK** to close the message box.</span></span>  
  
5.  <span data-ttu-id="12952-202">Nel **Debug** menu, fare clic su **interrompere il debug**.</span><span class="sxs-lookup"><span data-stu-id="12952-202">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="12952-203">La sessione di debug viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="12952-203">The debug session closes.</span></span>  
  
6.  <span data-ttu-id="12952-204">Se il termine delle prove, è possibile fare clic su **Chiudi progetto** sul **File** menu e salvare il progetto quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="12952-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="12952-205">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="12952-205">Next Steps</span></span>  
 <span data-ttu-id="12952-206">Questo progetto può essere migliorato apportandovi alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="12952-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="12952-207">Ad esempio, è possibile elencare le stored procedure disponibili in una casella di riepilogo, in modo che l'utente possa selezionare quella da eseguire.</span><span class="sxs-lookup"><span data-stu-id="12952-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="12952-208">È inoltre possibile trasmettere l'output dei rapporti a un file di testo.</span><span class="sxs-lookup"><span data-stu-id="12952-208">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12952-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12952-209">See Also</span></span>  
 [<span data-ttu-id="12952-210">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="12952-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="12952-211">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="12952-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
