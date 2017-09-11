---
title: Clausola Handles (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Handles
- vb.Handles
dev_langs:
- VB
helpviewer_keywords:
- Handles keyword
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: cd5dec12312e05242551d5aff112028a8e1ff8b3
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="b1f34-102">Clausola Handles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1f34-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="b1f34-103">Dichiara che una routine gestisce un evento specificato.</span><span class="sxs-lookup"><span data-stu-id="b1f34-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1f34-104">Syntax</span></span>  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="b1f34-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b1f34-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="b1f34-106">Dichiarazione `Sub` per la routine che gestirà l'evento.</span><span class="sxs-lookup"><span data-stu-id="b1f34-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="b1f34-107">Elenco degli eventi che devono essere gestiti da `proceduredeclaration`.</span><span class="sxs-lookup"><span data-stu-id="b1f34-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="b1f34-108">Gli eventi devono essere generati dalla classe base per la classe corrente o da un oggetto dichiarato usando la parola chiave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="b1f34-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1f34-109">Note</span><span class="sxs-lookup"><span data-stu-id="b1f34-109">Remarks</span></span>  
 <span data-ttu-id="b1f34-110">Usare la parola chiave `Handles` alla fine di una dichiarazione di routine per fare in modo che la routine gestisca eventi generati da una variabile oggetto dichiarata con la parola chiave `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="b1f34-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="b1f34-111">La parola chiave `Handles` può anche essere usata in una classe derivata per gestire eventi da una classe base.</span><span class="sxs-lookup"><span data-stu-id="b1f34-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="b1f34-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="b1f34-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="b1f34-113">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="b1f34-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="b1f34-114">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b1f34-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="b1f34-115">Per ulteriori informazioni, vedere [AddHandler (istruzione)](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1f34-115">For more information, see [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="b1f34-116">Per gli eventi personalizzati, l'applicazione richiama la funzione di accesso `AddHandler` dell'evento quando aggiunge la routine come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="b1f34-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="b1f34-117">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1f34-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1f34-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1f34-118">Example</span></span>  
 <span data-ttu-id="b1f34-119">[!code-vb[VbVbalrEvents n.&2;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b1f34-119">[!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]</span></span>  
  
 <span data-ttu-id="b1f34-120">L'esempio seguente illustra come una classe derivata può usare l'istruzione `Handles` per gestire un evento da una classe base.</span><span class="sxs-lookup"><span data-stu-id="b1f34-120">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 <span data-ttu-id="b1f34-121">[!code-vb[VbVbalrEvents n.&3;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b1f34-121">[!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1f34-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1f34-122">Example</span></span>  
 <span data-ttu-id="b1f34-123">Nell'esempio seguente contiene due gestori eventi del pulsante per un **applicazione WPF** project.</span><span class="sxs-lookup"><span data-stu-id="b1f34-123">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 <span data-ttu-id="b1f34-124">[!code-vb[VbVbalrEvents n.&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b1f34-124">[!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1f34-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1f34-125">Example</span></span>  
 <span data-ttu-id="b1f34-126">L'esempio che segue equivale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="b1f34-126">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="b1f34-127">L'oggetto `eventlist` nella clausola `Handles` contiene gli eventi per entrambi i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="b1f34-127">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 <span data-ttu-id="b1f34-128">[!code-vb[VbVbalrEvents&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b1f34-128">[!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f34-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1f34-129">See Also</span></span>  
 <span data-ttu-id="b1f34-130">[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) </span><span class="sxs-lookup"><span data-stu-id="b1f34-130">[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) </span></span>  
<span data-ttu-id="b1f34-131"> [AddHandler (istruzione)](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b1f34-131"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="b1f34-132"> [RemoveHandler (istruzione)](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b1f34-132"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="b1f34-133"> [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b1f34-133"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="b1f34-134"> [RaiseEvent (istruzione)](../../../visual-basic/language-reference/statements/raiseevent-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b1f34-134"> [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md) </span></span>  
<span data-ttu-id="b1f34-135"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="b1f34-135"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>

