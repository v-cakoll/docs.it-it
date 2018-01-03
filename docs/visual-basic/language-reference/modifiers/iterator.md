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
ms.openlocfilehash: fd6c0b1fa422dc4ab659d8c59472e5c098c729bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="fc68c-102">Iteratore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc68c-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="fc68c-103">Specifica che una funzione o `Get` funzione di accesso è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="fc68c-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc68c-104">Note</span><span class="sxs-lookup"><span data-stu-id="fc68c-104">Remarks</span></span>  
 <span data-ttu-id="fc68c-105">Un *iteratore* esegue un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="fc68c-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="fc68c-106">Un iteratore Usa il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="fc68c-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="fc68c-107">Quando un `Yield` istruzione viene raggiunto, viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="fc68c-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="fc68c-108">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="fc68c-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="fc68c-109">Un iteratore può essere implementato come una funzione o come un `Get` funzione di accesso di una definizione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fc68c-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="fc68c-110">Il `Iterator` modificatore viene visualizzato nella dichiarazione di funzione iteratore o `Get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="fc68c-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="fc68c-111">Chiamare un iteratore dal codice client utilizzando un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fc68c-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="fc68c-112">Il tipo restituito di una funzione iterator o `Get` della funzione di accesso può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="fc68c-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="fc68c-113">Un iteratore non può avere qualsiasi `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="fc68c-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="fc68c-114">Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="fc68c-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="fc68c-115">Un iteratore può essere una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="fc68c-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="fc68c-116">Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="fc68c-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="fc68c-117">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="fc68c-117">Usage</span></span>  
 <span data-ttu-id="fc68c-118">Il modificatore `Iterator` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc68c-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="fc68c-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="fc68c-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="fc68c-120">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="fc68c-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="fc68c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc68c-121">Example</span></span>  
 <span data-ttu-id="fc68c-122">Nell'esempio seguente viene illustrata una funzione iterator.</span><span class="sxs-lookup"><span data-stu-id="fc68c-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="fc68c-123">La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="fc68c-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="fc68c-124">Ogni iterazione del [per ogni](../../../visual-basic/language-reference/statements/for-each-next-statement.md) corpo dell'istruzione in `Main` crea una chiamata al `Power` funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="fc68c-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="fc68c-125">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="fc68c-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="fc68c-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc68c-126">Example</span></span>  
 <span data-ttu-id="fc68c-127">Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="fc68c-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="fc68c-128">Il `Iterator` modificatore è nella dichiarazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fc68c-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="fc68c-129">Per ulteriori esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="fc68c-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc68c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc68c-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="fc68c-131">Iteratori</span><span class="sxs-lookup"><span data-stu-id="fc68c-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)  
 [<span data-ttu-id="fc68c-132">Istruzione Yield</span><span class="sxs-lookup"><span data-stu-id="fc68c-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
