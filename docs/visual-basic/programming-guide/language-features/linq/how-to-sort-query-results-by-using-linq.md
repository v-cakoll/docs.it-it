---
title: 'Procedura: ordinare i risultati della Query utilizzando LINQ (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 0c728d9e52add00c9d3241a9f598c15eb2db17a5
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="6bd32-102">Procedura: ordinare i risultati di query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bd32-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="6bd32-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="6bd32-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="6bd32-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e ordina i risultati in base a più campi utilizzando il `Order By` clausola.</span><span class="sxs-lookup"><span data-stu-id="6bd32-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="6bd32-105">L'ordinamento per ogni campo può essere crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="6bd32-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="6bd32-106">Per ulteriori informazioni, vedere [clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6bd32-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="6bd32-107">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd32-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6bd32-108">Se si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="6bd32-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="6bd32-109">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="6bd32-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="6bd32-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="6bd32-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="6bd32-111">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Esplora Database** sul **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="6bd32-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="6bd32-112">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="6bd32-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="6bd32-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd32-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6bd32-114">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6bd32-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="6bd32-115">In Visual Studio, nel **File** dal menu **New** e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="6bd32-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6bd32-116">Selezionare Visual Basic **applicazione Windows Form** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd32-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="6bd32-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6bd32-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6bd32-118">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="6bd32-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="6bd32-119">Nome del file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6bd32-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6bd32-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6bd32-120">Click **Add**.</span></span> <span data-ttu-id="6bd32-121">Per il file Northwind. dbml viene aperta la Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="6bd32-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6bd32-122">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="6bd32-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="6bd32-123">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd32-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6bd32-124">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="6bd32-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="6bd32-125">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6bd32-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="6bd32-126">Fare clic sulla tabella Customers e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd32-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6bd32-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd32-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="6bd32-128">La finestra di progettazione crea nuovi `Customer` e `Order` gli oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd32-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6bd32-129">Si noti che la finestra di progettazione vengono rilevati automaticamente relazioni tra le tabelle e crea figlio le proprietà degli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="6bd32-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6bd32-130">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="6bd32-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="6bd32-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd32-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="6bd32-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd32-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6bd32-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="6bd32-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="6bd32-134">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView>controllo nel Form di Windows predefinito per il progetto, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="6bd32-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="6bd32-135">Fare doppio clic su Form1 per aggiungere il codice per il `Load` evento del form.</span><span class="sxs-lookup"><span data-stu-id="6bd32-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="6bd32-136">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext>oggetto al progetto.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="6bd32-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="6bd32-137">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="6bd32-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="6bd32-138">Il <xref:System.Data.Linq.DataContext>oggetto per il progetto viene denominato in base al nome del file. dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="6bd32-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6bd32-139">Per questo progetto, il <xref:System.Data.Linq.DataContext>oggetto è denominato `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="6bd32-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6bd32-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext>nel codice e query nelle tabelle specificate da O/R Designer.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="6bd32-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="6bd32-141">Aggiungere il codice seguente per il `Load` evento per eseguire query su tabelle che vengono esposte come proprietà del contesto dati e ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6bd32-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="6bd32-142">La query ordina i risultati in base al numero di ordini cliente, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="6bd32-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="6bd32-143">I clienti che hanno lo stesso numero di ordini vengono ordinati in base al nome della società in senso crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="6bd32-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     <span data-ttu-id="6bd32-144">[!code-vb[VbLINQToSQLHowTos&#10;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6bd32-144">[!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="6bd32-145">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6bd32-145">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd32-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd32-146">See Also</span></span>  
 <span data-ttu-id="6bd32-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bd32-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="6bd32-148"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="6bd32-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="6bd32-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="6bd32-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="6bd32-150"> [Metodi DataContext (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="6bd32-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

