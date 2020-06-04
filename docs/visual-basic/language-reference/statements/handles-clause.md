---
title: Clausola Handles
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: df786e4b0f0ab3795592ea57f7af17695b086cfa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404576"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="8b9c3-102">Clausola Handles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b9c3-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="8b9c3-103">Dichiara che una routine gestisce un evento specificato.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b9c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b9c3-104">Syntax</span></span>  
  
```vb  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="8b9c3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8b9c3-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="8b9c3-106">Dichiarazione `Sub` per la routine che gestirà l'evento.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="8b9c3-107">Elenco degli eventi che devono essere gestiti da `proceduredeclaration`.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="8b9c3-108">Gli eventi devono essere generati dalla classe base per la classe corrente o da un oggetto dichiarato usando la parola chiave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b9c3-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="8b9c3-109">Remarks</span></span>  
 <span data-ttu-id="8b9c3-110">Usare la parola chiave `Handles` alla fine di una dichiarazione di routine per fare in modo che la routine gestisca eventi generati da una variabile oggetto dichiarata con la parola chiave `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="8b9c3-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="8b9c3-111">La parola chiave `Handles` può anche essere usata in una classe derivata per gestire eventi da una classe base.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="8b9c3-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="8b9c3-113">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="8b9c3-114">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="8b9c3-115">Per ulteriori informazioni, vedere l' [istruzione AddHandler](addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b9c3-115">For more information, see [AddHandler Statement](addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="8b9c3-116">Per gli eventi personalizzati, l'applicazione richiama la funzione di accesso `AddHandler` dell'evento quando aggiunge la routine come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="8b9c3-117">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b9c3-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b9c3-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b9c3-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="8b9c3-119">L'esempio seguente illustra come una classe derivata può usare l'istruzione `Handles` per gestire un evento da una classe base.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-119">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8b9c3-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b9c3-120">Example</span></span>  
 <span data-ttu-id="8b9c3-121">Nell'esempio seguente sono contenuti due gestori di eventi Button per un progetto di **applicazione WPF** .</span><span class="sxs-lookup"><span data-stu-id="8b9c3-121">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="8b9c3-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b9c3-122">Example</span></span>  
 <span data-ttu-id="8b9c3-123">L'esempio che segue equivale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-123">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="8b9c3-124">L'oggetto `eventlist` nella clausola `Handles` contiene gli eventi per entrambi i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="8b9c3-124">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="8b9c3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b9c3-125">See also</span></span>

- [<span data-ttu-id="8b9c3-126">WithEvents</span><span class="sxs-lookup"><span data-stu-id="8b9c3-126">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="8b9c3-127">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="8b9c3-127">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="8b9c3-128">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="8b9c3-128">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="8b9c3-129">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="8b9c3-129">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="8b9c3-130">Istruzione RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="8b9c3-130">RaiseEvent Statement</span></span>](raiseevent-statement.md)
- [<span data-ttu-id="8b9c3-131">Events</span><span class="sxs-lookup"><span data-stu-id="8b9c3-131">Events</span></span>](../../programming-guide/language-features/events/index.md)
