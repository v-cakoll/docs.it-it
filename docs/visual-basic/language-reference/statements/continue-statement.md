---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835385"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="03dd5-102">Istruzione Continue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03dd5-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="03dd5-103">Trasferisce il controllo immediatamente all'iterazione successiva di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03dd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03dd5-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="03dd5-105">Note</span><span class="sxs-lookup"><span data-stu-id="03dd5-105">Remarks</span></span>  
 <span data-ttu-id="03dd5-106">È possibile trasferire da all'interno di un `Do`, `For`, o `While` ciclo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="03dd5-107">Il controllo passa immediatamente alla verifica della condizione di ciclo, che viene trasferito al `For` o `While` istruzione, o il `Do` o `Loop` istruzione che contiene la `Until` o `While` clausola.</span><span class="sxs-lookup"><span data-stu-id="03dd5-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="03dd5-108">È possibile usare `Continue` in qualsiasi posizione nel ciclo che consente i trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="03dd5-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="03dd5-109">Le regole che consentono il trasferimento del controllo sono le stesse usate con il [istruzione GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03dd5-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="03dd5-110">Ad esempio, se un ciclo è completamente indipendente all'interno di un `Try` blocco, una `Catch` blocco, o una `Finally` blocco, è possibile usare `Continue` da trasferire all'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="03dd5-111">Se, d'altra parte, il `Try`... `End Try` struttura è contenuta all'interno del ciclo, non è possibile usare `Continue` per trasferire il controllo fuori il `Finally` blocco ed è possibile utilizzare per il trasferimento di una `Try` o `Catch` bloccare solo se si trasferiscono completamente fuori il `Try`... `End Try` struttura.</span><span class="sxs-lookup"><span data-stu-id="03dd5-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="03dd5-112">Se sono presenti cicli annidati dello stesso tipo, ad esempio un `Do` ciclo all'interno di altra `Do` ciclo, un `Continue Do` istruzione passa all'iterazione successiva del ciclo `Do` ciclo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="03dd5-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="03dd5-113">Non è possibile usare `Continue` da ignorare all'iterazione successiva di un contenitore ciclo dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="03dd5-114">Se sono presenti cicli annidati di tipi diversi, ad esempio un `Do` ciclo all'interno di un `For` ciclo, è possibile passare all'iterazione successiva del ciclo di entrambi utilizzando `Continue Do` o `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="03dd5-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03dd5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="03dd5-115">Example</span></span>  
 <span data-ttu-id="03dd5-116">Il codice seguente viene illustrato come utilizzare il `Continue While` istruzione per ignorare la successiva colonna di una matrice se il divisore è zero.</span><span class="sxs-lookup"><span data-stu-id="03dd5-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="03dd5-117">Il `Continue While` si trova all'interno un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="03dd5-118">Viene trasferita l'esecuzione di `While col < lastcol` istruzione, ovvero l'iterazione successiva del ciclo `While` ciclo che contiene il `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="03dd5-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="03dd5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03dd5-119">See also</span></span>

- [<span data-ttu-id="03dd5-120">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="03dd5-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="03dd5-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="03dd5-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="03dd5-122">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="03dd5-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="03dd5-123">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="03dd5-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
