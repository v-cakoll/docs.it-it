---
title: 'Procedura: restituire un risultato di Query LINQ come tipo specifico (Visual Basic) | Documenti di Microsoft'
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
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: 8
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
ms.openlocfilehash: ecbc691a0afeb7ba631949684a0457d9bcdb2728
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="90d83-102">Procedura: restituire un risultato di query LINQ come tipo specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90d83-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="90d83-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="90d83-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="90d83-104">Per impostazione predefinita, le query LINQ restituiscono un elenco di oggetti come un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="90d83-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="90d83-105">È inoltre possibile specificare che la query restituisca un elenco di un tipo specifico utilizzando il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="90d83-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="90d83-106">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e vengono proiettati i risultati come un tipo denominato specifico.</span><span class="sxs-lookup"><span data-stu-id="90d83-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="90d83-107">Per ulteriori informazioni, vedere [tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="90d83-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="90d83-108">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="90d83-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="90d83-109">Se si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="90d83-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="90d83-110">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="90d83-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="90d83-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="90d83-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="90d83-112">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Esplora Database** sul **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="90d83-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="90d83-113">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="90d83-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="90d83-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="90d83-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="90d83-115">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="90d83-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="90d83-116">In Visual Studio, nel **File** dal menu **New** e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="90d83-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="90d83-117">Selezionare Visual Basic **applicazione Windows Form** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="90d83-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="90d83-118">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="90d83-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="90d83-119">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="90d83-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="90d83-120">Nome del file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="90d83-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="90d83-121">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="90d83-121">Click **Add**.</span></span> <span data-ttu-id="90d83-122">Per il file Northwind. dbml viene aperta la Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="90d83-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="90d83-123">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="90d83-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="90d83-124">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="90d83-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="90d83-125">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="90d83-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="90d83-126">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="90d83-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="90d83-127">Fare clic sulla tabella Customers e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="90d83-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="90d83-128">La finestra di progettazione crea un nuovo `Customer` oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="90d83-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="90d83-129">È possibile progettare un risultato della query come la `Customer` tipo o come un tipo creato.</span><span class="sxs-lookup"><span data-stu-id="90d83-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="90d83-130">In questo esempio crea un nuovo tipo in una procedura successiva e il risultato della query come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="90d83-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="90d83-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="90d83-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="90d83-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="90d83-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="90d83-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="90d83-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="90d83-134">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView>controllo nel Form di Windows predefinito per il progetto, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="90d83-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="90d83-135">Fare doppio clic su Form1 per modificare la classe Form1.</span><span class="sxs-lookup"><span data-stu-id="90d83-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="90d83-136">Dopo il `End Class` istruzione della classe Form1, aggiungere il codice seguente per creare un `CustomerInfo` tipo per contenere i risultati della query per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="90d83-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     <span data-ttu-id="90d83-137">[!code-vb[VbLINQToSQLHowTos&#16;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="90d83-137">[!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span></span>  
  
4.  <span data-ttu-id="90d83-138">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext>oggetto al progetto.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="90d83-138">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="90d83-139">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="90d83-139">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="90d83-140">Il <xref:System.Data.Linq.DataContext>oggetto per il progetto viene denominato in base al nome del file. dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="90d83-140">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="90d83-141">Per questo progetto, il <xref:System.Data.Linq.DataContext>oggetto è denominato `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="90d83-141">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="90d83-142">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext>nel codice e query nelle tabelle specificate da O/R Designer.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="90d83-142">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="90d83-143">Nel `Load` evento della classe Form1, aggiungere il codice seguente per eseguire query su tabelle che sono esposte come proprietà del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="90d83-143">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="90d83-144">Il `Select` clausola della query verrà creato un nuovo `CustomerInfo` tipo anziché un tipo anonimo per ogni elemento del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="90d83-144">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     <span data-ttu-id="90d83-145">[!code-vb[VbLINQToSQLHowTos&#15;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="90d83-145">[!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span></span>  
  
5.  <span data-ttu-id="90d83-146">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="90d83-146">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d83-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90d83-147">See Also</span></span>  
 <span data-ttu-id="90d83-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="90d83-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="90d83-149"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="90d83-149"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="90d83-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="90d83-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="90d83-151"> [Metodi DataContext (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="90d83-151"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

