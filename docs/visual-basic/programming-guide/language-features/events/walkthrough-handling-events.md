---
title: Gestione degli eventi (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b4ad77b3b0236e762fc17b8aba9d34108c8d75b5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="eec33-102">Procedura dettagliata: gestione di eventi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eec33-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="eec33-103">Questo è il secondo di due argomenti che illustrano come usare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="eec33-104">Il primo argomento, [procedura dettagliata: dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), viene illustrato come dichiarare e generare eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="eec33-105">Questa sezione viene usato il modulo e una classe da tale procedura dettagliata per illustrare come gestire gli eventi quando si verificano.</span><span class="sxs-lookup"><span data-stu-id="eec33-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="eec33-106">Il `Widget` esempio di classe vengono utilizzate istruzioni di gestione degli eventi tradizionali.</span><span class="sxs-lookup"><span data-stu-id="eec33-106">The `Widget` class example uses traditional event-handling statements.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eec33-107">sono disponibili altre tecniche per l'utilizzo di eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-107"> provides other techniques for working with events.</span></span> <span data-ttu-id="eec33-108">Come esercizio, è possibile modificare questo esempio per utilizzare il `AddHandler` e `Handles` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="eec33-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="eec33-109">Gestire l'evento PercentDone della classe Widget</span><span class="sxs-lookup"><span data-stu-id="eec33-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="eec33-110">Inserire il codice seguente in `Form1`:</span><span class="sxs-lookup"><span data-stu-id="eec33-110">Place the following code in `Form1`:</span></span>  
  
     <span data-ttu-id="eec33-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span></span>  
  
     <span data-ttu-id="eec33-112">Il `WithEvents` la parola chiave specifica che la variabile `mWidget` viene utilizzata per gestire gli eventi di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-112">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="eec33-113">Specificare il tipo di oggetto, indicando il nome della classe da cui verrà creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-113">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="eec33-114">La variabile `mWidget` viene dichiarata in `Form1` poiché `WithEvents` variabili devono essere a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="eec33-114">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="eec33-115">Questo vale indipendentemente dal tipo di classe in cui sono contenute.</span><span class="sxs-lookup"><span data-stu-id="eec33-115">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="eec33-116">La variabile `mblnCancel` viene utilizzato per annullare il `LongTask` metodo.</span><span class="sxs-lookup"><span data-stu-id="eec33-116">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="eec33-117">Scrittura di codice per gestire un evento</span><span class="sxs-lookup"><span data-stu-id="eec33-117">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="eec33-118">Non appena si dichiara una variabile utilizzando `WithEvents`, il nome della variabile viene visualizzato nell'elenco di riepilogo a discesa a sinistra della classe **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="eec33-118">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="eec33-119">Quando si seleziona `mWidget`, `Widget` gli eventi della classe vengono visualizzati nell'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="eec33-119">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="eec33-120">Se si seleziona un evento consente di visualizzare la corrispondente routine evento, con il prefisso `mWidget` e un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="eec33-120">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="eec33-121">Tutte le routine evento associate a un `WithEvents` variabile viene assegnato il nome di variabile come prefisso.</span><span class="sxs-lookup"><span data-stu-id="eec33-121">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="eec33-122">Per gestire un evento</span><span class="sxs-lookup"><span data-stu-id="eec33-122">To handle an event</span></span>  
  
1.  <span data-ttu-id="eec33-123">Selezionare `mWidget` dall'elenco di riepilogo a discesa a sinistra nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="eec33-123">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="eec33-124">Selezionare il `PercentDone` evento dall'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="eec33-124">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="eec33-125">Il **Editor di codice** apre il `mWidget_PercentDone` routine evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-125">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eec33-126">Il **Editor di codice** è utile, ma non obbligatorio, per l'inserimento di nuovi gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-126">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="eec33-127">In questa procedura dettagliata, è più semplice copiare i gestori eventi direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="eec33-127">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="eec33-128">Aggiungere il codice seguente al gestore eventi `mWidget_PercentDone`:</span><span class="sxs-lookup"><span data-stu-id="eec33-128">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     <span data-ttu-id="eec33-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span></span>  
  
     <span data-ttu-id="eec33-130">Ogni volta che il `PercentDone` evento viene generato, la routine evento Visualizza la percentuale di completamento in un `Label` controllo.</span><span class="sxs-lookup"><span data-stu-id="eec33-130">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="eec33-131">Il `DoEvents` metodo consente di ridisegnare l'etichetta e offre inoltre all'utente la possibilità di scegliere il **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="eec33-131">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="eec33-132">Aggiungere il codice seguente per il `Button2_Click` gestore dell'evento:</span><span class="sxs-lookup"><span data-stu-id="eec33-132">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     <span data-ttu-id="eec33-133">[!code-vb[6 VbVbcnWalkthroughDeclaringAndRaisingEvents](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span></span>  
  
 <span data-ttu-id="eec33-134">Se l'utente fa clic il **Annulla** pulsante durante `LongTask` è in esecuzione, il `Button2_Click` eventi viene eseguito non appena il `DoEvents` istruzione consente l'elaborazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-134">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="eec33-135">La variabile a livello di classe `mblnCancel` è impostato su `True`e `mWidget_PercentDone` evento quindi verifica l'evento e imposta il `ByRef Cancel` argomento `True`.</span><span class="sxs-lookup"><span data-stu-id="eec33-135">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="eec33-136">Una variabile WithEvents la connessione a un oggetto</span><span class="sxs-lookup"><span data-stu-id="eec33-136">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="eec33-137">`Form1`è ora configurato per gestire un `Widget` eventi dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-137">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="eec33-138">È ora per trovare un `Widget` da qualche parte.</span><span class="sxs-lookup"><span data-stu-id="eec33-138">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="eec33-139">Quando si dichiara una variabile `WithEvents` in fase di progettazione non è associato alcun oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-139">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="eec33-140">Oggetto `WithEvents` variabile è esattamente come qualsiasi altra variabile di oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-140">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="eec33-141">È necessario creare un oggetto e assegnare un riferimento a esso con il `WithEvents` variabile.</span><span class="sxs-lookup"><span data-stu-id="eec33-141">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="eec33-142">Per creare un oggetto e assegnare un riferimento a esso</span><span class="sxs-lookup"><span data-stu-id="eec33-142">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="eec33-143">Selezionare **(eventi Form1)** dall'elenco di riepilogo a discesa a sinistra nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="eec33-143">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="eec33-144">Selezionare il `Load` evento dall'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="eec33-144">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="eec33-145">Il **Editor di codice** apre il `Form1_Load` routine evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-145">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="eec33-146">Aggiungere il codice seguente per il `Form1_Load` routine evento per creare il `Widget`:</span><span class="sxs-lookup"><span data-stu-id="eec33-146">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     <span data-ttu-id="eec33-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span></span>  
  
 <span data-ttu-id="eec33-148">Quando viene eseguito questo codice, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] crea un `Widget` dell'oggetto e si connette gli eventi per le routine evento associate a `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="eec33-148">When this code executes, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="eec33-149">Da quel momento, ogni volta che il `Widget` genera il `PercentDone` evento, il `mWidget_PercentDone` viene eseguita la routine evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-149">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="eec33-150">Per chiamare il metodo LongTask</span><span class="sxs-lookup"><span data-stu-id="eec33-150">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="eec33-151">Aggiungere il codice seguente al gestore eventi `Button1_Click`:</span><span class="sxs-lookup"><span data-stu-id="eec33-151">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     <span data-ttu-id="eec33-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span></span>  
  
 <span data-ttu-id="eec33-153">Prima di `LongTask` metodo viene chiamato, l'etichetta che visualizza la percentuale di completamento deve essere inizializzato e a livello di classe `Boolean` flag di annullamento del metodo deve essere impostato su `False`.</span><span class="sxs-lookup"><span data-stu-id="eec33-153">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="eec33-154">`LongTask`viene chiamato con una durata di attività pari a 12,2 secondi.</span><span class="sxs-lookup"><span data-stu-id="eec33-154">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="eec33-155">Il `PercentDone` evento viene generato una volta ogni un terzo di secondo.</span><span class="sxs-lookup"><span data-stu-id="eec33-155">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="eec33-156">Ogni volta che viene generato l'evento, il `mWidget_PercentDone` viene eseguita la routine evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-156">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="eec33-157">Quando `LongTask` viene eseguita, `mblnCancel` viene verificato se `LongTask` è stato completato correttamente, o se è stato arrestato perché `mblnCancel` è stata impostata su `True`.</span><span class="sxs-lookup"><span data-stu-id="eec33-157">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="eec33-158">La percentuale di completamento viene aggiornata solo nel caso precedente.</span><span class="sxs-lookup"><span data-stu-id="eec33-158">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="eec33-159">Per eseguire il programma</span><span class="sxs-lookup"><span data-stu-id="eec33-159">To run the program</span></span>  
  
1.  <span data-ttu-id="eec33-160">Premere F5 per attivare il progetto in modalità di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eec33-160">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="eec33-161">Fare clic su di **Avvia attività** pulsante.</span><span class="sxs-lookup"><span data-stu-id="eec33-161">Click the **Start Task** button.</span></span> <span data-ttu-id="eec33-162">Ogni volta che il `PercentDone` viene generato l'evento, l'etichetta viene aggiornata con la percentuale di completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="eec33-162">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="eec33-163">Fare clic su di **Annulla** pulsante per arrestare l'attività.</span><span class="sxs-lookup"><span data-stu-id="eec33-163">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="eec33-164">Si noti che l'aspetto di **Annulla** pulsante Modifica immediatamente quando viene selezionata.</span><span class="sxs-lookup"><span data-stu-id="eec33-164">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="eec33-165">Il `Click` evento non può verificarsi fino a quando il `My.Application.DoEvents` istruzione consente l'elaborazione di eventi.</span><span class="sxs-lookup"><span data-stu-id="eec33-165">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eec33-166">Il `My.Application.DoEvents` metodo elabora gli eventi esattamente allo stesso modo del form.</span><span class="sxs-lookup"><span data-stu-id="eec33-166">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="eec33-167">Ad esempio, in questa procedura dettagliata, è necessario fare clic il **Annulla** due volte sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="eec33-167">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="eec33-168">Per consentire al modulo gestire gli eventi direttamente, è possibile utilizzare il multithreading.</span><span class="sxs-lookup"><span data-stu-id="eec33-168">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="eec33-169">Per ulteriori informazioni, vedere [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="eec33-169">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="eec33-170">Può risultare utile eseguire il programma con F11 e scorrere il codice una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="eec33-170">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="eec33-171">È possibile visualizzare chiaramente come esecuzione entra `LongTask`, quindi brevemente viene `Form1` ogni volta che il `PercentDone` viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-171">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="eec33-172">Che cosa accadrebbe se, durante l'esecuzione torna nel codice di `Form1`, `LongTask` metodo viene chiamato?</span><span class="sxs-lookup"><span data-stu-id="eec33-172">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="eec33-173">Nel peggiore dei casi, potrebbe verificarsi un overflow dello stack se `LongTask` chiamate ogni volta che è stato generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="eec33-173">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="eec33-174">È possibile che la variabile `mWidget` per gestire gli eventi per un altro `Widget` assegnando un riferimento al nuovo oggetto `Widget` a `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="eec33-174">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="eec33-175">Infatti, è possibile che il codice in `Button1_Click` eseguire questa operazione ogni volta che si sceglie il pulsante.</span><span class="sxs-lookup"><span data-stu-id="eec33-175">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="eec33-176">Per gestire gli eventi per un widget diverso</span><span class="sxs-lookup"><span data-stu-id="eec33-176">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="eec33-177">Aggiungere la seguente riga di codice per il `Button1_Click` procedura, la riga che precede immediatamente `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="eec33-177">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     <span data-ttu-id="eec33-178">[!code-vb[9 VbVbcnWalkthroughDeclaringAndRaisingEvents](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="eec33-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span></span>  
  
 <span data-ttu-id="eec33-179">Il codice sopra riportato crea un nuovo `Widget` ogni volta che si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="eec33-179">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="eec33-180">Non appena il `LongTask` metodo viene completato, il riferimento il `Widget` viene rilasciato e `Widget` viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="eec33-180">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="eec33-181">Oggetto `WithEvents` variabile può contenere un solo riferimento oggetto alla volta, pertanto se assegnare un diverso `Widget` oggetto `mWidget`, precedente `Widget` non verranno gestiti non sono più eventi dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec33-181">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="eec33-182">Se `mWidget` è l'unica variabile di oggetto che contiene un riferimento alla precedente `Widget`, l'oggetto viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="eec33-182">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="eec33-183">Se si desidera gestire eventi da svariati `Widget` oggetti, utilizzare il `AddHandler` istruzione per elaborare gli eventi di ogni oggetto separatamente.</span><span class="sxs-lookup"><span data-stu-id="eec33-183">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eec33-184">È possibile dichiarare un numero `WithEvents` matrici di variabili necessarie `WithEvents` variabili non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="eec33-184">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec33-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eec33-185">See Also</span></span>  
 <span data-ttu-id="eec33-186">[Procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span><span class="sxs-lookup"><span data-stu-id="eec33-186">[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span></span>  
<span data-ttu-id="eec33-187"> [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="eec33-187"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
