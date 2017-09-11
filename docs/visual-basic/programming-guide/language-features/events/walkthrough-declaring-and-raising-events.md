---
title: Dichiarazione e generazione di eventi (Visual Basic) | Documenti di Microsoft
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: eca112aca39bd998697d379a1705845e8f607367
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="44734-102">Procedura dettagliata: dichiarazione e generazione di eventi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44734-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="44734-103">Questa procedura dettagliata viene illustrato come dichiarare e generare eventi per una classe denominata `Widget`.</span><span class="sxs-lookup"><span data-stu-id="44734-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="44734-104">Dopo aver completato i passaggi, è possibile leggere l'argomento correlato, [procedura dettagliata: gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), che illustra come utilizzare gli eventi da `Widget` gli oggetti da fornire informazioni sullo stato in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="44734-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="44734-105">La classe Widget</span><span class="sxs-lookup"><span data-stu-id="44734-105">The Widget Class</span></span>  
 <span data-ttu-id="44734-106">Si supponga che si dispone di un `Widget` (classe).</span><span class="sxs-lookup"><span data-stu-id="44734-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="44734-107">La `Widget` classe dispone di un metodo che può richiedere un tempo di esecuzione e si desidera che l'applicazione in grado di venga visualizzato un indicatore di completamento.</span><span class="sxs-lookup"><span data-stu-id="44734-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="44734-108">Naturalmente, è possibile apportare il `Widget` oggetto visualizzare una finestra di dialogo percentuale di completamento, ma quindi verrebbe con tale finestra di dialogo in ogni progetto in cui viene utilizzata la `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="44734-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="44734-109">Una buona regola della progettazione di oggetti consiste nel consentire all'applicazione che utilizza un handle di oggetto dell'interfaccia utente, a meno che non è lo scopo dell'oggetto per la gestione di un modulo o finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="44734-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="44734-110">Lo scopo di `Widget` per eseguire altre attività, pertanto è consigliabile aggiungere un `PercentDone` evento e consentire alla routine che chiama `Widget`di metodi gestiscono che lo stato di evento e di visualizzare gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="44734-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="44734-111">Il `PercentDone` eventi possono anche fornire un meccanismo per l'annullamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="44734-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="44734-112">Per compilare l'esempio di codice per questo argomento</span><span class="sxs-lookup"><span data-stu-id="44734-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="44734-113">Aprire un nuovo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applicazione Windows di progetto e creare un form denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="44734-113">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="44734-114">Aggiungere due pulsanti e un'etichetta a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="44734-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="44734-115">Denominare gli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="44734-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="44734-116">Oggetto</span><span class="sxs-lookup"><span data-stu-id="44734-116">Object</span></span>|<span data-ttu-id="44734-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="44734-117">Property</span></span>|<span data-ttu-id="44734-118">Impostazione</span><span class="sxs-lookup"><span data-stu-id="44734-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="44734-119">Attività di avvio</span><span class="sxs-lookup"><span data-stu-id="44734-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="44734-120">Annulla</span><span class="sxs-lookup"><span data-stu-id="44734-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="44734-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="44734-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="44734-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="44734-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="44734-123">Nel **progetto** menu, scegliere **Aggiungi classe** per aggiungere una classe denominata `Widget.vb` al progetto.</span><span class="sxs-lookup"><span data-stu-id="44734-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="44734-124">Per dichiarare un evento per la classe Widget</span><span class="sxs-lookup"><span data-stu-id="44734-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="44734-125">Utilizzare il `Event` parola chiave per dichiarare un evento nella `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="44734-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="44734-126">Si noti che un evento può avere `ByVal` e `ByRef` argomenti, come `Widget`del `PercentDone` dimostrato dall'evento:</span><span class="sxs-lookup"><span data-stu-id="44734-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     <span data-ttu-id="44734-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="44734-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span></span>  
  
 <span data-ttu-id="44734-128">Quando l'oggetto chiamante riceve un `PercentDone` evento, il `Percent` argomento contiene la percentuale di completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="44734-128">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="44734-129">Il `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="44734-129">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44734-130">È possibile dichiarare argomenti dell'evento come argomenti di procedure, con le seguenti eccezioni: gli eventi devono avere `Optional` o `ParamArray` gli argomenti e gli eventi non dispongono di valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="44734-130">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="44734-131">Il `PercentDone` evento viene generato dal `LongTask` metodo la `Widget` classe.</span><span class="sxs-lookup"><span data-stu-id="44734-131">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="44734-132">`LongTask`accetta due argomenti: il periodo di tempo apparentemente richiesto dal metodo eseguire le operazioni e l'intervallo di tempo minimo prima `LongTask` pause per generare il `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="44734-132">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="44734-133">Per generare l'evento PercentDone</span><span class="sxs-lookup"><span data-stu-id="44734-133">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="44734-134">Per semplificare l'accesso per il `Timer` proprietà utilizzata da questa classe, aggiungere un `Imports` istruzione all'inizio della sezione relativa alle dichiarazioni del modulo di classe, sopra il `Class Widget` istruzione.</span><span class="sxs-lookup"><span data-stu-id="44734-134">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     <span data-ttu-id="44734-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="44734-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span></span>  
  
2.  <span data-ttu-id="44734-136">Aggiungere il codice seguente alla classe `Widget` :</span><span class="sxs-lookup"><span data-stu-id="44734-136">Add the following code to the `Widget` class:</span></span>  
  
     <span data-ttu-id="44734-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents n.&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="44734-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span></span>  
  
 <span data-ttu-id="44734-138">Quando l'applicazione chiama il `LongTask` (metodo), il `Widget` classe genera il `PercentDone` evento ogni `MinimumInterval` secondi.</span><span class="sxs-lookup"><span data-stu-id="44734-138">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="44734-139">Quando termina, l'evento `LongTask` verifica se il `Cancel` argomento è stato impostato su `True`.</span><span class="sxs-lookup"><span data-stu-id="44734-139">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="44734-140">Di seguito sono necessarie alcune osservazioni.</span><span class="sxs-lookup"><span data-stu-id="44734-140">A few disclaimers are necessary here.</span></span> <span data-ttu-id="44734-141">Per semplicità, la `LongTask` procedura si presuppone che si conosce in anticipo la durata dell'attività.</span><span class="sxs-lookup"><span data-stu-id="44734-141">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="44734-142">Ciò avviene quasi mai.</span><span class="sxs-lookup"><span data-stu-id="44734-142">This is almost never the case.</span></span> <span data-ttu-id="44734-143">Suddivisione delle attività in blocchi di dimensioni pari può essere difficile e spesso gli utenti desiderano soprattutto è semplicemente la quantità di tempo di attesa prima di ottenere un'indicazione che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="44734-143">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="44734-144">In questo esempio si potrebbe individua un difetto di un altro.</span><span class="sxs-lookup"><span data-stu-id="44734-144">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="44734-145">Il `Timer` proprietà restituisce il numero di secondi trascorsi dalla mezzanotte; pertanto, l'applicazione ottiene bloccata se è stato avviato prima di mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="44734-145">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="44734-146">Un approccio più precisa per misurare il tempo necessario tenere in considerazione o evitarli del tutto, utilizzando le proprietà, ad esempio `Now`.</span><span class="sxs-lookup"><span data-stu-id="44734-146">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="44734-147">Ora che la `Widget` classe può generare eventi, è possibile spostare la successiva procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="44734-147">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="44734-148">[Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) viene illustrato come utilizzare `WithEvents` per associare un gestore eventi con il `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="44734-148">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44734-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44734-149">See Also</span></span>  
 <span data-ttu-id="44734-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span><span class="sxs-lookup"><span data-stu-id="44734-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span></span>   
 <span data-ttu-id="44734-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="44734-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span></span>   
<span data-ttu-id="44734-152"> [Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span><span class="sxs-lookup"><span data-stu-id="44734-152"> [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span></span>  
<span data-ttu-id="44734-153"> [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="44734-153"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
