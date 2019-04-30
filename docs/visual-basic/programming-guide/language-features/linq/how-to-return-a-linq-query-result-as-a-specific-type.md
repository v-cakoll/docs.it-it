---
title: 'Procedura: Restituire un risultato di Query LINQ come tipo specifico (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 5ccd71d93185f9478f6720419369df713d590c39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053756"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="3a050-102">Procedura: Restituire un risultato di Query LINQ come tipo specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a050-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="3a050-103">Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.</span><span class="sxs-lookup"><span data-stu-id="3a050-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="3a050-104">Per impostazione predefinita, le query LINQ restituiscono un elenco di oggetti come un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="3a050-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="3a050-105">È anche possibile specificare che la query restituisca un elenco di uno specifico tipo usando il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="3a050-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="3a050-106">Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e proietta i risultati come un tipo denominato specifico.</span><span class="sxs-lookup"><span data-stu-id="3a050-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="3a050-107">Per altre informazioni, vedere [i tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3a050-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="3a050-108">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="3a050-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="3a050-109">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="3a050-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="3a050-110">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3a050-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="3a050-111">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="3a050-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="3a050-112">In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="3a050-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="3a050-113">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="3a050-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="3a050-114">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="3a050-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="3a050-115">Per aggiungere un progetto che contiene un file LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3a050-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="3a050-116">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3a050-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="3a050-117">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="3a050-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="3a050-118">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3a050-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="3a050-119">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="3a050-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="3a050-120">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="3a050-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="3a050-121">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3a050-121">Click **Add**.</span></span> <span data-ttu-id="3a050-122">Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="3a050-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="3a050-123">Per aggiungere tabelle a query a O/R Designer</span><span class="sxs-lookup"><span data-stu-id="3a050-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="3a050-124">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="3a050-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="3a050-125">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="3a050-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="3a050-126">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3a050-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="3a050-127">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a050-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="3a050-128">Crea una nuova finestra di progettazione `Customer` oggetto per il progetto.</span><span class="sxs-lookup"><span data-stu-id="3a050-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="3a050-129">È possibile proiettare un risultato della query come la `Customer` tipo o come un tipo che si crea.</span><span class="sxs-lookup"><span data-stu-id="3a050-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="3a050-130">In questo esempio crea un nuovo tipo in una procedura successiva e il risultato di una query di quel tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="3a050-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="3a050-131">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a050-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="3a050-132">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3a050-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="3a050-133">Per aggiungere il codice per eseguire query sul database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="3a050-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="3a050-134">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="3a050-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="3a050-135">Fare doppio clic su Form1 per modificare la classe Form1.</span><span class="sxs-lookup"><span data-stu-id="3a050-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="3a050-136">Dopo il `End Class` istruzione della classe Form1, aggiungere il codice seguente per creare un `CustomerInfo` tipo per contenere i risultati della query per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3a050-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="3a050-137">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetti al progetto.</span><span class="sxs-lookup"><span data-stu-id="3a050-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="3a050-138">Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle e per accedere ai singoli oggetti e raccolte per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="3a050-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="3a050-139">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="3a050-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="3a050-140">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="3a050-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="3a050-141">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="3a050-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="3a050-142">Nel `Load` eventi della classe Form1, aggiungere il codice seguente per eseguire query su tabelle che vengono esposti come proprietà del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="3a050-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="3a050-143">Il `Select` clausola della query verrà creata una nuova `CustomerInfo` tipo invece di un tipo anonimo per ogni elemento del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="3a050-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="3a050-144">Premere F5 per eseguire il progetto e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="3a050-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a050-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a050-145">See also</span></span>

- [<span data-ttu-id="3a050-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="3a050-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="3a050-147">Query</span><span class="sxs-lookup"><span data-stu-id="3a050-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3a050-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3a050-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="3a050-149">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="3a050-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
