---
title: 'Procedura: Conteggio, somma, o media di dati usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 8be585c3e11bc3637b2dd1cfaf3437620aa2ba09
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405017"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="e5252-102">Procedura: conteggio, somma, o media di dati utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5252-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e5252-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="e5252-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="e5252-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5252-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="e5252-105">L'esempio conta, somma e calcola la media dei risultati usando le `Aggregate` `Group By` clausole e.</span><span class="sxs-lookup"><span data-stu-id="e5252-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="e5252-106">Per ulteriori informazioni, vedere clausola [Aggregate](../../../language-reference/queries/aggregate-clause.md) e [clausola Group by](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e5252-106">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="e5252-107">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="e5252-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e5252-108">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5252-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="e5252-109">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e5252-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e5252-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="e5252-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="e5252-111">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="e5252-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="e5252-112">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="e5252-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="e5252-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="e5252-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e5252-114">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e5252-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="e5252-115">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="e5252-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e5252-116">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="e5252-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="e5252-117">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e5252-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e5252-118">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="e5252-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="e5252-119">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e5252-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e5252-120">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5252-120">Click **Add**.</span></span> <span data-ttu-id="e5252-121">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="e5252-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e5252-122">Per aggiungere tabelle a query in Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="e5252-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="e5252-123">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="e5252-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e5252-124">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e5252-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e5252-125">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e5252-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="e5252-126">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5252-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="e5252-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5252-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e5252-128">La finestra di progettazione crea nuovi `Customer` `Order` oggetti e per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e5252-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="e5252-129">Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea le proprietà figlio per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="e5252-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="e5252-130">Ad esempio, IntelliSense indicherà che l' `Customer` oggetto dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="e5252-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="e5252-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5252-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="e5252-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="e5252-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e5252-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="e5252-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="e5252-134">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="e5252-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="e5252-135">Fare doppio clic su Form1 per aggiungere codice all' `Load` evento del modulo.</span><span class="sxs-lookup"><span data-stu-id="e5252-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="e5252-136">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e5252-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e5252-137">Questo oggetto contiene il codice necessario per accedere a tali tabelle e per accedere a oggetti e raccolte singoli per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="e5252-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="e5252-138">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="e5252-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e5252-139">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="e5252-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e5252-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="e5252-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e5252-141">Aggiungere il codice seguente all' `Load` evento per eseguire una query sulle tabelle esposte come proprietà del <xref:System.Data.Linq.DataContext> e contare, sommare e calcolare la media dei risultati.</span><span class="sxs-lookup"><span data-stu-id="e5252-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="e5252-142">Nell'esempio viene utilizzata la `Aggregate` clausola per eseguire una query per ottenere un singolo risultato e la `Group By` clausola per visualizzare una media per i risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="e5252-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="e5252-143">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e5252-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5252-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5252-144">See also</span></span>

- [<span data-ttu-id="e5252-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="e5252-145">LINQ</span></span>](index.md)
- [<span data-ttu-id="e5252-146">Query</span><span class="sxs-lookup"><span data-stu-id="e5252-146">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="e5252-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e5252-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="e5252-148">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="e5252-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="e5252-149">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="e5252-149">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="e5252-150">Clausola Group By</span><span class="sxs-lookup"><span data-stu-id="e5252-150">Group By Clause</span></span>](../../../language-reference/queries/group-by-clause.md)
