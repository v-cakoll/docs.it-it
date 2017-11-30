---
title: Iteratore (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="21802-102">Iteratore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21802-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="21802-103">Specifica che una funzione o `Get` funzione di accesso è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="21802-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21802-104">Note</span><span class="sxs-lookup"><span data-stu-id="21802-104">Remarks</span></span>  
 <span data-ttu-id="21802-105">Un *iteratore* esegue un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21802-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="21802-106">Un iteratore Usa il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="21802-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="21802-107">Quando un `Yield` istruzione viene raggiunto, viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="21802-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="21802-108">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="21802-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="21802-109">Un iteratore può essere implementato come una funzione o come un `Get` funzione di accesso di una definizione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="21802-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="21802-110">Il `Iterator` modificatore viene visualizzato nella dichiarazione di funzione iteratore o `Get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="21802-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="21802-111">Chiamare un iteratore dal codice client utilizzando un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21802-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="21802-112">Il tipo restituito di una funzione iterator o `Get` della funzione di accesso può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="21802-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="21802-113">Un iteratore non può avere qualsiasi `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="21802-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="21802-114">Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="21802-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="21802-115">Un iteratore può essere una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="21802-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="21802-116">Per altre informazioni, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="21802-116">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="21802-117">Per altre informazioni sugli iteratori, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="21802-117">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="21802-118">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="21802-118">Usage</span></span>  
 <span data-ttu-id="21802-119">Il modificatore `Iterator` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="21802-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="21802-120">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="21802-120">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="21802-121">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="21802-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="21802-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="21802-122">Example</span></span>  
 <span data-ttu-id="21802-123">Nell'esempio seguente viene illustrata una funzione iterator.</span><span class="sxs-lookup"><span data-stu-id="21802-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="21802-124">La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="21802-124">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="21802-125">Ogni iterazione del [per ogni](../../../visual-basic/language-reference/statements/for-each-next-statement.md) corpo dell'istruzione in `Main` crea una chiamata al `Power` funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="21802-125">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="21802-126">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="21802-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="21802-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="21802-127">Example</span></span>  
 <span data-ttu-id="21802-128">Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="21802-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="21802-129">Il `Iterator` modificatore è nella dichiarazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="21802-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="21802-130">Per ulteriori esempi, vedere [iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="21802-130">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21802-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21802-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="21802-132">Iteratori</span><span class="sxs-lookup"><span data-stu-id="21802-132">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="21802-133">Istruzione Yield</span><span class="sxs-lookup"><span data-stu-id="21802-133">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
