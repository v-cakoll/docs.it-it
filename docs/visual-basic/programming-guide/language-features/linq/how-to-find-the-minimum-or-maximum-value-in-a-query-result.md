---
title: 'Procedura: trovare il valore minimo o massimo in un risultato di Query utilizzando LINQ (Visual Basic) | Documenti di Microsoft'
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
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
caps.latest.revision: 6
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
ms.openlocfilehash: 76f5ad02dc79bf8447ae0656c0ea90b5d9bb8edc
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="30abc-102">Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30abc-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="30abc-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni di database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="30abc-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="30abc-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30abc-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="30abc-105">Nell'esempio vengono determinati i valori minimi e massimo per i risultati utilizzando il `Aggregate` e `Group By` clausole.</span><span class="sxs-lookup"><span data-stu-id="30abc-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="30abc-106">Per ulteriori informazioni, vedere [clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="30abc-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="30abc-107">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="30abc-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="30abc-108">Se si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="30abc-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="30abc-109">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="30abc-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="30abc-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="30abc-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="30abc-111">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Esplora Database** sul **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="30abc-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="30abc-112">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="30abc-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="30abc-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="30abc-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="30abc-114">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="30abc-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="30abc-115">In Visual Studio, nel **File** dal menu **nuovo** e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="30abc-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="30abc-116">Selezionare Visual Basic **applicazione Windows Form** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="30abc-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="30abc-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="30abc-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="30abc-118">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="30abc-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="30abc-119">Nome del file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="30abc-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="30abc-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="30abc-120">Click **Add**.</span></span> <span data-ttu-id="30abc-121">Per il file Northwind. dbml viene aperta la Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="30abc-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="30abc-122">Per aggiungere le tabelle di eseguire query O/R Designer</span><span class="sxs-lookup"><span data-stu-id="30abc-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="30abc-123">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="30abc-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="30abc-124">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="30abc-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="30abc-125">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="30abc-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="30abc-126">Fare clic sulla tabella Customers e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="30abc-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="30abc-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="30abc-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="30abc-128">La finestra di progettazione crea nuovi `Customer` e `Order` gli oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="30abc-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="30abc-129">Si noti che la finestra di progettazione vengono rilevati automaticamente relazioni tra le tabelle e crea figlio le proprietà degli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="30abc-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="30abc-130">Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="30abc-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="30abc-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="30abc-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="30abc-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="30abc-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="30abc-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="30abc-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="30abc-134">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView>controllo nel Form di Windows predefinito per il progetto, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="30abc-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="30abc-135">Fare doppio clic su Form1 per aggiungere il codice per il `Load` evento del form.</span><span class="sxs-lookup"><span data-stu-id="30abc-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="30abc-136">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext>oggetto per il progetto.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="30abc-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="30abc-137">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="30abc-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="30abc-138">Il <xref:System.Data.Linq.DataContext>oggetto per il progetto viene denominato in base al nome del file. dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="30abc-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="30abc-139">Per questo progetto, il <xref:System.Data.Linq.DataContext>oggetto è denominato `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="30abc-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="30abc-140">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext>nel codice e query nelle tabelle specificate da O/R Designer.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="30abc-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="30abc-141">Aggiungere il codice seguente per il `Load` evento.</span><span class="sxs-lookup"><span data-stu-id="30abc-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="30abc-142">Questo codice esegue una query nelle tabelle vengono esposte come proprietà del contesto dati e determina i valori minimi e massimo per i risultati.</span><span class="sxs-lookup"><span data-stu-id="30abc-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="30abc-143">Nell'esempio viene utilizzata la `Aggregate` clausola per eseguire query per un singolo risultato e `Group By` clausola per visualizzare una media dei risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="30abc-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     <span data-ttu-id="30abc-144">[!code-vb[VbLINQToSQLHowTos&#14;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="30abc-144">[!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]</span></span>  
  
4.  <span data-ttu-id="30abc-145">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="30abc-145">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30abc-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30abc-146">See Also</span></span>  
 <span data-ttu-id="30abc-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="30abc-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="30abc-148"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="30abc-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="30abc-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="30abc-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="30abc-150"> [Metodi DataContext (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="30abc-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

