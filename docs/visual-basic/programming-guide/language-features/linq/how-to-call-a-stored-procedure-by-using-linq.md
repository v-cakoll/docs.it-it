---
title: 'Procedura: Chiamare una stored procedure usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: b451642a16f36c4f7fd19c853fdfd2282f5bede5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405030"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="6bd5f-102">Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bd5f-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="6bd5f-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database, inclusi oggetti di database quali stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="6bd5f-104">Nell'esempio seguente viene illustrato come creare un'applicazione che chiama un stored procedure in un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="6bd5f-105">Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="6bd5f-106">Ogni procedura restituisce i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="6bd5f-107">Una procedura accetta parametri di input e l'altra procedura non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="6bd5f-108">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6bd5f-109">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6bd5f-110">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6bd5f-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="6bd5f-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="6bd5f-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="6bd5f-112">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="6bd5f-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="6bd5f-113">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="6bd5f-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6bd5f-115">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6bd5f-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="6bd5f-116">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6bd5f-117">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="6bd5f-118">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6bd5f-119">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="6bd5f-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="6bd5f-120">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6bd5f-121">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-121">Click **Add**.</span></span> <span data-ttu-id="6bd5f-122">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="6bd5f-123">Per aggiungere stored procedure a Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="6bd5f-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="6bd5f-124">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6bd5f-125">Espandere la cartella **Stored procedure** .</span><span class="sxs-lookup"><span data-stu-id="6bd5f-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="6bd5f-126">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="6bd5f-127">Fare clic su **Sales by Year** stored procedure e trascinarlo nel riquadro destro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="6bd5f-128">Fare clic sui **dieci prodotti più costosi** stored procedure trascinarli nel riquadro destro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="6bd5f-129">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="6bd5f-130">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="6bd5f-131">Per aggiungere codice per visualizzare i risultati delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="6bd5f-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="6bd5f-132">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="6bd5f-133">Fare doppio clic su Form1 per aggiungere codice al relativo `Load` evento.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="6bd5f-134">Quando sono state aggiunte stored procedure a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6bd5f-135">Questo oggetto contiene il codice necessario per accedere a tali procedure.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="6bd5f-136">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="6bd5f-137">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="6bd5f-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6bd5f-138">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e chiamare i metodi stored procedure specificati da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="6bd5f-139">Per eseguire l'associazione all' <xref:System.Windows.Forms.DataGridView> oggetto, potrebbe essere necessario forzare l'esecuzione immediata della query chiamando il <xref:System.Linq.Enumerable.ToList%2A> metodo sui risultati della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="6bd5f-140">Aggiungere il codice seguente all' `Load` evento per chiamare una delle stored procedure esposte come metodi per il contesto dati.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="6bd5f-141">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6bd5f-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd5f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd5f-142">See also</span></span>

- [<span data-ttu-id="6bd5f-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="6bd5f-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="6bd5f-144">Query</span><span class="sxs-lookup"><span data-stu-id="6bd5f-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="6bd5f-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6bd5f-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6bd5f-146">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="6bd5f-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="6bd5f-147">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="6bd5f-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
