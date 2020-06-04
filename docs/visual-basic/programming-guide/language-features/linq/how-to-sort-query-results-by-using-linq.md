---
title: 'Procedura: Ordinare i risultati di query usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: c1bc6ab863f9de118d59e102d3d5d251d326f497
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404939"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="fcfef-102">Procedura: ordinare i risultati di query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcfef-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="fcfef-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="fcfef-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="fcfef-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e ordina i risultati in base a più campi utilizzando la `Order By` clausola.</span><span class="sxs-lookup"><span data-stu-id="fcfef-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="fcfef-105">Il tipo di ordinamento per ogni campo può essere ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="fcfef-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="fcfef-106">Per ulteriori informazioni, vedere [clausola ORDER BY](../../../language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fcfef-106">For more information, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="fcfef-107">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="fcfef-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fcfef-108">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fcfef-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fcfef-109">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fcfef-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fcfef-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="fcfef-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fcfef-111">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="fcfef-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fcfef-112">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="fcfef-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fcfef-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="fcfef-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fcfef-114">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fcfef-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fcfef-115">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="fcfef-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fcfef-116">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="fcfef-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fcfef-117">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fcfef-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fcfef-118">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="fcfef-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fcfef-119">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="fcfef-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fcfef-120">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fcfef-120">Click **Add**.</span></span> <span data-ttu-id="fcfef-121">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="fcfef-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fcfef-122">Per aggiungere tabelle a query in Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="fcfef-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fcfef-123">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="fcfef-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fcfef-124">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="fcfef-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fcfef-125">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fcfef-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fcfef-126">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fcfef-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="fcfef-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fcfef-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fcfef-128">La finestra di progettazione crea nuovi `Customer` `Order` oggetti e per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fcfef-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="fcfef-129">Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea le proprietà figlio per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="fcfef-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="fcfef-130">Ad esempio, IntelliSense indicherà che l' `Customer` oggetto dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="fcfef-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="fcfef-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fcfef-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fcfef-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="fcfef-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fcfef-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="fcfef-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fcfef-134">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="fcfef-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fcfef-135">Fare doppio clic su Form1 per aggiungere codice all' `Load` evento del modulo.</span><span class="sxs-lookup"><span data-stu-id="fcfef-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="fcfef-136">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto al progetto.</span><span class="sxs-lookup"><span data-stu-id="fcfef-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="fcfef-137">Questo oggetto contiene il codice necessario per accedere a tali tabelle e per accedere a oggetti e raccolte singoli per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="fcfef-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="fcfef-138">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="fcfef-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fcfef-139">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="fcfef-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fcfef-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="fcfef-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fcfef-141">Aggiungere il codice seguente all' `Load` evento per eseguire una query sulle tabelle esposte come proprietà del contesto dati e ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fcfef-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="fcfef-142">La query ordina i risultati in base al numero di ordini dei clienti, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="fcfef-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="fcfef-143">I clienti che hanno lo stesso numero di ordini sono ordinati in base al nome della società in ordine crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="fcfef-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="fcfef-144">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fcfef-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfef-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcfef-145">See also</span></span>

- [<span data-ttu-id="fcfef-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fcfef-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="fcfef-147">Query</span><span class="sxs-lookup"><span data-stu-id="fcfef-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="fcfef-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fcfef-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fcfef-149">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="fcfef-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
