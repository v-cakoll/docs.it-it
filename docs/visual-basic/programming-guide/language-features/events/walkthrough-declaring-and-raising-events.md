---
title: Dichiarazione e generazione di eventi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973090"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="cc0b5-102">Procedura dettagliata: Dichiarazione e generazione di eventi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc0b5-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="cc0b5-103">Questa procedura dettagliata illustra come dichiarare e generare eventi per una classe denominata `Widget`.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="cc0b5-104">Dopo aver completato i passaggi, è possibile leggere l'argomento complementare [procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), che mostra come usare gli eventi da `Widget` oggetti da fornire informazioni sullo stato in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="cc0b5-105">La classe di Widget</span><span class="sxs-lookup"><span data-stu-id="cc0b5-105">The Widget Class</span></span>  
 <span data-ttu-id="cc0b5-106">Si supponga che per il momento in cui è necessario un `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="cc0b5-107">Il `Widget` classe dispone di un metodo che può richiedere molto tempo per l'esecuzione e si vuole che l'applicazione sia in grado di venga visualizzato un indicatore di completamento.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="cc0b5-108">Naturalmente, è possibile apportare le `Widget` oggetto Mostra una finestra di dialogo percentuale di completamento, ma è quindi potrebbe bloccarsi con tale finestra di dialogo in tutti i progetti in cui è stato usato il `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="cc0b5-109">Una buona regola della progettazione di oggetti consiste nel consentire all'applicazione che usa un handle di oggetto dell'interfaccia utente, a meno che l'obiettivo finale dell'oggetto sia per la gestione di un form o finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="cc0b5-110">Lo scopo della `Widget` consiste nell'eseguire altre attività, è preferibile aggiungere un' `PercentDone` evento e lasciare che le procedure che chiama `Widget`di metodi gestiscono che gli aggiornamenti di stato di evento e la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="cc0b5-111">Il `PercentDone` evento può fornire anche un meccanismo per l'annullamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="cc0b5-112">Per compilare l'esempio di codice in questo argomento</span><span class="sxs-lookup"><span data-stu-id="cc0b5-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="cc0b5-113">Aprire un nuovo progetto applicazione Windows di Visual Basic e creare un form denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="cc0b5-114">Aggiungere due pulsanti e un'etichetta a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="cc0b5-115">Assegnare i nomi agli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="cc0b5-116">Oggetto</span><span class="sxs-lookup"><span data-stu-id="cc0b5-116">Object</span></span>|<span data-ttu-id="cc0b5-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cc0b5-117">Property</span></span>|<span data-ttu-id="cc0b5-118">Impostazione</span><span class="sxs-lookup"><span data-stu-id="cc0b5-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="cc0b5-119">Attività di avvio</span><span class="sxs-lookup"><span data-stu-id="cc0b5-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="cc0b5-120">Annulla</span><span class="sxs-lookup"><span data-stu-id="cc0b5-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="cc0b5-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="cc0b5-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="cc0b5-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="cc0b5-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="cc0b5-123">Nel **Project** menu, scegliere **Aggiungi classe** per aggiungere una classe denominata `Widget.vb` al progetto.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="cc0b5-124">Per dichiarare un evento per la classe di Widget</span><span class="sxs-lookup"><span data-stu-id="cc0b5-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="cc0b5-125">Usare la `Event` parola chiave per dichiarare un evento nel `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="cc0b5-126">Si noti che un evento può avere `ByVal` e `ByRef` gli argomenti, come `Widget`del `PercentDone` dimostrato dall'evento:</span><span class="sxs-lookup"><span data-stu-id="cc0b5-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="cc0b5-127">Quando l'oggetto chiamante riceve un' `PercentDone` evento, il `Percent` argomento contiene la percentuale di completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="cc0b5-128">Il `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc0b5-129">È possibile dichiarare argomenti dell'evento, come avviene gli argomenti di routine, con le eccezioni seguenti: Gli eventi non possono avere `Optional` o `ParamArray` argomenti e gli eventi non hanno valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="cc0b5-130">Il `PercentDone` evento viene generato dal `LongTask` metodo il `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="cc0b5-131">`LongTask` accetta due argomenti: il periodo di tempo il metodo finge di eseguire le operazioni e l'intervallo di tempo minimo prima che `LongTask` mette in pausa per generare il `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="cc0b5-132">Per generare l'evento PercentDone</span><span class="sxs-lookup"><span data-stu-id="cc0b5-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="cc0b5-133">Per semplificare l'accesso per il `Timer` proprietà utilizzata da questa classe, aggiungere un' `Imports` istruzione all'inizio della sezione delle dichiarazioni di modulo di classe, sopra il `Class Widget` istruzione.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="cc0b5-134">Aggiungere il codice seguente alla classe `Widget`:</span><span class="sxs-lookup"><span data-stu-id="cc0b5-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="cc0b5-135">Quando l'applicazione chiama il `LongTask` metodo, il `Widget` classe genera le `PercentDone` eventi ogni `MinimumInterval` secondi.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="cc0b5-136">Quando termina, l'evento `LongTask` verifica se il `Cancel` argomento è stato impostato su `True`.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="cc0b5-137">In questo caso, sono necessarie alcune dichiarazioni di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="cc0b5-138">Per semplicità, il `LongTask` procedura presuppone che si conosce in anticipo quanto tempo l'attività.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="cc0b5-139">Ciò avviene quasi mai.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-139">This is almost never the case.</span></span> <span data-ttu-id="cc0b5-140">Suddivisione in blocchi di dimensioni pari delle attività può essere difficile e spesso ciò che più interessa gli utenti è semplicemente la quantità di tempo trascorso prima che diventino un valore che indica che qualcosa è in corso.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="cc0b5-141">In questo esempio si potrebbe individua un difetto di un altro.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="cc0b5-142">Il `Timer` proprietà restituisce il numero di secondi trascorsi dalla mezzanotte; pertanto, l'applicazione si blocca se è stato avviato prima di mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="cc0b5-143">Un approccio più attenzione alla misurazione del tempo potrebbe tenere in considerazione o evitarli del tutto, utilizzando le proprietà, ad esempio `Now`.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="cc0b5-144">Ora che il `Widget` classe può generare eventi, è possibile spostare la successiva procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="cc0b5-145">[Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) illustra come usare `WithEvents` per associare un gestore eventi con il `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="cc0b5-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0b5-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc0b5-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="cc0b5-147">Procedura dettagliata: Gestione degli eventi</span><span class="sxs-lookup"><span data-stu-id="cc0b5-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="cc0b5-148">Eventi</span><span class="sxs-lookup"><span data-stu-id="cc0b5-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
