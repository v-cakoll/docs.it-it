---
title: 'Procedura dettagliata: gestione degli errori che si verificano durante l''immissione di dati nel controllo DataGridView Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 016a30e4b578ead199124d70cc12f240c74bf370
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0d4f2-102">Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d4f2-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0d4f2-103">Gestione degli errori dall'archivio dati sottostante è una funzionalità necessaria per un'applicazione di immissione di dati.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="0d4f2-104">Windows Form <xref:System.Windows.Forms.DataGridView> controllo semplifica questa attività esponendo il <xref:System.Windows.Forms.DataGridView.DataError> evento, viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="0d4f2-105">In questa procedura dettagliata, si recupererà le righe di `Customers` tabella nel database di esempio Northwind e visualizzarli in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d4f2-106">Quando un duplicato `CustomerID` viene rilevato in una nuova riga o una riga esistente modificata, il <xref:System.Windows.Forms.DataGridView.DataError> si verifica l'evento, che verrà gestito visualizzando un <xref:System.Windows.Forms.MessageBox> che descrive l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="0d4f2-107">Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0d4f2-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0d4f2-108">Prerequisites</span></span>  
 <span data-ttu-id="0d4f2-109">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="0d4f2-109">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="0d4f2-110">Accesso a un server con il database di esempio Northwind di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="0d4f2-111">Creazione del form</span><span class="sxs-lookup"><span data-stu-id="0d4f2-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="0d4f2-112">Per gestire gli errori di immissione di dati nel controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="0d4f2-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="0d4f2-113">Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="0d4f2-114">Esempio di codice seguente fornisce l'inizializzazione di base e include un `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  <span data-ttu-id="0d4f2-115">Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="0d4f2-116">Nell'esempio viene utilizzata una `GetData` metodo che restituisce un insieme <xref:System.Data.DataTable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="0d4f2-117">Accertarsi di impostare il `connectionString` variabile su un valore appropriato per il database.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0d4f2-118">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="0d4f2-119">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="0d4f2-120">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-120">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  <span data-ttu-id="0d4f2-121">Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e impostare l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  <span data-ttu-id="0d4f2-122">Gestire il <xref:System.Windows.Forms.DataGridView.DataError> evento il <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="0d4f2-123">Se il contesto per l'errore è un'operazione di commit, visualizzare l'errore in un <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="0d4f2-124">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0d4f2-124">Testing the Application</span></span>  
 <span data-ttu-id="0d4f2-125">È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="0d4f2-126">Per verificare il modulo</span><span class="sxs-lookup"><span data-stu-id="0d4f2-126">To test the form</span></span>  
  
-   <span data-ttu-id="0d4f2-127">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="0d4f2-128">Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo riempito di dati della tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="0d4f2-129">Se si immette un valore duplicato per `CustomerID` e il commit della modifica, il valore della cella verrà ripristinato automaticamente e verrà visualizzato un <xref:System.Windows.Forms.MessageBox> che viene visualizzato l'errore di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0d4f2-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0d4f2-130">Next Steps</span></span>  
 <span data-ttu-id="0d4f2-131">Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="0d4f2-132">È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="0d4f2-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="0d4f2-133">Modificare gli stili del bordo e intestazione.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-133">Change border and header styles.</span></span> <span data-ttu-id="0d4f2-134">Per ulteriori informazioni, vedere [procedura: modificare il bordo e gli stili delle linee della griglia nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="0d4f2-135">Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d4f2-136">Per ulteriori informazioni, vedere [procedura: impedire l'aggiunta delle righe e eliminazione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), e [come: rendere sola lettura di colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="0d4f2-137">Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d4f2-138">Per ulteriori informazioni, vedere [procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="0d4f2-139">Gestire grandi set di dati utilizzando la modalità virtuale.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="0d4f2-140">Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="0d4f2-141">Personalizzare l'aspetto delle celle.</span><span class="sxs-lookup"><span data-stu-id="0d4f2-141">Customize the appearance of cells.</span></span> <span data-ttu-id="0d4f2-142">Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto di celle nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f2-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4f2-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d4f2-143">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="0d4f2-144">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d4f2-144">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="0d4f2-145">Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d4f2-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="0d4f2-146">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d4f2-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="0d4f2-147">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="0d4f2-147">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
