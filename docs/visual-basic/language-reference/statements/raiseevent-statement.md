---
title: Istruzione RaiseEvent
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 46b93c060a12d82b34dafdf3aa4ea677df6f54cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404291"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="2ff4a-102">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="2ff4a-102">RaiseEvent Statement</span></span>
<span data-ttu-id="2ff4a-103">Attiva un evento dichiarato a livello di modulo all'interno di una classe, un form o un documento.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff4a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ff4a-104">Syntax</span></span>  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="2ff4a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2ff4a-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="2ff4a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-106">Required.</span></span> <span data-ttu-id="2ff4a-107">Nome dell'evento da attivare.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="2ff4a-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-108">Optional.</span></span> <span data-ttu-id="2ff4a-109">Elenco delimitato da virgole di variabili, matrici o espressioni.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="2ff4a-110">L' `argumentlist` argomento deve essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="2ff4a-111">Se non è presente alcun argomento, le parentesi devono essere omesse.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ff4a-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="2ff4a-112">Remarks</span></span>  
 <span data-ttu-id="2ff4a-113">Il valore richiesto `eventname` è il nome di un evento dichiarato all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="2ff4a-114">Segue Visual Basic convenzioni di denominazione delle variabili.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="2ff4a-115">Se l'evento non è stato dichiarato all'interno del modulo in cui viene generato, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="2ff4a-116">Nel frammento di codice seguente viene illustrata una dichiarazione di evento e una procedura in cui viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="2ff4a-117">Non è possibile usare `RaiseEvent` per generare eventi non dichiarati in modo esplicito nel modulo.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="2ff4a-118">Ad esempio, tutti i form ereditano un <xref:System.Windows.Forms.Control.Click> evento da e non <xref:System.Windows.Forms.Form?displayProperty=nameWithType> possono essere generati utilizzando `RaiseEvent` in un formato derivato.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="2ff4a-119">Se si dichiara un `Click` evento nel modulo modulo, viene ombreggiato l'evento del modulo <xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="2ff4a-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="2ff4a-120">È comunque possibile richiamare l'evento del form chiamando <xref:System.Windows.Forms.Control.Click> il <xref:System.Windows.Forms.Control.OnClick%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="2ff4a-121">Per impostazione predefinita, un evento definito in Visual Basic genera i relativi gestori eventi nell'ordine in cui vengono stabilite le connessioni.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="2ff4a-122">Poiché gli eventi possono avere `ByRef` parametri, un processo che si connette in ritardo può ricevere parametri che sono stati modificati da un gestore eventi precedente.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="2ff4a-123">Dopo l'esecuzione dei gestori di eventi, il controllo viene restituito alla subroutine che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff4a-124">Gli eventi non condivisi non devono essere generati all'interno del costruttore della classe in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="2ff4a-125">Sebbene tali eventi non causino errori in fase di esecuzione, potrebbero non essere rilevati dai gestori eventi associati.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="2ff4a-126">Usare il `Shared` modificatore per creare un evento condiviso se è necessario generare un evento da un costruttore.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff4a-127">È possibile modificare il comportamento predefinito degli eventi definendo un evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="2ff4a-128">Per gli eventi personalizzati, l' `RaiseEvent` istruzione richiama la funzione di `RaiseEvent` accesso dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="2ff4a-129">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2ff4a-129">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ff4a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ff4a-130">Example</span></span>  
 <span data-ttu-id="2ff4a-131">Negli esempi seguenti, gli eventi vengono usati per il conto alla rovescia dei secondi, da 10 a 0.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="2ff4a-132">Nel codice vengono illustrati diversi metodi, proprietà e istruzioni correlati agli eventi, inclusa l' `RaiseEvent` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="2ff4a-133">La classe che genera un evento viene definita origine e i metodi che lo elaborano vengono definiti gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="2ff4a-134">Un'origine eventi può disporre di più gestori per gli eventi generati.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="2ff4a-135">Quando la classe genera l'evento, lo stesso evento viene generato in tutte le classi per cui è stato scelto di gestire eventi per tale istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="2ff4a-136">Nell'esempio vengono usati anche un form (`Form1`) con un pulsante (`Button1`) e una casella di testo (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="2ff4a-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="2ff4a-137">Quando si fa clic sul pulsante, nella prima casella di testo viene visualizzato il conto alla rovescia dei secondi da 10 a 0.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="2ff4a-138">Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".</span><span class="sxs-lookup"><span data-stu-id="2ff4a-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="2ff4a-139">Il codice di `Form1` specifica gli stati di inizio e fine del form.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="2ff4a-140">Contiene inoltre il codice eseguito quando vengono generati gli eventi.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="2ff4a-141">Per usare questo esempio, aprire un nuovo progetto di applicazione Windows, aggiungere un pulsante denominato `Button1` e una casella di testo denominata `TextBox1` al form principale, denominato `Form1` .</span><span class="sxs-lookup"><span data-stu-id="2ff4a-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="2ff4a-142">Fare quindi clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="2ff4a-143">Aggiungere una `WithEvents` variabile alla sezione delle dichiarazioni della `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="2ff4a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ff4a-144">Example</span></span>  
 <span data-ttu-id="2ff4a-145">Aggiungere il codice seguente al codice per `Form1`:</span><span class="sxs-lookup"><span data-stu-id="2ff4a-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="2ff4a-146">Sostituire eventuali procedure duplicate che possono esistere, ad esempio `Form_Load` o `Button_Click` .</span><span class="sxs-lookup"><span data-stu-id="2ff4a-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="2ff4a-147">Premere F5 per eseguire l'esempio precedente e fare clic sul pulsante **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="2ff4a-148">Nella prima casella di testo viene avviato il conto alla rovescia dei secondi.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="2ff4a-149">Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".</span><span class="sxs-lookup"><span data-stu-id="2ff4a-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff4a-150">Il `My.Application.DoEvents` metodo non elabora gli eventi esattamente allo stesso modo del modulo.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="2ff4a-151">Per consentire al modulo di gestire direttamente gli eventi, è possibile utilizzare il multithreading.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="2ff4a-152">Per altre informazioni, vedere [Threading gestito](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ff4a-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff4a-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ff4a-153">See also</span></span>

- [<span data-ttu-id="2ff4a-154">Events</span><span class="sxs-lookup"><span data-stu-id="2ff4a-154">Events</span></span>](../../programming-guide/language-features/events/index.md)
- [<span data-ttu-id="2ff4a-155">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="2ff4a-155">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="2ff4a-156">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="2ff4a-156">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="2ff4a-157">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="2ff4a-157">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="2ff4a-158">Selettori</span><span class="sxs-lookup"><span data-stu-id="2ff4a-158">Handles</span></span>](handles-clause.md)
