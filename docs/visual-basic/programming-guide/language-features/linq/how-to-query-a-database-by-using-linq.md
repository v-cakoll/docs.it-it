---
title: 'Procedura: eseguire Query su un Database utilizzando LINQ (Visual Basic) | Documenti di Microsoft'
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
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: 12
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
ms.openlocfilehash: a645a71dd0489d6bf2cc0cd4fe5898eb7293f13c
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="b59e1-102">Procedura: eseguire query in un database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b59e1-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="b59e1-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="b59e1-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="b59e1-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b59e1-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="b59e1-105">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b59e1-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b59e1-106">Se si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="b59e1-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="b59e1-107">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="b59e1-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b59e1-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="b59e1-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="b59e1-109">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Esplora Database** sul **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="b59e1-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="b59e1-110">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="b59e1-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="b59e1-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b59e1-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="b59e1-112">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b59e1-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="b59e1-113">In Visual Studio, nel **File** dal menu **nuovo** e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="b59e1-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b59e1-114">Selezionare Visual Basic **applicazione Windows Form** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="b59e1-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="b59e1-115">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b59e1-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b59e1-116">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="b59e1-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="b59e1-117">Nome del file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="b59e1-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b59e1-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b59e1-118">Click **Add**.</span></span> <span data-ttu-id="b59e1-119">Per il file Northwind. dbml viene aperta la Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="b59e1-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="b59e1-120">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="b59e1-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="b59e1-121">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="b59e1-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b59e1-122">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="b59e1-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="b59e1-123">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b59e1-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="b59e1-124">Fare clic sulla tabella Customers e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b59e1-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="b59e1-125">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b59e1-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="b59e1-126">La finestra di progettazione crea nuovi `Customer` e `Order` gli oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b59e1-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="b59e1-127">Si noti che la finestra di progettazione vengono rilevati automaticamente relazioni tra le tabelle e crea figlio le proprietà degli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="b59e1-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="b59e1-128">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="b59e1-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="b59e1-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b59e1-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="b59e1-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b59e1-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="b59e1-131">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="b59e1-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="b59e1-132">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView>controllo nel Form di Windows predefinito per il progetto, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="b59e1-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="b59e1-133">Fare doppio clic su Form1 per aggiungere il codice per il `Load` evento del form.</span><span class="sxs-lookup"><span data-stu-id="b59e1-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="b59e1-134">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext>oggetto per il progetto.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="b59e1-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="b59e1-135">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="b59e1-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="b59e1-136">Il <xref:System.Data.Linq.DataContext>oggetto per il progetto viene denominato in base al nome del file. dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="b59e1-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b59e1-137">Per questo progetto, il <xref:System.Data.Linq.DataContext>oggetto è denominato `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="b59e1-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="b59e1-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext>nel codice e query nelle tabelle specificate da O/R Designer.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="b59e1-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="b59e1-139">Aggiungere il codice seguente per il `Load` query sulle tabelle che sono esposte come proprietà del contesto dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b59e1-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     <span data-ttu-id="b59e1-140">[!code-vb[VbLINQToSQLHowTos n.&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b59e1-140">[!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="b59e1-141">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b59e1-141">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="b59e1-142">Di seguito sono illustrate alcune query aggiuntive che è possibile provare:</span><span class="sxs-lookup"><span data-stu-id="b59e1-142">Following are some additional queries that you can try:</span></span>  
  
     <span data-ttu-id="b59e1-143">[!code-vb[VbLINQToSQLHowTos n.&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b59e1-143">[!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span></span>  
    <span data-ttu-id="b59e1-144">[!code-vb[VbLINQToSQLHowTos n.&5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b59e1-144">[!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59e1-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b59e1-145">See Also</span></span>  
 <span data-ttu-id="b59e1-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="b59e1-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="b59e1-147"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="b59e1-147"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="b59e1-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="b59e1-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="b59e1-149"> [Metodi DataContext (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="b59e1-149"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

