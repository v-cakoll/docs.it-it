---
title: 'Procedura: Conteggio, somma o Media di dati utilizzando LINQ (Visual Basic)'
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
ms.openlocfilehash: 3ee518928bccaedeaa54c642944ff4e73620ef39
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819138"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="a82ca-102">Procedura: Conteggio, somma o Media di dati utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a82ca-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a82ca-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="a82ca-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="a82ca-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a82ca-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="a82ca-105">L'esempio conta, calcola la somma e la media dei risultati usando il `Aggregate` e `Group By` clausole.</span><span class="sxs-lookup"><span data-stu-id="a82ca-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="a82ca-106">Per altre informazioni, vedere [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a82ca-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="a82ca-107">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a82ca-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a82ca-108">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="a82ca-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a82ca-109">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a82ca-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a82ca-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="a82ca-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="a82ca-111">In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="a82ca-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a82ca-112">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="a82ca-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="a82ca-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a82ca-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a82ca-114">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a82ca-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="a82ca-115">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a82ca-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a82ca-116">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="a82ca-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="a82ca-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a82ca-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a82ca-118">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="a82ca-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="a82ca-119">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="a82ca-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a82ca-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a82ca-120">Click **Add**.</span></span> <span data-ttu-id="a82ca-121">Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="a82ca-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a82ca-122">Per aggiungere tabelle a query a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="a82ca-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="a82ca-123">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="a82ca-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a82ca-124">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="a82ca-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="a82ca-125">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a82ca-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="a82ca-126">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a82ca-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a82ca-127">Fare clic nella tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a82ca-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="a82ca-128">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a82ca-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a82ca-129">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea figlio le proprietà per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="a82ca-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a82ca-130">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="a82ca-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="a82ca-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a82ca-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="a82ca-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a82ca-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a82ca-133">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="a82ca-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="a82ca-134">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="a82ca-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="a82ca-135">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del form.</span><span class="sxs-lookup"><span data-stu-id="a82ca-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="a82ca-136">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a82ca-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a82ca-137">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e per accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="a82ca-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="a82ca-138">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="a82ca-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a82ca-139">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="a82ca-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a82ca-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="a82ca-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="a82ca-141">Aggiungere il codice seguente per il `Load` eventi per eseguire query su tabelle che vengono esposti come proprietà del <xref:System.Data.Linq.DataContext> conteggio, somma e Media dei risultati.</span><span class="sxs-lookup"><span data-stu-id="a82ca-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="a82ca-142">L'esempio Usa la `Aggregate` clausola per eseguire query per un singolo risultato e il `Group By` clausola per visualizzare una media dei risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="a82ca-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4.  <span data-ttu-id="a82ca-143">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a82ca-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82ca-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a82ca-144">See also</span></span>

- [<span data-ttu-id="a82ca-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="a82ca-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="a82ca-146">Query</span><span class="sxs-lookup"><span data-stu-id="a82ca-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a82ca-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a82ca-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a82ca-148">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="a82ca-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="a82ca-149">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="a82ca-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="a82ca-150">Clausola Group By</span><span class="sxs-lookup"><span data-stu-id="a82ca-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
