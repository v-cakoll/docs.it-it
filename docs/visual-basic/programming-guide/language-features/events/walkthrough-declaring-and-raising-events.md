---
title: Dichiarazione e generazione di eventi
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 3da60014d7ac95189c5d56c3e339ff1b054a40dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405093"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="5c1dc-102">Procedura dettagliata: dichiarazione e generazione di eventi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c1dc-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="5c1dc-103">In questa procedura dettagliata viene illustrato come dichiarare e generare eventi per una classe denominata `Widget` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="5c1dc-104">Dopo aver completato i passaggi, potrebbe essere necessario leggere l'argomento complementare, [procedura dettagliata: gestione degli eventi](walkthrough-handling-events.md), che Mostra come usare gli eventi degli `Widget` oggetti per fornire informazioni sullo stato in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="5c1dc-105">Classe widget</span><span class="sxs-lookup"><span data-stu-id="5c1dc-105">The Widget Class</span></span>  
 <span data-ttu-id="5c1dc-106">Si supponga che nel momento in cui si dispone di una `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="5c1dc-107">La `Widget` classe dispone di un metodo che può richiedere molto tempo per l'esecuzione e si desidera che l'applicazione sia in grado di inserire un tipo di indicatore di completamento.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="5c1dc-108">Naturalmente, è possibile fare in modo che l' `Widget` oggetto mostri una finestra di dialogo percentuale di completamento, ma in ogni progetto in cui è stata usata la classe verrà bloccata la finestra di dialogo `Widget` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="5c1dc-109">Un principio efficace della progettazione degli oggetti consiste nel consentire all'applicazione che utilizza un oggetto di gestire l'interfaccia utente, a meno che l'intero scopo dell'oggetto non sia quello di gestire un modulo o una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="5c1dc-110">Lo scopo di `Widget` è quello di eseguire altre attività, quindi è preferibile aggiungere un `PercentDone` evento e consentire alla routine che chiama i `Widget` metodi di gestire l'evento e visualizzare gli aggiornamenti dello stato.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="5c1dc-111">L' `PercentDone` evento può inoltre fornire un meccanismo per annullare l'attività.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="5c1dc-112">Per compilare l'esempio di codice per questo argomento</span><span class="sxs-lookup"><span data-stu-id="5c1dc-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="5c1dc-113">Aprire un nuovo progetto di applicazione Windows Visual Basic e creare un modulo denominato `Form1` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="5c1dc-114">Aggiungere due pulsanti e un'etichetta a `Form1` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="5c1dc-115">Assegnare i nomi agli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="5c1dc-116">Oggetto</span><span class="sxs-lookup"><span data-stu-id="5c1dc-116">Object</span></span>|<span data-ttu-id="5c1dc-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5c1dc-117">Property</span></span>|<span data-ttu-id="5c1dc-118">Impostazione</span><span class="sxs-lookup"><span data-stu-id="5c1dc-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="5c1dc-119">Attività di avvio</span><span class="sxs-lookup"><span data-stu-id="5c1dc-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="5c1dc-120">Annulla</span><span class="sxs-lookup"><span data-stu-id="5c1dc-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="5c1dc-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5c1dc-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="5c1dc-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="5c1dc-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="5c1dc-123">Scegliere **Aggiungi classe** dal menu **progetto** per aggiungere una classe denominata `Widget.vb` al progetto.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="5c1dc-124">Per dichiarare un evento per la classe widget</span><span class="sxs-lookup"><span data-stu-id="5c1dc-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="5c1dc-125">Usare la `Event` parola chiave per dichiarare un evento nella `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="5c1dc-126">Si noti che un evento può `ByVal` avere `ByRef` argomenti e, `Widget` come `PercentDone` illustrato nell'evento:</span><span class="sxs-lookup"><span data-stu-id="5c1dc-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="5c1dc-127">Quando l'oggetto chiamante riceve un `PercentDone` evento, l' `Percent` argomento contiene la percentuale dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="5c1dc-128">L' `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c1dc-129">È possibile dichiarare gli argomenti dell'evento nello stesso modo in cui si eseguono gli argomenti delle procedure, con le eccezioni seguenti: gli eventi non possono avere `Optional` `ParamArray` argomenti o e gli eventi non hanno valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="5c1dc-130">L' `PercentDone` evento viene generato dal `LongTask` metodo della `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="5c1dc-131">`LongTask`accetta due argomenti: il periodo di tempo durante il quale il metodo tende a funzionare e l'intervallo di tempo minimo prima della `LongTask` pausa per generare l' `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="5c1dc-132">Per generare l'evento PercentDone</span><span class="sxs-lookup"><span data-stu-id="5c1dc-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="5c1dc-133">Per semplificare l'accesso alla `Timer` proprietà usata da questa classe, aggiungere un' `Imports` istruzione all'inizio della sezione delle dichiarazioni del modulo della classe, sopra l' `Class Widget` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="5c1dc-134">Aggiungere il codice seguente alla classe `Widget`:</span><span class="sxs-lookup"><span data-stu-id="5c1dc-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="5c1dc-135">Quando l'applicazione chiama il `LongTask` metodo, la `Widget` classe genera l' `PercentDone` evento ogni `MinimumInterval` secondi.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="5c1dc-136">Quando l'evento viene restituito, `LongTask` verifica se l' `Cancel` argomento è stato impostato su `True` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="5c1dc-137">Qui sono necessarie alcune dichiarazioni di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="5c1dc-138">Per semplicità, la `LongTask` procedura presuppone che si conosca in anticipo quanto tempo sarà necessario per l'attività.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="5c1dc-139">Questo non è il caso.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-139">This is almost never the case.</span></span> <span data-ttu-id="5c1dc-140">Suddividere le attività in blocchi di dimensioni pari può essere difficile e spesso ciò che interessa maggiormente agli utenti è semplicemente la quantità di tempo che trascorre prima che venga indicato che si sta verificando qualcosa.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="5c1dc-141">In questo esempio è possibile che si sia notato un altro difetto.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="5c1dc-142">La `Timer` proprietà restituisce il numero di secondi passati dalla mezzanotte, quindi l'applicazione viene bloccata se viene avviata immediatamente prima della mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="5c1dc-143">Un approccio più attento alla misurazione del tempo richiederebbe condizioni di limite, ad esempio in considerazione, oppure evitarle completamente, usando proprietà come `Now` .</span><span class="sxs-lookup"><span data-stu-id="5c1dc-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="5c1dc-144">Ora che la `Widget` classe può generare eventi, è possibile passare alla procedura dettagliata successiva.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="5c1dc-145">[Procedura dettagliata: gestione degli eventi](walkthrough-handling-events.md) illustra come usare `WithEvents` per associare un gestore eventi all' `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="5c1dc-145">[Walkthrough: Handling Events](walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1dc-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c1dc-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="5c1dc-147">Procedura dettagliata: gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="5c1dc-147">Walkthrough: Handling Events</span></span>](walkthrough-handling-events.md)
- [<span data-ttu-id="5c1dc-148">Events</span><span class="sxs-lookup"><span data-stu-id="5c1dc-148">Events</span></span>](index.md)
