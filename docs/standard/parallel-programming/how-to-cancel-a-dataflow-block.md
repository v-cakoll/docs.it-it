---
title: 'Procedura: annullare un blocco di flussi di dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="ce6b5-102">Procedura: annullare un blocco di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="ce6b5-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="ce6b5-103">In questo documento viene dimostrato come abilitare l'annullamento nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="ce6b5-104">In questo esempio Windows Form viene usato per mostrare dove gli elementi di lavoro sono attivi in una pipeline del flusso di dati, nonché gli effetti dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ce6b5-105">La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6b5-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="ce6b5-106">Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="ce6b5-107">Per creare l'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce6b5-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="ce6b5-108">Creare un progetto **Windows Forms Application** di C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="ce6b5-109">Nei passaggi seguenti il progetto viene denominato `CancellationWinForms`.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="ce6b5-110">Nella finestra di progettazione di form per il form principale, Form1.cs (Form1. vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), aggiungere un <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="ce6b5-111">Aggiungere un <xref:System.Windows.Forms.ToolStripButton> controllo il <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ce6b5-112">Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> e <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà **aggiungere elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="ce6b5-113">Aggiungere un secondo <xref:System.Windows.Forms.ToolStripButton> controllo il <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ce6b5-114">Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà **Annulla**e <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> proprietà `False`.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="ce6b5-115">Aggiungere quattro <xref:System.Windows.Forms.ToolStripProgressBar> oggetti per il <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="ce6b5-116">Creazione della pipeline del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ce6b5-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="ce6b5-117">In questa sezione viene descritto come creare la pipeline del flusso di dati che elabora gli elementi di lavoro e aggiorna le barre di stato.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="ce6b5-118">Per creare la pipeline del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ce6b5-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="ce6b5-119">Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="ce6b5-120">Assicurarsi che in Form1.cs (Form1.vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) siano contenute le seguenti istruzioni `using` (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ce6b5-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="ce6b5-121">Aggiungere la classe `WorkItem` come un tipo interno della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="ce6b5-122">Aggiungere i membri dei dati seguenti alla classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="ce6b5-123">Aggiungere il metodo `CreatePipeline` seguente alla classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="ce6b5-124">Poiché i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono usati nell'interfaccia utente, è importante che queste azioni si verifichino nel thread di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="ce6b5-125">A tale scopo, durante la costruzione di questi oggetti forniscono ciascuna un <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> oggetto che ha il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> proprietà impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce6b5-126">Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="ce6b5-127">Poiché il costruttore `Form1` viene chiamato dal thread dell'interfaccia utente, le azioni per i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono eseguite anche nel thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="ce6b5-128">In questo esempio il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> proprietà quando costruisce i membri della pipeline.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="ce6b5-129">Poiché il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> proprietà Annulla definitivamente bloccare l'esecuzione del flusso di dati, è necessario ricreare l'intera pipeline dopo che l'utente annulla l'operazione e quindi si desidera aggiungere più elementi di lavoro per la pipeline.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="ce6b5-130">Per un esempio che mostra un modo alternativo per annullare un blocco del flusso di dati per poter eseguire un altro lavoro dopo che viene annullata un'operazione, vedere [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md) (Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="ce6b5-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ce6b5-131">Connessione della pipeline del flusso di dati all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ce6b5-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="ce6b5-132">In questa sezione viene descritto come connettere la pipeline del flusso di dati all'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="ce6b5-133">Sia la creazione della pipeline sia l'aggiunta di elementi di lavoro alla pipeline sono controllate dal gestore eventi tramite il pulsante **Aggiungi elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="ce6b5-134">L'annullamento viene avviato dal pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="ce6b5-135">Quando l'utente fa clic su uno di questi pulsanti, l'azione appropriata viene avviata in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ce6b5-136">Per connettere la pipeline del flusso di dati all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ce6b5-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="ce6b5-137">Nella finestra di progettazione di form per il form principale, creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento per il **aggiungere elementi di lavoro** pulsante.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="ce6b5-138">Implementare il <xref:System.Windows.Forms.ToolStripItem.Click> evento per il **aggiungere elementi di lavoro** pulsante.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="ce6b5-139">Nella finestra di progettazione di form per il form principale, creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per il **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="ce6b5-140">Implementare il <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per il **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="ce6b5-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce6b5-141">Example</span></span>  
 <span data-ttu-id="ce6b5-142">Nell'esempio seguente viene illustrato il codice completo per Form1.cs (Form1.vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ce6b5-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="ce6b5-143">Nell'immagine riportata di seguito viene illustrata l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce6b5-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="ce6b5-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="ce6b5-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ce6b5-145">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ce6b5-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce6b5-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce6b5-146">See Also</span></span>  
 [<span data-ttu-id="ce6b5-147">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ce6b5-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
