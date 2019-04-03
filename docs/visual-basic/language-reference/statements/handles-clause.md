---
title: Clausola Handles (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 50a449ea8a5131c878cf703f44695cd2e2304444
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842577"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="a6e67-102">Clausola Handles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6e67-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="a6e67-103">Dichiara che una routine gestisce un evento specificato.</span><span class="sxs-lookup"><span data-stu-id="a6e67-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6e67-104">Syntax</span></span>  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="a6e67-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a6e67-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="a6e67-106">Dichiarazione `Sub` per la routine che gestirà l'evento.</span><span class="sxs-lookup"><span data-stu-id="a6e67-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="a6e67-107">Elenco degli eventi che devono essere gestiti da `proceduredeclaration`.</span><span class="sxs-lookup"><span data-stu-id="a6e67-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="a6e67-108">Gli eventi devono essere generati dalla classe base per la classe corrente o da un oggetto dichiarato usando la parola chiave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="a6e67-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6e67-109">Note</span><span class="sxs-lookup"><span data-stu-id="a6e67-109">Remarks</span></span>  
 <span data-ttu-id="a6e67-110">Usare la parola chiave `Handles` alla fine di una dichiarazione di routine per fare in modo che la routine gestisca eventi generati da una variabile oggetto dichiarata con la parola chiave `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="a6e67-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="a6e67-111">La parola chiave `Handles` può anche essere usata in una classe derivata per gestire eventi da una classe base.</span><span class="sxs-lookup"><span data-stu-id="a6e67-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="a6e67-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="a6e67-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a6e67-113">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="a6e67-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a6e67-114">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a6e67-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a6e67-115">Per altre informazioni, vedere [istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6e67-115">For more information, see [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="a6e67-116">Per gli eventi personalizzati, l'applicazione richiama la funzione di accesso `AddHandler` dell'evento quando aggiunge la routine come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a6e67-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="a6e67-117">Per altre informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6e67-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6e67-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6e67-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a6e67-119">L'esempio seguente illustra come una classe derivata può usare l'istruzione `Handles` per gestire un evento da una classe base.</span><span class="sxs-lookup"><span data-stu-id="a6e67-119">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a6e67-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6e67-120">Example</span></span>  
 <span data-ttu-id="a6e67-121">L'esempio seguente contiene due gestori eventi dei pulsanti per un **WPF Application** progetto.</span><span class="sxs-lookup"><span data-stu-id="a6e67-121">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="a6e67-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6e67-122">Example</span></span>  
 <span data-ttu-id="a6e67-123">L'esempio che segue equivale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="a6e67-123">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="a6e67-124">L'oggetto `eventlist` nella clausola `Handles` contiene gli eventi per entrambi i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="a6e67-124">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="a6e67-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e67-125">See also</span></span>

- [<span data-ttu-id="a6e67-126">WithEvents</span><span class="sxs-lookup"><span data-stu-id="a6e67-126">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="a6e67-127">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="a6e67-127">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="a6e67-128">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="a6e67-128">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="a6e67-129">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="a6e67-129">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a6e67-130">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="a6e67-130">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [<span data-ttu-id="a6e67-131">Eventi</span><span class="sxs-lookup"><span data-stu-id="a6e67-131">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
