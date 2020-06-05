---
title: 'Procedura: restituire un risultato di query LINQ come tipo specifico'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: c8ed792bf3ffefd903d60522f621958e44546d32
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404952"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="b2b68-102">Procedura: restituire un risultato di query LINQ come tipo specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2b68-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="b2b68-103">LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="b2b68-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="b2b68-104">Per impostazione predefinita, le query LINQ restituiscono un elenco di oggetti come tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="b2b68-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="b2b68-105">È inoltre possibile specificare che una query restituisca un elenco di un tipo specifico utilizzando la `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="b2b68-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="b2b68-106">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e proietta i risultati come tipo denominato specifico.</span><span class="sxs-lookup"><span data-stu-id="b2b68-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="b2b68-107">Per ulteriori informazioni, vedere [tipi anonimi](../objects-and-classes/anonymous-types.md) e [clausola SELECT](../../../language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b2b68-107">For more information, see [Anonymous Types](../objects-and-classes/anonymous-types.md) and [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="b2b68-108">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b2b68-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b2b68-109">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2b68-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="b2b68-110">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b2b68-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b2b68-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="b2b68-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="b2b68-112">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="b2b68-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="b2b68-113">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="b2b68-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="b2b68-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b2b68-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="b2b68-115">Per aggiungere un progetto che contiene un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b2b68-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="b2b68-116">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="b2b68-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b2b68-117">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="b2b68-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="b2b68-118">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b2b68-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b2b68-119">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="b2b68-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="b2b68-120">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="b2b68-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b2b68-121">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b2b68-121">Click **Add**.</span></span> <span data-ttu-id="b2b68-122">Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="b2b68-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="b2b68-123">Per aggiungere tabelle a query in Progettazione relazionale di O/R</span><span class="sxs-lookup"><span data-stu-id="b2b68-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="b2b68-124">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="b2b68-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b2b68-125">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="b2b68-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="b2b68-126">Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b2b68-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="b2b68-127">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b2b68-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="b2b68-128">La finestra di progettazione crea un nuovo `Customer` oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b2b68-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="b2b68-129">È possibile proiettare un risultato di query come `Customer` tipo o come tipo creato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b2b68-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="b2b68-130">In questo esempio viene creato un nuovo tipo in una procedura successiva e viene proiettato il risultato di una query come quel tipo.</span><span class="sxs-lookup"><span data-stu-id="b2b68-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="b2b68-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b2b68-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="b2b68-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b2b68-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="b2b68-133">Per aggiungere codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="b2b68-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="b2b68-134">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="b2b68-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="b2b68-135">Fare doppio clic su Form1 per modificare la classe Form1.</span><span class="sxs-lookup"><span data-stu-id="b2b68-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="b2b68-136">Dopo l' `End Class` istruzione della classe Form1, aggiungere il codice seguente per creare un `CustomerInfo` tipo che contenga i risultati della query per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="b2b68-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="b2b68-137">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto al progetto.</span><span class="sxs-lookup"><span data-stu-id="b2b68-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="b2b68-138">Questo oggetto contiene il codice necessario per accedere a tali tabelle e per accedere a oggetti e raccolte singoli per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="b2b68-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="b2b68-139">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="b2b68-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b2b68-140">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="b2b68-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="b2b68-141">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="b2b68-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="b2b68-142">Nel `Load` caso della classe Form1, aggiungere il codice seguente per eseguire una query sulle tabelle esposte come proprietà del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="b2b68-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="b2b68-143">La `Select` clausola della query creerà un nuovo `CustomerInfo` tipo anziché un tipo anonimo per ogni elemento del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="b2b68-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="b2b68-144">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b2b68-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b68-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2b68-145">See also</span></span>

- [<span data-ttu-id="b2b68-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="b2b68-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="b2b68-147">Query</span><span class="sxs-lookup"><span data-stu-id="b2b68-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="b2b68-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b2b68-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="b2b68-149">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="b2b68-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
