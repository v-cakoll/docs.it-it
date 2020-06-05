---
title: 'Procedura: Eseguire query in un database usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: ad4744e1734fd968f610ec02b60814eadd3ebe9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404965"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="a35ef-102">Procedura: eseguire query in un database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a35ef-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a35ef-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="a35ef-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="a35ef-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a35ef-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="a35ef-105">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a35ef-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a35ef-106">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a35ef-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a35ef-107">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a35ef-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a35ef-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="a35ef-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="a35ef-109">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="a35ef-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="a35ef-110">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="a35ef-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="a35ef-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a35ef-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a35ef-112">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a35ef-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="a35ef-113">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="a35ef-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a35ef-114">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="a35ef-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="a35ef-115">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a35ef-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a35ef-116">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="a35ef-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="a35ef-117">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="a35ef-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a35ef-118">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a35ef-118">Click **Add**.</span></span> <span data-ttu-id="a35ef-119">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="a35ef-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a35ef-120">Per aggiungere tabelle a query in Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="a35ef-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="a35ef-121">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="a35ef-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a35ef-122">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="a35ef-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="a35ef-123">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a35ef-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="a35ef-124">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a35ef-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a35ef-125">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a35ef-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="a35ef-126">La finestra di progettazione crea nuovi `Customer` `Order` oggetti e per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a35ef-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a35ef-127">Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea le proprietà figlio per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="a35ef-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a35ef-128">Ad esempio, IntelliSense indicherà che l' `Customer` oggetto dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="a35ef-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="a35ef-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a35ef-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="a35ef-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a35ef-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a35ef-131">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="a35ef-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="a35ef-132">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="a35ef-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="a35ef-133">Fare doppio clic su Form1 per aggiungere codice all' `Load` evento del modulo.</span><span class="sxs-lookup"><span data-stu-id="a35ef-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="a35ef-134">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a35ef-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a35ef-135">Questo oggetto contiene il codice necessario per accedere a tali tabelle, oltre a singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="a35ef-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="a35ef-136">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="a35ef-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a35ef-137">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="a35ef-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a35ef-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="a35ef-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="a35ef-139">Aggiungere il codice seguente all' `Load` evento per eseguire una query sulle tabelle esposte come proprietà del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="a35ef-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="a35ef-140">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a35ef-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="a35ef-141">Di seguito sono riportate alcune query aggiuntive che è possibile provare:</span><span class="sxs-lookup"><span data-stu-id="a35ef-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a35ef-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a35ef-142">See also</span></span>

- [<span data-ttu-id="a35ef-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="a35ef-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="a35ef-144">Query</span><span class="sxs-lookup"><span data-stu-id="a35ef-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="a35ef-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a35ef-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a35ef-146">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="a35ef-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
