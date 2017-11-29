---
title: 'Procedura dettagliata: esecuzione di un''operazione in background'
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
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de485eb0b9c67ee9c3c897b6521971f50aaf751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="66d7a-102">Procedura dettagliata: esecuzione di un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="66d7a-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="66d7a-103">Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="66d7a-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="66d7a-104">Per un elenco completo del codice usato in questo esempio, vedere [procedura: eseguire un'operazione in Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="66d7a-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66d7a-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="66d7a-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="66d7a-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="66d7a-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="66d7a-107">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="66d7a-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="66d7a-108">Per eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="66d7a-108">To run an operation in the background</span></span>  
  
1.  <span data-ttu-id="66d7a-109">Il form attivo in Progettazione Windows Form, trascinare due <xref:System.Windows.Forms.Button> dei controlli di **della casella degli strumenti** al form e quindi impostare il `Name` e <xref:System.Windows.Forms.Control.Text%2A> le proprietà dei pulsanti in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66d7a-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="66d7a-110">Pulsante</span><span class="sxs-lookup"><span data-stu-id="66d7a-110">Button</span></span>|<span data-ttu-id="66d7a-111">Nome</span><span class="sxs-lookup"><span data-stu-id="66d7a-111">Name</span></span>|<span data-ttu-id="66d7a-112">Testo</span><span class="sxs-lookup"><span data-stu-id="66d7a-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="66d7a-113">**Start**</span><span class="sxs-lookup"><span data-stu-id="66d7a-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="66d7a-114">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="66d7a-114">**Cancel**</span></span>|  
  
2.  <span data-ttu-id="66d7a-115">Aprire il **della casella degli strumenti**, fare clic su di **componenti** scheda e quindi trascinare il <xref:System.ComponentModel.BackgroundWorker> componente al form.</span><span class="sxs-lookup"><span data-stu-id="66d7a-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="66d7a-116">Il `backgroundWorker1` componente viene visualizzato nel **sulla barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="66d7a-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3.  <span data-ttu-id="66d7a-117">Nel **proprietà** finestra, impostare il <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="66d7a-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4.  <span data-ttu-id="66d7a-118">Nel **proprietà** finestra, fare clic su di **eventi** pulsante e quindi fare doppio clic sul <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gli eventi per creare gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="66d7a-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5.  <span data-ttu-id="66d7a-119">Inserire il codice nel tempo la <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="66d7a-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6.  <span data-ttu-id="66d7a-120">Estrarre tutti i parametri richiesti per l'operazione dal <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs> parametro.</span><span class="sxs-lookup"><span data-stu-id="66d7a-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7.  <span data-ttu-id="66d7a-121">Assegnare il risultato del calcolo per il <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="66d7a-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="66d7a-122">Si tratta di verranno messe a disposizione il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="66d7a-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  <span data-ttu-id="66d7a-123">Inserire il codice per recuperare il risultato dell'operazione nel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="66d7a-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="66d7a-124">Implementare il metodo `TimeConsumingOperation`.</span><span class="sxs-lookup"><span data-stu-id="66d7a-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="66d7a-125">In Progettazione Windows Form, fare doppio clic su `startButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="66d7a-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="66d7a-126">Chiamare il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo il <xref:System.Windows.Forms.Control.Click> gestore eventi per `startButton`.</span><span class="sxs-lookup"><span data-stu-id="66d7a-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="66d7a-127">In Progettazione Windows Form, fare doppio clic su `cancelButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="66d7a-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="66d7a-128">Chiamare il <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodo il <xref:System.Windows.Forms.Control.Click> gestore eventi per `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="66d7a-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="66d7a-129">Nella parte superiore del file, importare gli spazi dei nomi System. ComponentModel e System. Threading.</span><span class="sxs-lookup"><span data-stu-id="66d7a-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="66d7a-130">Premere F6 per compilare la soluzione e quindi premere CTRL + F5 per eseguire l'applicazione all'esterno del debugger.</span><span class="sxs-lookup"><span data-stu-id="66d7a-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66d7a-131">Se si preme F5 per eseguire l'applicazione nel debugger, l'eccezione generata nel `TimeConsumingOperation` (metodo) viene rilevata e visualizzate dal debugger.</span><span class="sxs-lookup"><span data-stu-id="66d7a-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="66d7a-132">Quando si esegue l'applicazione all'esterno del debugger, il <xref:System.ComponentModel.BackgroundWorker> gestisce l'eccezione e lo memorizza nella cache nel <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> proprietà del <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="66d7a-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1.  <span data-ttu-id="66d7a-133">Fare clic sul **avviare** pulsante per eseguire un'operazione asincrona e quindi scegliere il **Annulla** pulsante per arrestare l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="66d7a-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="66d7a-134">Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="66d7a-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="66d7a-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="66d7a-135">Next Steps</span></span>  
  
-   <span data-ttu-id="66d7a-136">Implementare un form che segnala lo stato di avanzamento del processo di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="66d7a-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="66d7a-137">Per ulteriori informazioni, vedere [procedura: implementare un Form che usa un'operazione in Background](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="66d7a-137">For more information, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="66d7a-138">Implementare una classe che supporta il modello asincrono per i componenti.</span><span class="sxs-lookup"><span data-stu-id="66d7a-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="66d7a-139">Per ulteriori informazioni, vedere [implementazione del modello asincrono basato su eventi](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="66d7a-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d7a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66d7a-140">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="66d7a-141">Procedura: Implementare un form che esegue un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="66d7a-141">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="66d7a-142">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="66d7a-142">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="66d7a-143">BackgroundWorker (componente)</span><span class="sxs-lookup"><span data-stu-id="66d7a-143">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
