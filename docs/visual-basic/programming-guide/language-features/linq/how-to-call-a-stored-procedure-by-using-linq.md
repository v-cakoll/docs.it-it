---
title: 'Procedura: chiamare una Stored Procedure utilizzando LINQ (Visual Basic) | Documenti di Microsoft'
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
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
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
ms.openlocfilehash: 40e72ece8399b1ffbe8c5457c63113d563c9f7f8
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="760c4-102">Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="760c4-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="760c4-103">Language-Integrated Query (LINQ) consente di accedere alle informazioni di database, inclusi oggetti quali stored procedure di database.</span><span class="sxs-lookup"><span data-stu-id="760c4-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="760c4-104">Nell'esempio seguente viene illustrato come creare un'applicazione che chiama una stored procedure in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="760c4-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="760c4-105">Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="760c4-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="760c4-106">Ogni procedura restituisce i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="760c4-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="760c4-107">Una procedura accetta parametri di input e l'altra procedura non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="760c4-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="760c4-108">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="760c4-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="760c4-109">Se si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="760c4-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="760c4-110">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="760c4-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="760c4-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="760c4-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="760c4-112">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Esplora Database** sul **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="760c4-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="760c4-113">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="760c4-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="760c4-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="760c4-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="760c4-115">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="760c4-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="760c4-116">In Visual Studio, nel **File** dal menu **New** e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="760c4-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="760c4-117">Selezionare Visual Basic **applicazione Windows Form** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="760c4-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="760c4-118">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="760c4-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="760c4-119">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="760c4-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="760c4-120">Nome del file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="760c4-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="760c4-121">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="760c4-121">Click **Add**.</span></span> <span data-ttu-id="760c4-122">Per il file Northwind. dbml viene aperta la Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="760c4-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="760c4-123">Per aggiungere stored procedure a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="760c4-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="760c4-124">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="760c4-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="760c4-125">Espandere il **Stored procedure** cartella.</span><span class="sxs-lookup"><span data-stu-id="760c4-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="760c4-126">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="760c4-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="760c4-127">Fare clic su di **Sales by Year** stored procedure e trascinarlo nel riquadro a destra della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="760c4-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="760c4-128">Fare clic su di **Ten Most Expensive Products** stored procedure trascinarlo nel riquadro a destra della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="760c4-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="760c4-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="760c4-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="760c4-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="760c4-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="760c4-131">Per aggiungere il codice per visualizzare i risultati delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="760c4-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="760c4-132">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView>controllo nel Form di Windows predefinito per il progetto, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="760c4-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="760c4-133">Fare doppio clic su Form1 per aggiungere codice al relativo `Load` evento.</span><span class="sxs-lookup"><span data-stu-id="760c4-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="760c4-134">Quando si aggiungono stored procedure per la Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext>oggetto per il progetto.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="760c4-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="760c4-135">Questo oggetto contiene il codice che è necessario disporre per accedere a tali procedure.</span><span class="sxs-lookup"><span data-stu-id="760c4-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="760c4-136">Il <xref:System.Data.Linq.DataContext>oggetto per il progetto viene denominato in base al nome del file. dbml.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="760c4-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="760c4-137">Per questo progetto, il <xref:System.Data.Linq.DataContext>oggetto è denominato `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="760c4-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="760c4-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext>nel codice e chiamare i metodi della stored procedure specificato da O/R Designer.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="760c4-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="760c4-139">Per associare il <xref:System.Windows.Forms.DataGridView>dell'oggetto, potrebbe essere necessario forzare la query per eseguire immediatamente la chiamata il <xref:System.Linq.Enumerable.ToList%2A>metodo sui risultati della stored procedure.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="760c4-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="760c4-140">Aggiungere il codice seguente per il `Load` eventi per chiamare una qualsiasi delle stored procedure esposte come metodi per il contesto dati.</span><span class="sxs-lookup"><span data-stu-id="760c4-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     <span data-ttu-id="760c4-141">[!code-vb[VbLINQtoSQLHowTos n.&1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="760c4-141">[!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span></span>  
    <span data-ttu-id="760c4-142">[!code-vb[VbLINQtoSQLHowTos n.&2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="760c4-142">[!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span></span>  
  
4.  <span data-ttu-id="760c4-143">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="760c4-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760c4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="760c4-144">See Also</span></span>  
 <span data-ttu-id="760c4-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="760c4-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="760c4-146"> [Query](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="760c4-146"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="760c4-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="760c4-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="760c4-148"> [Metodi DataContext (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="760c4-148"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="760c4-149"> [Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="760c4-149"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>

