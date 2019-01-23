---
title: 'Procedura: Query su un Database utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: a76eb5a010c8c5f750336935f0044e8dcc4322f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514855"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="50e80-102">Procedura: Query su un Database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50e80-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="50e80-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="50e80-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="50e80-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50e80-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="50e80-105">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="50e80-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="50e80-106">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="50e80-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="50e80-107">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="50e80-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="50e80-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="50e80-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="50e80-109">In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="50e80-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="50e80-110">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="50e80-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="50e80-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="50e80-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="50e80-112">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="50e80-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="50e80-113">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="50e80-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="50e80-114">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="50e80-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="50e80-115">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="50e80-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="50e80-116">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="50e80-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="50e80-117">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="50e80-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="50e80-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="50e80-118">Click **Add**.</span></span> <span data-ttu-id="50e80-119">Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="50e80-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="50e80-120">Per aggiungere tabelle a query a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="50e80-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="50e80-121">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="50e80-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="50e80-122">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="50e80-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="50e80-123">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="50e80-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="50e80-124">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="50e80-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="50e80-125">Fare clic nella tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="50e80-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="50e80-126">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="50e80-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="50e80-127">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea figlio le proprietà per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="50e80-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="50e80-128">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="50e80-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="50e80-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="50e80-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="50e80-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="50e80-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="50e80-131">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="50e80-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="50e80-132">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="50e80-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="50e80-133">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del form.</span><span class="sxs-lookup"><span data-stu-id="50e80-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="50e80-134">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="50e80-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="50e80-135">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="50e80-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="50e80-136">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="50e80-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="50e80-137">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="50e80-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="50e80-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="50e80-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="50e80-139">Aggiungere il codice seguente per il `Load` eseguire query su tabelle che vengono esposti come proprietà del contesto dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="50e80-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="50e80-140">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="50e80-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="50e80-141">Di seguito sono riportate alcune query aggiuntive che è possibile provare:</span><span class="sxs-lookup"><span data-stu-id="50e80-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="50e80-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50e80-142">See also</span></span>
- [<span data-ttu-id="50e80-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="50e80-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="50e80-144">Query</span><span class="sxs-lookup"><span data-stu-id="50e80-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="50e80-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="50e80-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="50e80-146">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="50e80-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
