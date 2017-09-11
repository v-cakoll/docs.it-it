---
title: 'Procedura: chiamare un gestore eventi in Visual Basic | Documenti di Microsoft'
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
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
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
ms.openlocfilehash: dc0174d50c7b5f5cda9d057bce39960b3e563f4e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="fbd8d-102">Procedura: chiamare un gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbd8d-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="fbd8d-103">Un *evento* è un'azione o un'occorrenza, ad esempio un mouse superato un limite di credito o fare clic su, che è riconosciuto da un componente di programma e per cui è possibile scrivere codice per rispondere.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="fbd8d-104">Un *gestore dell'evento* è il codice scritto in risposta a un evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="fbd8d-105">Un gestore dell'evento [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] è un `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-105">An event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="fbd8d-106">Tuttavia, si non viene in genere chiamato lo stesso modo di altri `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="fbd8d-107">Al contrario, la procedura per identificare come un gestore per l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="fbd8d-108">È possibile eseguire questa operazione con un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola e [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variabile, o con un [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="fbd8d-109">Utilizzando un `Handles` clausola è la modalità predefinita per dichiarare un gestore dell'evento [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbd8d-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="fbd8d-110">Questo è il modo in cui che i gestori eventi vengono scritti dalle finestre di progettazione quando si programma nell'ambiente di sviluppo integrato (IDE).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="fbd8d-111">Il `AddHandler` istruzione è adatta per la generazione di eventi in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="fbd8d-112">Quando si verifica l'evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automaticamente chiama la routine del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-112">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="fbd8d-113">Qualsiasi codice che dispone dell'accesso per l'evento può causare la generazione mediante l'esecuzione di un [istruzione RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="fbd8d-114">È possibile associare più gestori di eventi con lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="fbd8d-115">In alcuni casi è possibile dissociare un gestore a un evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="fbd8d-116">Per ulteriori informazioni, vedere [eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="fbd8d-117">Per chiamare un gestore eventi mediante Handles e WithEvents</span><span class="sxs-lookup"><span data-stu-id="fbd8d-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="fbd8d-118">Assicurarsi che l'evento è dichiarato con un [istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="fbd8d-119">Dichiarare una variabile oggetto livello di modulo o classe utilizzando il [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="fbd8d-120">Il `As` clausola per questa variabile deve specificare la classe che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="fbd8d-121">Nella dichiarazione della gestione dell'evento `Sub` procedura, aggiungere un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola che specifica il `WithEvents` variabile e il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="fbd8d-122">Quando si verifica l'evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chiama automaticamente il `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-122">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="fbd8d-123">Il codice può usare un `RaiseEvent` istruzione per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="fbd8d-124">Nell'esempio seguente definisce un evento e un `WithEvents` variabile che fa riferimento alla classe che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="fbd8d-125">La gestione dell'evento `Sub` procedura vengono utilizzati un `Handles` clausola per specificare la classe gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     <span data-ttu-id="fbd8d-126">[!code-vb[VbVbcnProcedures n.&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fbd8d-126">[!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span></span>  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="fbd8d-127">Per chiamare un gestore eventi mediante AddHandler</span><span class="sxs-lookup"><span data-stu-id="fbd8d-127">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="fbd8d-128">Assicurarsi che l'evento è dichiarato con un `Event` istruzione.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-128">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="fbd8d-129">Eseguire un [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) in grado di connettersi in modo dinamico la gestione dell'evento `Sub` procedure con l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-129">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="fbd8d-130">Quando si verifica l'evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chiama automaticamente il `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-130">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="fbd8d-131">Il codice può usare un `RaiseEvent` istruzione per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbd8d-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="fbd8d-132">L'esempio seguente definisce una `Sub` procedura per gestire il <xref:System.Windows.Forms.Form.Closing>evento di un form.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="fbd8d-132">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="fbd8d-133">Viene quindi utilizzato il [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) per associare il `catchClose` procedura come un gestore eventi per <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="fbd8d-133">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     <span data-ttu-id="fbd8d-134">[!code-vb[VbVbcnProcedures n.&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="fbd8d-134">[!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span></span>  
  
     <span data-ttu-id="fbd8d-135">È possibile dissociare un gestore eventi da un evento mediante l'esecuzione di [istruzione RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fbd8d-135">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd8d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd8d-136">See Also</span></span>  
 <span data-ttu-id="fbd8d-137">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="fbd8d-137">[Procedures](./index.md) </span></span>  
<span data-ttu-id="fbd8d-138"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fbd8d-138"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="fbd8d-139"> [Sub (istruzione)](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="fbd8d-139"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="fbd8d-140"> [AddressOf (operatore)](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="fbd8d-140"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="fbd8d-141"> [Procedura: creare una stored Procedure](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="fbd8d-141"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="fbd8d-142"> [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="fbd8d-142"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
