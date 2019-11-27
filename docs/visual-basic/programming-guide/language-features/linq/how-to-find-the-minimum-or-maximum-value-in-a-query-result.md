---
title: 'Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: bddb90baa0b01fd9d724583b472af9f9fa7569e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344972"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="21196-102">Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21196-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="21196-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="21196-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="21196-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21196-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="21196-105">L'esempio determina i valori minimo e massimo per i risultati usando le clausole `Aggregate` e `Group By`.</span><span class="sxs-lookup"><span data-stu-id="21196-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="21196-106">Per ulteriori informazioni, vedere clausola [Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [clausola Group by](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="21196-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="21196-107">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="21196-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="21196-108">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dal Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="21196-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="21196-109">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="21196-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="21196-110">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="21196-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="21196-111">In Visual Studio aprire **Esplora server**/**Esplora database** scegliendo **Esplora server**/**Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="21196-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="21196-112">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server**/**Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="21196-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="21196-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="21196-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="21196-114">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="21196-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="21196-115">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="21196-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="21196-116">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="21196-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="21196-117">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="21196-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="21196-118">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="21196-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="21196-119">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="21196-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="21196-120">Fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="21196-120">Click **Add**.</span></span> <span data-ttu-id="21196-121">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="21196-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="21196-122">Per aggiungere tabelle a query in Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="21196-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="21196-123">In **Esplora server**/**Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="21196-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="21196-124">Espandere la cartella **tabelle** .</span><span class="sxs-lookup"><span data-stu-id="21196-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="21196-125">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="21196-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="21196-126">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="21196-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="21196-127">Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="21196-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="21196-128">La finestra di progettazione crea nuovi oggetti `Customer` e `Order` per il progetto.</span><span class="sxs-lookup"><span data-stu-id="21196-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="21196-129">Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea le proprietà figlio per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="21196-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="21196-130">Ad esempio, IntelliSense indicherà che l'oggetto `Customer` dispone di una proprietà `Orders` per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="21196-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="21196-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="21196-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="21196-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="21196-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="21196-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="21196-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="21196-134">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.DataGridView> nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="21196-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="21196-135">Fare doppio clic su Form1 per aggiungere codice all'evento `Load` del modulo.</span><span class="sxs-lookup"><span data-stu-id="21196-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="21196-136">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un oggetto <xref:System.Data.Linq.DataContext> per il progetto.</span><span class="sxs-lookup"><span data-stu-id="21196-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="21196-137">Questo oggetto contiene il codice necessario per accedere a tali tabelle, oltre a singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="21196-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="21196-138">L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="21196-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="21196-139">Per questo progetto, l'oggetto <xref:System.Data.Linq.DataContext> è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="21196-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="21196-140">È possibile creare un'istanza del <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="21196-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="21196-141">Aggiungere il codice seguente all'evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="21196-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="21196-142">Questo codice esegue una query sulle tabelle esposte come proprietà del contesto dati e determina i valori minimo e massimo per i risultati.</span><span class="sxs-lookup"><span data-stu-id="21196-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="21196-143">Nell'esempio viene utilizzata la clausola `Aggregate` per eseguire una query per ottenere un singolo risultato e la clausola `Group By` per visualizzare una media per i risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="21196-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="21196-144">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="21196-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21196-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21196-145">See also</span></span>

- [<span data-ttu-id="21196-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="21196-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="21196-147">Query</span><span class="sxs-lookup"><span data-stu-id="21196-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="21196-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="21196-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="21196-149">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="21196-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
