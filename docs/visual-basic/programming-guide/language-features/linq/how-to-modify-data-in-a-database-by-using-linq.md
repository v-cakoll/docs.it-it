---
title: 'Procedura: Modificare dati in un database usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: eb076d9156fa66858f2e560422eef0dc61ba22b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403485"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="cd682-102">Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd682-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="cd682-103">Con le query LINQ (Language-Integrated Query) è possibile accedere facilmente alle informazioni sul database e modificare i valori nel database.</span><span class="sxs-lookup"><span data-stu-id="cd682-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>

<span data-ttu-id="cd682-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che recupera e aggiorna le informazioni in un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cd682-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>

<span data-ttu-id="cd682-105">Negli esempi di questo argomento viene utilizzato il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="cd682-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="cd682-106">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd682-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="cd682-107">Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="cd682-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="cd682-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="cd682-108">To create a connection to a database</span></span>

1. <span data-ttu-id="cd682-109">In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic sul menu **Visualizza** e quindi selezionare **Esplora server** / **Esplora database**.</span><span class="sxs-lookup"><span data-stu-id="cd682-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>

2. <span data-ttu-id="cd682-110">Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database**e scegliere **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="cd682-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>

3. <span data-ttu-id="cd682-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="cd682-111">Specify a valid connection to the Northwind sample database.</span></span>

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="cd682-112">Per aggiungere un progetto con un file di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cd682-112">To add a Project with a LINQ to SQL file</span></span>

1. <span data-ttu-id="cd682-113">In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="cd682-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="cd682-114">Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="cd682-115">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cd682-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="cd682-116">Selezionare il modello di elemento **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="cd682-116">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="cd682-117">Assegnare al file il nome `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="cd682-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="cd682-118">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cd682-118">Click **Add**.</span></span> <span data-ttu-id="cd682-119">Il Object Relational Designer (O/R Designer) viene aperto per il `northwind.dbml` file.</span><span class="sxs-lookup"><span data-stu-id="cd682-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="cd682-120">Per aggiungere tabelle per eseguire query e modifiche nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="cd682-120">To add tables to query and modify to the designer</span></span>

1. <span data-ttu-id="cd682-121">In **Esplora server** / **Esplora database**espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="cd682-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="cd682-122">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="cd682-122">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="cd682-123">Se la finestra di progettazione O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul `northwind.dbml` file aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cd682-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>

2. <span data-ttu-id="cd682-124">Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cd682-124">Click the Customers table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="cd682-125">La finestra di progettazione crea un nuovo oggetto Customer per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-125">The designer creates a new Customer object for your project.</span></span>

3. <span data-ttu-id="cd682-126">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cd682-126">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="cd682-127">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-127">Save your project.</span></span>

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="cd682-128">Per aggiungere codice per modificare il database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="cd682-128">To add code to modify the database and display the results</span></span>

1. <span data-ttu-id="cd682-129">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.</span><span class="sxs-lookup"><span data-stu-id="cd682-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="cd682-130">Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto al progetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="cd682-131">Questo oggetto contiene codice che è possibile utilizzare per accedere alla tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="cd682-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="cd682-132">Contiene anche codice che definisce un oggetto Customer locale e una raccolta Customers per la tabella.</span><span class="sxs-lookup"><span data-stu-id="cd682-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="cd682-133">L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="cd682-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="cd682-134">Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="cd682-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

     <span data-ttu-id="cd682-135">È possibile creare un'istanza dell' <xref:System.Data.Linq.DataContext> oggetto nel codice e cercare e modificare la raccolta Customers specificata da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="cd682-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="cd682-136">Le modifiche apportate alla raccolta Customers non vengono riflesse nel database fino a quando non vengono inviate chiamando il <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metodo dell' <xref:System.Data.Linq.DataContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>

     <span data-ttu-id="cd682-137">Fare doppio clic su Windows Form, Form1, per aggiungere codice all' <xref:System.Windows.Forms.Form.Load> evento per eseguire una query sulla tabella Customers esposta come proprietà dell'oggetto <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="cd682-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="cd682-138">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cd682-138">Add the following code:</span></span>

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. <span data-ttu-id="cd682-139">Dalla **casella degli strumenti**Trascinare tre <xref:System.Windows.Forms.Button> controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="cd682-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="cd682-140">Selezionare il primo `Button` controllo.</span><span class="sxs-lookup"><span data-stu-id="cd682-140">Select the first `Button` control.</span></span> <span data-ttu-id="cd682-141">Nella finestra **Proprietà** impostare la proprietà `Name` del `Button` controllo su `AddButton` e `Text` su `Add` .</span><span class="sxs-lookup"><span data-stu-id="cd682-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="cd682-142">Selezionare il secondo pulsante e impostare la `Name` proprietà su `UpdateButton` e la `Text` proprietà su `Update` .</span><span class="sxs-lookup"><span data-stu-id="cd682-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="cd682-143">Selezionare il terzo pulsante e impostare la `Name` proprietà su `DeleteButton` e la `Text` proprietà su `Delete` .</span><span class="sxs-lookup"><span data-stu-id="cd682-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>

4. <span data-ttu-id="cd682-144">Fare doppio clic sul pulsante **Aggiungi** per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="cd682-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="cd682-145">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cd682-145">Add the following code:</span></span>

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. <span data-ttu-id="cd682-146">Fare doppio clic sul pulsante **Aggiorna** per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="cd682-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="cd682-147">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cd682-147">Add the following code:</span></span>

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. <span data-ttu-id="cd682-148">Fare doppio clic sul pulsante **Elimina** per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="cd682-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="cd682-149">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cd682-149">Add the following code:</span></span>

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. <span data-ttu-id="cd682-150">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="cd682-150">Press F5 to run your project.</span></span> <span data-ttu-id="cd682-151">Fare clic su **Aggiungi** per aggiungere un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="cd682-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="cd682-152">Fare clic su **Aggiorna** per modificare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="cd682-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="cd682-153">Fare clic su **Elimina** per eliminare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="cd682-153">Click **Delete** to delete the new record.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd682-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd682-154">See also</span></span>

- [<span data-ttu-id="cd682-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="cd682-155">LINQ</span></span>](index.md)
- [<span data-ttu-id="cd682-156">Query</span><span class="sxs-lookup"><span data-stu-id="cd682-156">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="cd682-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cd682-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="cd682-158">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="cd682-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="cd682-159">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="cd682-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
