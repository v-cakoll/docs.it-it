---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="44903-102">Istruzione Continue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44903-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="44903-103">Trasferisce il controllo immediatamente all'iterazione successiva di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="44903-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44903-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44903-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="44903-105">Note</span><span class="sxs-lookup"><span data-stu-id="44903-105">Remarks</span></span>  
 <span data-ttu-id="44903-106">È possibile trasferire da all'interno di un `Do`, `For`, o `While` ciclo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="44903-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="44903-107">Il controllo passa immediatamente alla verifica della condizione di ciclo, che viene trasferito al `For` o `While` istruzione o il `Do` o `Loop` istruzione che contiene il `Until` o `While` clausola.</span><span class="sxs-lookup"><span data-stu-id="44903-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="44903-108">È possibile utilizzare `Continue` in qualsiasi posizione nel ciclo che consente i trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="44903-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="44903-109">Le regole che consentono il trasferimento del controllo sono la stessa utilizzata con la [istruzione GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="44903-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="44903-110">Ad esempio, se un ciclo è contenuto completamente all'interno di un `Try` blocco, una `Catch` blocco, o un `Finally` blocco, è possibile utilizzare `Continue` per il trasferimento all'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="44903-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="44903-111">Se, invece, il `Try`... `End Try` struttura è contenuta all'interno del ciclo, è possibile utilizzare `Continue` per trasferire il controllo fuori il `Finally` blocco ed è possibile utilizzarla per uscire da un `Try` o `Catch` blocco solo se si trasferiscono completamente fuori il `Try`... `End Try` struttura.</span><span class="sxs-lookup"><span data-stu-id="44903-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="44903-112">Se sono presenti cicli annidati dello stesso tipo, ad esempio un `Do` ciclo all'interno di altra `Do` ciclo, un `Continue Do` istruzione passa all'iterazione successiva del ciclo `Do` ciclo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="44903-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="44903-113">Non è possibile utilizzare `Continue` per passare all'iterazione successiva di un contenitore ciclo dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="44903-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="44903-114">Se sono presenti cicli annidati di tipi diversi, ad esempio un `Do` ciclo all'interno di un `For` ciclo, è possibile passare all'iterazione successiva del ciclo di entrambi, utilizzando `Continue Do` o `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="44903-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44903-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="44903-115">Example</span></span>  
 <span data-ttu-id="44903-116">Nell'esempio di codice viene illustrato come utilizzare il `Continue While` istruzione per passare alla colonna successiva di una matrice, se un divisore è zero.</span><span class="sxs-lookup"><span data-stu-id="44903-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="44903-117">Il `Continue While` è all'interno di un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="44903-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="44903-118">Passa al `While col < lastcol` istruzione, ovvero l'iterazione successiva del ciclo `While` che contiene il `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="44903-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="44903-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44903-119">See Also</span></span>  
 [<span data-ttu-id="44903-120">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="44903-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="44903-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="44903-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="44903-122">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="44903-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="44903-123">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="44903-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
