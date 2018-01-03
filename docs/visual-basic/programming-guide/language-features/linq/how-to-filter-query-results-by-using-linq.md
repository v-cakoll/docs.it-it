---
title: 'Procedura: filtrare i risultati di una query utilizzando LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80d4f05e9f90e8543c61af26080e66f9cf262f01
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="eb40a-102">Procedura: filtrare i risultati di una query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb40a-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="eb40a-103">Language-Integrated Query (LINQ) rende più semplice accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="eb40a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="eb40a-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e filtra i risultati in un determinato valore utilizzando il `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="eb40a-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="eb40a-105">Per ulteriori informazioni, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="eb40a-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="eb40a-106">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="eb40a-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="eb40a-107">Se non si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="eb40a-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="eb40a-108">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="eb40a-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="eb40a-109">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="eb40a-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="eb40a-110">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Database Esplora** sul **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="eb40a-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="eb40a-111">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="eb40a-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="eb40a-112">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="eb40a-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="eb40a-113">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eb40a-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="eb40a-114">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="eb40a-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="eb40a-115">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="eb40a-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="eb40a-116">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="eb40a-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="eb40a-117">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="eb40a-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="eb40a-118">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="eb40a-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="eb40a-119">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="eb40a-119">Click **Add**.</span></span> <span data-ttu-id="eb40a-120">Consente di aprire il Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="eb40a-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="eb40a-121">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="eb40a-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="eb40a-122">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="eb40a-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="eb40a-123">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="eb40a-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="eb40a-124">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="eb40a-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="eb40a-125">Fare clic sulla tabella di clienti e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb40a-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="eb40a-126">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb40a-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="eb40a-127">La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb40a-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="eb40a-128">Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea le proprietà per gli oggetti correlati figlio.</span><span class="sxs-lookup"><span data-stu-id="eb40a-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="eb40a-129">Ad esempio, IntelliSense visualizzerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="eb40a-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="eb40a-130">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb40a-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="eb40a-131">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb40a-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="eb40a-132">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="eb40a-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="eb40a-133">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="eb40a-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="eb40a-134">Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del modulo.</span><span class="sxs-lookup"><span data-stu-id="eb40a-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="eb40a-135">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb40a-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="eb40a-136">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="eb40a-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="eb40a-137">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="eb40a-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="eb40a-138">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="eb40a-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="eb40a-139">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query vengono specificate le tabelle da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="eb40a-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="eb40a-140">Aggiungere il codice seguente per il `Load` evento per eseguire query su tabelle che sono esposte come proprietà del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="eb40a-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="eb40a-141">La query filtra i risultati e restituisce solo i clienti che si trovano in `London`.</span><span class="sxs-lookup"><span data-stu-id="eb40a-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="eb40a-142">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="eb40a-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="eb40a-143">Di seguito sono alcuni altri filtri che è possibile provare.</span><span class="sxs-lookup"><span data-stu-id="eb40a-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eb40a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb40a-144">See Also</span></span>  
 [<span data-ttu-id="eb40a-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="eb40a-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="eb40a-146">Query</span><span class="sxs-lookup"><span data-stu-id="eb40a-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="eb40a-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eb40a-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="eb40a-148">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="eb40a-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
