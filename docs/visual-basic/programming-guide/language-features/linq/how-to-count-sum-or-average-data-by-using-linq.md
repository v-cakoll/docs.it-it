---
title: 'Procedura: conteggio, somma, o media di dati utilizzando LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dbdc074bef64413b8b25709e48bba49f296ecb95
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="d08c2-102">Procedura: conteggio, somma, o media di dati utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d08c2-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="d08c2-103">Language-Integrated Query (LINQ) rende più semplice accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="d08c2-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="d08c2-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d08c2-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="d08c2-105">L'esempio esegue il conteggio, somma e la media dei risultati utilizzando il `Aggregate` e `Group By` clausole.</span><span class="sxs-lookup"><span data-stu-id="d08c2-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="d08c2-106">Per ulteriori informazioni, vedere [clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d08c2-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="d08c2-107">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="d08c2-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d08c2-108">Se non si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="d08c2-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="d08c2-109">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d08c2-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d08c2-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="d08c2-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="d08c2-111">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Database Esplora** sul **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="d08c2-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="d08c2-112">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="d08c2-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="d08c2-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="d08c2-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d08c2-114">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d08c2-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="d08c2-115">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d08c2-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d08c2-116">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="d08c2-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="d08c2-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d08c2-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d08c2-118">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="d08c2-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="d08c2-119">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="d08c2-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d08c2-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d08c2-120">Click **Add**.</span></span> <span data-ttu-id="d08c2-121">Il Object Relational Designer (O/R Designer) è aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="d08c2-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="d08c2-122">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="d08c2-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="d08c2-123">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="d08c2-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d08c2-124">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="d08c2-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="d08c2-125">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d08c2-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="d08c2-126">Fare clic sulla tabella di clienti e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d08c2-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="d08c2-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d08c2-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="d08c2-128">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d08c2-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="d08c2-129">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea le proprietà per gli oggetti correlati figlio.</span><span class="sxs-lookup"><span data-stu-id="d08c2-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="d08c2-130">Ad esempio, IntelliSense visualizzerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="d08c2-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="d08c2-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d08c2-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="d08c2-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d08c2-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="d08c2-133">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="d08c2-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="d08c2-134">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="d08c2-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="d08c2-135">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del modulo.</span><span class="sxs-lookup"><span data-stu-id="d08c2-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="d08c2-136">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d08c2-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="d08c2-137">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e di accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="d08c2-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="d08c2-138">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="d08c2-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="d08c2-139">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="d08c2-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d08c2-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query vengono specificate le tabelle da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="d08c2-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="d08c2-141">Aggiungere il codice seguente per il `Load` evento per eseguire query su tabelle che vengono esposti come proprietà del <xref:System.Data.Linq.DataContext> e conteggio, somma e la media dei risultati.</span><span class="sxs-lookup"><span data-stu-id="d08c2-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="d08c2-142">Nell'esempio viene utilizzato il `Aggregate` clausola per eseguire query per un singolo risultato e `Group By` clausola per visualizzare una media dei risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="d08c2-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="d08c2-143">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d08c2-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08c2-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d08c2-144">See Also</span></span>  
 [<span data-ttu-id="d08c2-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="d08c2-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="d08c2-146">Query</span><span class="sxs-lookup"><span data-stu-id="d08c2-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="d08c2-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d08c2-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="d08c2-148">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="d08c2-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="d08c2-149">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="d08c2-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="d08c2-150">Clausola Group By</span><span class="sxs-lookup"><span data-stu-id="d08c2-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
