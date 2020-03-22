---
title: 'Procedura: Trovare il valore minimo o massimo in un risultato di query usando LINQ'
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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112362"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="6a3e6-102">Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a3e6-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="6a3e6-103">Language-Integrated Query (LINQ) semplifica l'accesso alle informazioni del database e l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="6a3e6-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.The following example shows how to create a new application that performs queries against a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="6a3e6-105">L'esempio determina i valori minimo e `Aggregate` massimo `Group By` per i risultati utilizzando le clausole e .</span><span class="sxs-lookup"><span data-stu-id="6a3e6-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="6a3e6-106">Per ulteriori informazioni, vedere [Clausola di aggregazione](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6a3e6-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="6a3e6-107">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6a3e6-108">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6a3e6-109">Per istruzioni, consultate [Download di database di esempio.](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)</span><span class="sxs-lookup"><span data-stu-id="6a3e6-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="6a3e6-110">Creare una connessione a un databaseCreate a connection to a database</span><span class="sxs-lookup"><span data-stu-id="6a3e6-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="6a3e6-111">In Visual Studio aprire**Esplora database** di Esplora **server**/scegliendo**Esplora database** di Esplora/ **server**dal menu **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="6a3e6-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="6a3e6-112">Fare clic con il pulsante destro del mouse su **Connessioni dati** in Esplora database **di Esplora**/**Database Explorer** server, quindi **scegliere Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="6a3e6-113">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6a3e6-114">Per aggiungere un progetto che contiene un file LINQ to SQLTo add a project that contains a LINQ to SQL file</span><span class="sxs-lookup"><span data-stu-id="6a3e6-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="6a3e6-115">In Visual Studio scegliere **Nuovo** dal menu **File,** quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6a3e6-116">Selezionare **Applicazione Windows Form** di Visual Basic come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="6a3e6-117">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6a3e6-118">Selezionare il modello di elemento **Classi LINQ to SQL.**</span><span class="sxs-lookup"><span data-stu-id="6a3e6-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="6a3e6-119">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6a3e6-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-120">Click **Add**.</span></span> <span data-ttu-id="6a3e6-121">Progettazione relazionale oggetti (O/R Designer) viene aperto per il file northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6a3e6-122">Aggiungere tabelle per eseguire query a Progettazione relazionale oggetti</span><span class="sxs-lookup"><span data-stu-id="6a3e6-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="6a3e6-123">In**Esplora database di Esplora**/ **server**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6a3e6-124">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="6a3e6-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="6a3e6-125">Se È stato chiuso Progettazione relazionale oggetti, è possibile riaprirlo facendo doppio clic sul file northwind.dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="6a3e6-126">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6a3e6-127">Fare clic sulla tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="6a3e6-128">La finestra `Customer` di `Order` progettazione crea nuovi oggetti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6a3e6-129">Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea proprietà figlio per gli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6a3e6-130">Ad esempio, IntelliSense mostrerà che l'oggetto `Customer` dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="6a3e6-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="6a3e6-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6a3e6-133">Aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="6a3e6-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="6a3e6-134">Dalla **Casella degli** <xref:System.Windows.Forms.DataGridView> strumenti trascinare un controllo nel Windows Form predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="6a3e6-135">Fare doppio clic su Form1 `Load` per aggiungere codice all'evento del form.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="6a3e6-136">Quando sono state aggiunte tabelle a Progettazione <xref:System.Data.Linq.DataContext> relazionale oggetti, la finestra di progettazione ha aggiunto un oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6a3e6-137">Questo oggetto contiene il codice necessario per accedere a tali tabelle, oltre a singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="6a3e6-138">L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6a3e6-139">Per questo progetto, l'oggetto <xref:System.Data.Linq.DataContext> è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6a3e6-140">È possibile creare un'istanza <xref:System.Data.Linq.DataContext> di nel codice ed eseguire una query sulle tabelle specificate da Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="6a3e6-141">Aggiungere il codice `Load` seguente all'evento.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="6a3e6-142">Questo codice esegue una query sulle tabelle esposte come proprietà del contesto dati e determina i valori minimo e massimo per i risultati.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="6a3e6-143">Nell'esempio `Aggregate` viene utilizzata la clausola per `Group By` eseguire una query per un singolo risultato e la clausola per visualizzare una media per i risultati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="6a3e6-144">Premere **F5** per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6a3e6-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3e6-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a3e6-145">See also</span></span>

- [<span data-ttu-id="6a3e6-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="6a3e6-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="6a3e6-147">Query</span><span class="sxs-lookup"><span data-stu-id="6a3e6-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6a3e6-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6a3e6-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6a3e6-149">DataContext Methods (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="6a3e6-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
