---
title: 'Procedura: Ordina i risultati di Query utilizzando LINQ (Visual Basic)'
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
ms.openlocfilehash: ab1bebae4fe88e8b4e630a6f7eca70ca8d1b32c5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829161"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="d8eed-102">Procedura: Ordina i risultati di Query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8eed-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="d8eed-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="d8eed-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="d8eed-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e ordina i risultati per più campi usando la `Order By` clausola.</span><span class="sxs-lookup"><span data-stu-id="d8eed-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="d8eed-105">L'ordinamento per ogni campo può essere ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="d8eed-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="d8eed-106">Per altre informazioni, vedere [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d8eed-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="d8eed-107">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="d8eed-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d8eed-108">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="d8eed-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="d8eed-109">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d8eed-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d8eed-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="d8eed-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="d8eed-111">In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="d8eed-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="d8eed-112">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="d8eed-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="d8eed-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="d8eed-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d8eed-114">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d8eed-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="d8eed-115">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d8eed-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d8eed-116">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="d8eed-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="d8eed-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d8eed-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d8eed-118">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="d8eed-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="d8eed-119">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="d8eed-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d8eed-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d8eed-120">Click **Add**.</span></span> <span data-ttu-id="d8eed-121">Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="d8eed-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="d8eed-122">Per aggiungere tabelle a query a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="d8eed-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="d8eed-123">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="d8eed-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d8eed-124">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="d8eed-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="d8eed-125">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d8eed-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="d8eed-126">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d8eed-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="d8eed-127">Fare clic nella tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d8eed-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="d8eed-128">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d8eed-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="d8eed-129">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea figlio le proprietà per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="d8eed-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="d8eed-130">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="d8eed-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="d8eed-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d8eed-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="d8eed-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d8eed-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="d8eed-133">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="d8eed-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="d8eed-134">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="d8eed-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="d8eed-135">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del form.</span><span class="sxs-lookup"><span data-stu-id="d8eed-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="d8eed-136">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetti al progetto.</span><span class="sxs-lookup"><span data-stu-id="d8eed-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="d8eed-137">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e per accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="d8eed-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="d8eed-138">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="d8eed-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="d8eed-139">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="d8eed-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d8eed-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="d8eed-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="d8eed-141">Aggiungere il codice seguente per il `Load` eventi per le tabelle che vengono esposte come proprietà del contesto dati e ordinare i risultati di query.</span><span class="sxs-lookup"><span data-stu-id="d8eed-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="d8eed-142">La query ordina i risultati in base al numero di ordini dei clienti, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="d8eed-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="d8eed-143">I clienti che hanno lo stesso numero di ordini vengono ordinati in base al nome di società in modo crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="d8eed-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4.  <span data-ttu-id="d8eed-144">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d8eed-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8eed-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8eed-145">See also</span></span>

- [<span data-ttu-id="d8eed-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="d8eed-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="d8eed-147">Query</span><span class="sxs-lookup"><span data-stu-id="d8eed-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d8eed-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d8eed-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="d8eed-149">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="d8eed-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
