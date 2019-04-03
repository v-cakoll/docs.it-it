---
title: 'Procedura: Filtrare i risultati della Query utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 4de6ed4436f6a1769d178508210ed20e0162f647
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822882"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="606a1-102">Procedura: Filtrare i risultati della Query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="606a1-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="606a1-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="606a1-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="606a1-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e filtra i risultati in un determinato valore utilizzando il `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="606a1-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="606a1-105">Per altre informazioni, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="606a1-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="606a1-106">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="606a1-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="606a1-107">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="606a1-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="606a1-108">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="606a1-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="606a1-109">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="606a1-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="606a1-110">In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="606a1-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="606a1-111">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="606a1-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="606a1-112">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="606a1-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="606a1-113">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="606a1-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="606a1-114">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="606a1-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="606a1-115">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="606a1-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="606a1-116">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="606a1-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="606a1-117">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="606a1-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="606a1-118">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="606a1-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="606a1-119">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="606a1-119">Click **Add**.</span></span> <span data-ttu-id="606a1-120">Verrà visualizzata la finestra di Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="606a1-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="606a1-121">Per aggiungere tabelle a query a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="606a1-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="606a1-122">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="606a1-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="606a1-123">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="606a1-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="606a1-124">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="606a1-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="606a1-125">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="606a1-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="606a1-126">Fare clic nella tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="606a1-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="606a1-127">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="606a1-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="606a1-128">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea figlio le proprietà per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="606a1-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="606a1-129">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="606a1-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="606a1-130">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="606a1-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="606a1-131">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="606a1-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="606a1-132">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="606a1-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="606a1-133">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="606a1-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="606a1-134">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del form.</span><span class="sxs-lookup"><span data-stu-id="606a1-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="606a1-135">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="606a1-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="606a1-136">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="606a1-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="606a1-137">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="606a1-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="606a1-138">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="606a1-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="606a1-139">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="606a1-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="606a1-140">Aggiungere il codice seguente per il `Load` eseguire query su tabelle che vengono esposti come proprietà del contesto dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="606a1-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="606a1-141">La query consente di filtrare i risultati e restituisce solo i clienti che si trovano in `London`.</span><span class="sxs-lookup"><span data-stu-id="606a1-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]  
  
4.  <span data-ttu-id="606a1-142">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="606a1-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="606a1-143">Di seguito sono alcuni altri filtri che è possibile provare.</span><span class="sxs-lookup"><span data-stu-id="606a1-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="606a1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="606a1-144">See also</span></span>

- [<span data-ttu-id="606a1-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="606a1-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="606a1-146">Query</span><span class="sxs-lookup"><span data-stu-id="606a1-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="606a1-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="606a1-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="606a1-148">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="606a1-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
