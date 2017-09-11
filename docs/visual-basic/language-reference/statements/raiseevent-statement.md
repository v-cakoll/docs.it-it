---
title: Istruzione RaiseEvent | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 6a0cf1c5635335f22fddd57c7dd2baaeca6ddd23
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="raiseevent-statement"></a><span data-ttu-id="f5842-102">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="f5842-102">RaiseEvent Statement</span></span>
<span data-ttu-id="f5842-103">Trigger di un evento dichiarato a livello di modulo in una classe, un modulo o un documento.</span><span class="sxs-lookup"><span data-stu-id="f5842-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5842-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5842-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="f5842-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f5842-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="f5842-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f5842-106">Required.</span></span> <span data-ttu-id="f5842-107">Nome dell'evento da attivare.</span><span class="sxs-lookup"><span data-stu-id="f5842-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="f5842-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f5842-108">Optional.</span></span> <span data-ttu-id="f5842-109">Elenco delimitato da virgole di variabili, matrici o espressioni.</span><span class="sxs-lookup"><span data-stu-id="f5842-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="f5842-110">Il `argumentlist` argomento deve essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="f5842-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="f5842-111">Se non sono presenti argomenti, è necessario omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="f5842-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5842-112">Note</span><span class="sxs-lookup"><span data-stu-id="f5842-112">Remarks</span></span>  
 <span data-ttu-id="f5842-113">Obbligatoria `eventname` è il nome di un evento dichiarato all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="f5842-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="f5842-114">Ne consegue convenzioni di denominazione di variabili di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f5842-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="f5842-115">Se l'evento non è stata dichiarata all'interno del modulo in cui viene generato, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="f5842-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="f5842-116">Nel frammento di codice seguente viene illustrata una dichiarazione di evento e una procedura in cui viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="f5842-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 <span data-ttu-id="f5842-117">[!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f5842-117">[!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="f5842-118">Non è possibile utilizzare `RaiseEvent` per generare eventi non vengono dichiarati in modo esplicito nel modulo.</span><span class="sxs-lookup"><span data-stu-id="f5842-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="f5842-119">Ad esempio, tutti i form ereditano un <xref:System.Windows.Forms.Control.Click>evento <xref:System.Windows.Forms.Form?displayProperty=fullName>, non può essere generato utilizzando `RaiseEvent` in un form derivato.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="f5842-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=fullName>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="f5842-120">Se si dichiara un `Click` evento nel modulo del form, esso nasconde il modulo <xref:System.Windows.Forms.Control.Click>eventi.</xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="f5842-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="f5842-121">È comunque possibile richiamare il modulo <xref:System.Windows.Forms.Control.Click>evento chiamando il <xref:System.Windows.Forms.Control.OnClick%2A>(metodo).</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="f5842-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="f5842-122">Per impostazione predefinita, un evento definito in Visual Basic genera gestori eventi nell'ordine che vengono stabilite le connessioni.</span><span class="sxs-lookup"><span data-stu-id="f5842-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="f5842-123">Poiché gli eventi possono essere `ByRef` parametri, un processo collegato in seguito possono essere passati parametri che sono stati modificati da un gestore eventi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f5842-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="f5842-124">Dopo che i gestori di eventi è stato eseguito, il controllo viene restituito alla subroutine che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="f5842-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5842-125">Gli eventi non condivisi non devono essere generati all'interno del costruttore della classe in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="f5842-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="f5842-126">Anche se tali eventi non causano errori di run-time, potrebbero non riuscire a essere rilevate dai gestori eventi associati.</span><span class="sxs-lookup"><span data-stu-id="f5842-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="f5842-127">Utilizzare il `Shared` modificatore per creare un evento condiviso se è necessario generare un evento da un costruttore.</span><span class="sxs-lookup"><span data-stu-id="f5842-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5842-128">È possibile modificare il comportamento predefinito di eventi mediante la definizione di un evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f5842-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="f5842-129">Per gli eventi personalizzati, il `RaiseEvent` istruzione richiama l'evento `RaiseEvent` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="f5842-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="f5842-130">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f5842-130">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5842-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5842-131">Example</span></span>  
 <span data-ttu-id="f5842-132">Negli esempi seguenti, gli eventi vengono usati per il conto alla rovescia dei secondi, da 10 a 0.</span><span class="sxs-lookup"><span data-stu-id="f5842-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="f5842-133">Il codice illustra alcune delle relative agli eventi di metodi, proprietà e le istruzioni, inclusa la `RaiseEvent` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f5842-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="f5842-134">La classe che genera un evento viene definita origine e i metodi che lo elaborano vengono definiti gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="f5842-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="f5842-135">Un'origine eventi può disporre di più gestori per gli eventi generati.</span><span class="sxs-lookup"><span data-stu-id="f5842-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="f5842-136">Quando la classe genera l'evento, lo stesso evento viene generato in tutte le classi per cui è stato scelto di gestire eventi per tale istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5842-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="f5842-137">Nell'esempio vengono usati anche un form (`Form1`) con un pulsante (`Button1`) e una casella di testo (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="f5842-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="f5842-138">Quando si fa clic sul pulsante, nella prima casella di testo viene visualizzato il conto alla rovescia dei secondi da 10 a 0.</span><span class="sxs-lookup"><span data-stu-id="f5842-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="f5842-139">Al termine dei&10; secondi, nella prima casella di testo viene visualizzato "Done".</span><span class="sxs-lookup"><span data-stu-id="f5842-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="f5842-140">Il codice di `Form1` specifica gli stati di inizio e fine del form.</span><span class="sxs-lookup"><span data-stu-id="f5842-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="f5842-141">Contiene inoltre il codice eseguito quando vengono generati gli eventi.</span><span class="sxs-lookup"><span data-stu-id="f5842-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="f5842-142">Per utilizzare questo esempio, aprire un nuovo progetto applicazione Windows, aggiungere un pulsante denominato `Button1` e una casella di testo denominato `TextBox1` per il form principale, denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="f5842-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="f5842-143">Quindi fare doppio clic su form e fare clic su **Visualizza codice** per aprire l'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="f5842-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="f5842-144">Aggiungere un `WithEvents` sezione delle dichiarazioni di variabile di `Form1` (classe).</span><span class="sxs-lookup"><span data-stu-id="f5842-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 <span data-ttu-id="f5842-145">[!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f5842-145">[!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5842-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5842-146">Example</span></span>  
 <span data-ttu-id="f5842-147">Aggiungere il codice seguente al codice per `Form1`:</span><span class="sxs-lookup"><span data-stu-id="f5842-147">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="f5842-148">Sostituire eventuali procedure duplicate esistenti, ad esempio `Form_Load`, o `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="f5842-148">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 <span data-ttu-id="f5842-149">[!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f5842-149">[!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="f5842-150">Premere F5 per eseguire l'esempio precedente, quindi fare clic sul pulsante con etichettato **avviare**.</span><span class="sxs-lookup"><span data-stu-id="f5842-150">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="f5842-151">Nella prima casella di testo viene avviato il conto alla rovescia dei secondi.</span><span class="sxs-lookup"><span data-stu-id="f5842-151">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="f5842-152">Al termine dei&10; secondi, nella prima casella di testo viene visualizzato "Done".</span><span class="sxs-lookup"><span data-stu-id="f5842-152">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5842-153">Il `My.Application.DoEvents` metodo elabora gli eventi esattamente allo stesso modo del form.</span><span class="sxs-lookup"><span data-stu-id="f5842-153">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="f5842-154">Per consentire al modulo gestire gli eventi direttamente, è possibile utilizzare il multithreading.</span><span class="sxs-lookup"><span data-stu-id="f5842-154">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="f5842-155">Per ulteriori informazioni, vedere [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="f5842-155">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5842-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5842-156">See Also</span></span>  
 <span data-ttu-id="f5842-157">[Eventi](../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5842-157">[Events](../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="f5842-158"> [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5842-158"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="f5842-159"> [AddHandler (istruzione)](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5842-159"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="f5842-160"> [RemoveHandler (istruzione)](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5842-160"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="f5842-161"> [Handle](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="f5842-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
