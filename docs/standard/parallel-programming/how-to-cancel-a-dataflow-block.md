---
title: 'Procedura: Annullare un blocco di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
ms.openlocfilehash: 530c231deeaba007975849ab6dc41f4da6a859ea
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285547"
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="6518e-102">Procedura: Annullare un blocco di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="6518e-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="6518e-103">In questo documento viene dimostrato come abilitare l'annullamento nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6518e-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="6518e-104">In questo esempio Windows Form viene usato per mostrare dove gli elementi di lavoro sono attivi in una pipeline del flusso di dati, nonché gli effetti dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="6518e-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="6518e-105">Per creare l'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6518e-105">To Create the Windows Forms Application</span></span>  
  
1. <span data-ttu-id="6518e-106">Creare un progetto **Windows Forms Application** di C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6518e-106">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="6518e-107">Nei passaggi seguenti il progetto viene denominato `CancellationWinForms`.</span><span class="sxs-lookup"><span data-stu-id="6518e-107">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2. <span data-ttu-id="6518e-108">Nella finestra di progettazione del form per il form principale, Form1.cs (Form1.vb per Visual Basic), aggiungere un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6518e-108">On the form designer for the main form, Form1.cs (Form1.vb for Visual Basic), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3. <span data-ttu-id="6518e-109">Aggiungere un controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6518e-109">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="6518e-110">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> e la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Aggiungi elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6518e-110">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4. <span data-ttu-id="6518e-111">Aggiungere un secondo controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6518e-111">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="6518e-112">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Annulla** e la proprietà <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> su `False`.</span><span class="sxs-lookup"><span data-stu-id="6518e-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5. <span data-ttu-id="6518e-113">Aggiungere quattro oggetti <xref:System.Windows.Forms.ToolStripProgressBar> al controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6518e-113">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="6518e-114">Creazione della pipeline del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6518e-114">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="6518e-115">In questa sezione viene descritto come creare la pipeline del flusso di dati che elabora gli elementi di lavoro e aggiorna le barre di stato.</span><span class="sxs-lookup"><span data-stu-id="6518e-115">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="6518e-116">Per creare la pipeline del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6518e-116">To Create the Dataflow Pipeline</span></span>  
  
1. <span data-ttu-id="6518e-117">Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="6518e-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2. <span data-ttu-id="6518e-118">Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6518e-118">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` statements (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3. <span data-ttu-id="6518e-119">Aggiungere la classe `WorkItem` come un tipo interno della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6518e-119">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4. <span data-ttu-id="6518e-120">Aggiungere i membri dei dati seguenti alla classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6518e-120">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5. <span data-ttu-id="6518e-121">Aggiungere il metodo `CreatePipeline` seguente alla classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6518e-121">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="6518e-122">Poiché i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono usati nell'interfaccia utente, è importante che queste azioni si verifichino nel thread di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6518e-122">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="6518e-123">A questo scopo, durante la costruzione ciascuno di questi oggetti fornisce un oggetto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> la cui proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> è impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6518e-123">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6518e-124">Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="6518e-124">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="6518e-125">Poiché il costruttore `Form1` viene chiamato dal thread dell'interfaccia utente, le azioni per i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono eseguite anche nel thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6518e-125">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="6518e-126">Questo esempio imposta la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> durante la costruzione dei membri della pipeline.</span><span class="sxs-lookup"><span data-stu-id="6518e-126">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="6518e-127">Poiché la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> annulla definitivamente l'esecuzione del blocco del flusso di dati, l'intera pipeline deve essere ricreata dopo che l'utente annulla l'operazione e quindi vuole aggiungere più elementi di lavoro alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="6518e-127">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="6518e-128">Per un esempio che mostra un modo alternativo per annullare un blocco del flusso di dati per poter eseguire un altro lavoro dopo che viene annullata un'operazione, vedere [Walkthrough: Using Dataflow in a Windows Forms Application](walkthrough-using-dataflow-in-a-windows-forms-application.md) (Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="6518e-128">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="6518e-129">Connessione della pipeline del flusso di dati all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6518e-129">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="6518e-130">In questa sezione viene descritto come connettere la pipeline del flusso di dati all'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6518e-130">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="6518e-131">Sia la creazione della pipeline sia l'aggiunta di elementi di lavoro alla pipeline sono controllate dal gestore eventi tramite il pulsante **Aggiungi elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6518e-131">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="6518e-132">L'annullamento viene avviato dal pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="6518e-132">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="6518e-133">Quando l'utente fa clic su uno di questi pulsanti, l'azione appropriata viene avviata in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="6518e-133">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="6518e-134">Per connettere la pipeline del flusso di dati all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6518e-134">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1. <span data-ttu-id="6518e-135">Nella finestra di progettazione del form principale creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Aggiungi elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6518e-135">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2. <span data-ttu-id="6518e-136">Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Aggiungi elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6518e-136">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3. <span data-ttu-id="6518e-137">Nella finestra di progettazione del form principale creare un gestore eventi per il gestore eventi <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="6518e-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="6518e-138">Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="6518e-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="6518e-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="6518e-139">Example</span></span>  
 <span data-ttu-id="6518e-140">L'esempio seguente illustra il codice completo per Form1.cs (Form1.vb per Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6518e-140">The following example shows the complete code for Form1.cs (Form1.vb for Visual Basic).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="6518e-141">Nell'immagine riportata di seguito viene illustrata l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6518e-141">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="6518e-142">![Applicazione Windows Form](media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="6518e-142">![The Windows Forms Application](media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  

## <a name="see-also"></a><span data-ttu-id="6518e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6518e-143">See also</span></span>

- [<span data-ttu-id="6518e-144">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6518e-144">Dataflow</span></span>](dataflow-task-parallel-library.md)
