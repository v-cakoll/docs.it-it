---
title: 'Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973771"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0f03d-102">Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03d-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0f03d-103">Quando si desidera visualizzare quantità molto elevate di dati tabulari in un' <xref:System.Windows.Forms.DataGridView> (controllo), è possibile impostare il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true` e gestire in modo esplicito l'interazione del controllo con il relativo archivio dati.</span><span class="sxs-lookup"><span data-stu-id="0f03d-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="0f03d-104">Ciò consente di ottimizzare le prestazioni del controllo in questa situazione.</span><span class="sxs-lookup"><span data-stu-id="0f03d-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="0f03d-105">Il <xref:System.Windows.Forms.DataGridView> controllo fornisce diversi eventi che è possibile gestire in modo da interagire con un archivio dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f03d-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="0f03d-106">In questa procedura dettagliata è illustrato il processo di implementazione di questi gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="0f03d-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="0f03d-107">L'esempio di codice in questo argomento Usa un'origine dati molto semplice a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="0f03d-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="0f03d-108">In un ambiente di produzione, è in genere caricherà solo le righe da visualizzare in una cache e gestire <xref:System.Windows.Forms.DataGridView> eventi per interagire con e aggiornare la cache.</span><span class="sxs-lookup"><span data-stu-id="0f03d-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="0f03d-109">Per altre informazioni, vedere [implementazione della modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="0f03d-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="0f03d-110">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Implementare la modalità virtuale nel Windows Form controllo DataGridView](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0f03d-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="0f03d-111">Creazione del form</span><span class="sxs-lookup"><span data-stu-id="0f03d-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="0f03d-112">Per implementare la modalità virtuale</span><span class="sxs-lookup"><span data-stu-id="0f03d-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="0f03d-113">Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0f03d-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="0f03d-114">Il codice seguente contiene alcuni inizializzazione di base.</span><span class="sxs-lookup"><span data-stu-id="0f03d-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="0f03d-115">Dichiara alcune variabili che verranno usati nei passaggi successivi, fornisce un `Main` (metodo) e fornisce un layout in formato semplice nel costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="0f03d-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="0f03d-116">Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> controllano e popolare l'archivio dati con valori di esempio.</span><span class="sxs-lookup"><span data-stu-id="0f03d-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="0f03d-117">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventi che consente di recuperare il valore della cella richiesto dall'archivio dati o `Customer` oggetto attualmente in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0f03d-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="0f03d-118">Questo evento viene generato ogni volta che il <xref:System.Windows.Forms.DataGridView> controllo deve disegnare una cella.</span><span class="sxs-lookup"><span data-stu-id="0f03d-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="0f03d-119">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellValuePushed> evento che archivia un valore di cella modificata nel `Customer` oggetto che rappresenta la riga modificata.</span><span class="sxs-lookup"><span data-stu-id="0f03d-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="0f03d-120">Questo evento si verifica ogni volta che l'utente esegue il commit di una modifica del valore di cella.</span><span class="sxs-lookup"><span data-stu-id="0f03d-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="0f03d-121">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.NewRowNeeded> che crea un nuovo evento `Customer` oggetto che rappresenta una riga appena creata.</span><span class="sxs-lookup"><span data-stu-id="0f03d-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="0f03d-122">Questo evento si verifica ogni volta che l'utente immette la riga per i nuovi record.</span><span class="sxs-lookup"><span data-stu-id="0f03d-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="0f03d-123">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.RowValidated> eventi che consente di salvare le righe nuove o modificate per l'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="0f03d-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="0f03d-124">Questo evento si verifica ogni volta che l'utente modifica la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="0f03d-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="0f03d-125">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento che indica se il <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento si verifica quando l'utente segnala l'annullamento della riga premendo ESC due volte nella modalità di modifica o una volta di fuori di modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0f03d-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="0f03d-126">Per impostazione predefinita, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> viene generato al momento dell'annullamento della riga quando tutte le celle nella riga corrente sono state modificate, a meno che il <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> è impostata su `true` nel <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0f03d-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="0f03d-127">Questo evento è utile quando l'ambito di commit è determinato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0f03d-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="0f03d-128">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventi che rimuove i valori del `Customer` oggetto che rappresenta la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="0f03d-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="0f03d-129">Questo evento si verifica quando l'utente segnala l'annullamento della riga premendo ESC due volte nella modalità di modifica o una volta di fuori di modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0f03d-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="0f03d-130">Questo evento viene generato se nessuna cella nella riga corrente è stata modificata oppure se il valore della <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> proprietà è stata impostata su `false` in un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0f03d-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="0f03d-131">Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.UserDeletingRow> eventi che consente di eliminare un oggetto esistente `Customer` oggetto dall'archivio dati o rimuove un non sono state salvate `Customer` oggetto che rappresenta una riga appena creata.</span><span class="sxs-lookup"><span data-stu-id="0f03d-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="0f03d-132">Questo evento si verifica ogni volta che l'utente elimina una riga facendo clic su un'intestazione di riga e premendo il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="0f03d-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="0f03d-133">Implementare una semplice `Customers` classe per rappresentare gli elementi di dati utilizzati da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="0f03d-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="0f03d-134">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f03d-134">Testing the Application</span></span>  
 <span data-ttu-id="0f03d-135">È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="0f03d-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="0f03d-136">Per testare il form</span><span class="sxs-lookup"><span data-stu-id="0f03d-136">To test the form</span></span>  
  
- <span data-ttu-id="0f03d-137">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="0f03d-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="0f03d-138">Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo popolato con tre record cliente.</span><span class="sxs-lookup"><span data-stu-id="0f03d-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="0f03d-139">È possibile modificare i valori delle celle più in una riga e premere ESC due volte nella modalità di modifica e una volta di fuori di modalità di modifica per ripristinare l'intera riga per i relativi valori originali.</span><span class="sxs-lookup"><span data-stu-id="0f03d-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="0f03d-140">Quando si modifica, aggiungere o eliminare righe nel controllo `Customer` oggetti nell'archivio dati vengono modificati, aggiunti o eliminati anche.</span><span class="sxs-lookup"><span data-stu-id="0f03d-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f03d-141">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0f03d-141">Next Steps</span></span>  
 <span data-ttu-id="0f03d-142">Questa applicazione fornisce una conoscenza di base degli eventi è necessario gestire per implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0f03d-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0f03d-143">È possibile migliorare questa applicazione di base in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="0f03d-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="0f03d-144">Implementare un archivio dati che vengono memorizzati nella cache i valori da un database esterno.</span><span class="sxs-lookup"><span data-stu-id="0f03d-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="0f03d-145">La cache deve recuperare e rimuovere i valori in base alle esigenze in modo che contenga solo ciò che serve per la visualizzazione durante l'uso di una piccola quantità di memoria nel computer client.</span><span class="sxs-lookup"><span data-stu-id="0f03d-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="0f03d-146">Ottimizzare le prestazioni dell'archivio dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0f03d-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="0f03d-147">È possibile, ad esempio compensare le connessioni di rete lento anziché a limiti di memoria dei computer client usando una cache di dimensioni superiori e riducendo al minimo il numero di query di database.</span><span class="sxs-lookup"><span data-stu-id="0f03d-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="0f03d-148">Per altre informazioni sulla memorizzazione nella cache i valori da un database esterno, vedere [come: Implementare il modo virtuale con il caricamento dei dati Just-In-Time in di Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="0f03d-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f03d-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f03d-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="0f03d-150">Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f03d-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0f03d-151">Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f03d-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0f03d-152">Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f03d-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="0f03d-153">Procedura: Implementare la modalità virtuale nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f03d-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
