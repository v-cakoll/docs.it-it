---
title: 'Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 943bf4c80d88633cad857896381efcbef69683cc
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="8ba9a-102">Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ba9a-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="8ba9a-103">Language-Integrated Query (LINQ) rende più semplice l'accesso a informazioni sul database, inclusi oggetti quali stored procedure di database.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="8ba9a-104">Nell'esempio seguente viene illustrato come creare un'applicazione che chiama una stored procedure in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="8ba9a-105">Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="8ba9a-106">Ogni procedura restituisce i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="8ba9a-107">Una procedura accetta parametri di input e le altre routine non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="8ba9a-108">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="8ba9a-109">Se non si dispone di esempio Northwind nel computer di sviluppo, è possibile scaricarlo dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sito Web.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="8ba9a-110">Per istruzioni, vedere [download dei database di esempio](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="8ba9a-110">For instructions, see [Downloading Sample Databases](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="8ba9a-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="8ba9a-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="8ba9a-112">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Database Esplora** sul **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="8ba9a-113">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="8ba9a-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="8ba9a-115">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8ba9a-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="8ba9a-116">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="8ba9a-117">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="8ba9a-118">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="8ba9a-119">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="8ba9a-120">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="8ba9a-121">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-121">Click **Add**.</span></span> <span data-ttu-id="8ba9a-122">Il Object Relational Designer (O/R Designer) è aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="8ba9a-123">Per aggiungere stored procedure a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="8ba9a-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="8ba9a-124">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="8ba9a-125">Espandere il **Stored procedure** cartella.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="8ba9a-126">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="8ba9a-127">Fare clic su di **Sales by Year** stored procedure e trascinarlo nel riquadro a destra della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="8ba9a-128">Fare clic su di **dieci prodotti più costosi** stored procedure trascinarla nel riquadro a destra della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="8ba9a-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="8ba9a-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="8ba9a-131">Per aggiungere il codice per visualizzare i risultati delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="8ba9a-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="8ba9a-132">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="8ba9a-133">Fare doppio clic su Form1 per aggiungere codice al relativo `Load` evento.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="8ba9a-134">Quando si aggiungono le stored procedure per la Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="8ba9a-135">Questo oggetto contiene il codice che è necessario disporre per accedere a tali procedure.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="8ba9a-136">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="8ba9a-137">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="8ba9a-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e chiamare i metodi della stored procedure specificato da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="8ba9a-139">Da associare il <xref:System.Windows.Forms.DataGridView> dell'oggetto, potrebbe essere necessario forzare la query per eseguire immediatamente la chiamata di <xref:System.Linq.Enumerable.ToList%2A> metodo sui risultati della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="8ba9a-140">Aggiungere il codice seguente per il `Load` eventi per chiamare una qualsiasi delle stored procedure esposte come metodi per il contesto dati.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  <span data-ttu-id="8ba9a-141">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba9a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ba9a-142">See Also</span></span>  
 [<span data-ttu-id="8ba9a-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="8ba9a-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="8ba9a-144">Query</span><span class="sxs-lookup"><span data-stu-id="8ba9a-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="8ba9a-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8ba9a-145">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="8ba9a-146">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="8ba9a-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="8ba9a-147">Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="8ba9a-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
