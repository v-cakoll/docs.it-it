---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005111"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="01afe-102">Istruzione Continue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01afe-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="01afe-103">Trasferisce immediatamente il controllo all'iterazione successiva di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="01afe-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01afe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01afe-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="01afe-105">Note</span><span class="sxs-lookup"><span data-stu-id="01afe-105">Remarks</span></span>  
 <span data-ttu-id="01afe-106">È possibile trasferire dall'interno di un ciclo `Do`, `For` o `While` alla successiva iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="01afe-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="01afe-107">Il controllo passa immediatamente al test della condizione del ciclo, che equivale a trasferire l'istruzione `For` o `While` o all'istruzione `Do` o `Loop` che contiene la clausola `Until` o `While`.</span><span class="sxs-lookup"><span data-stu-id="01afe-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="01afe-108">È possibile utilizzare `Continue` in qualsiasi posizione del ciclo che consente i trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="01afe-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="01afe-109">Le regole che consentono il trasferimento del controllo sono le stesse dell' [istruzione goto](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="01afe-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="01afe-110">Se, ad esempio, un ciclo è interamente contenuto all'interno di un blocco `Try`, un blocco `Catch` o un blocco `Finally`, è possibile utilizzare `Continue` per trasferire il ciclo.</span><span class="sxs-lookup"><span data-stu-id="01afe-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="01afe-111">Se, invece, la struttura `Try`... `End Try` è contenuta all'interno del ciclo, non è possibile usare `Continue` per trasferire il controllo dal blocco `Finally` ed è possibile usarlo per trasferire fuori da un blocco `Try` o `Catch` solo se si trasferisce completamente dal @no_ struttura _T-6... `End Try`.</span><span class="sxs-lookup"><span data-stu-id="01afe-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="01afe-112">Se si dispone di cicli annidati dello stesso tipo, ad esempio un ciclo `Do` in un altro ciclo `Do`, un'istruzione `Continue Do` passa alla successiva iterazione del ciclo `Do` più interno che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="01afe-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="01afe-113">Non è possibile usare `Continue` per passare all'iterazione successiva di un ciclo contenitore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="01afe-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="01afe-114">Se sono presenti cicli annidati di tipi diversi, ad esempio un ciclo `Do` all'interno di un ciclo `For`, è possibile passare all'iterazione successiva di uno dei due cicli usando `Continue Do` o `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="01afe-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01afe-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="01afe-115">Example</span></span>  
 <span data-ttu-id="01afe-116">Nell'esempio di codice seguente viene utilizzata l'istruzione `Continue While` per passare alla colonna successiva di una matrice se il divisore è zero.</span><span class="sxs-lookup"><span data-stu-id="01afe-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="01afe-117">Il `Continue While` si trova all'interno di un ciclo `For`.</span><span class="sxs-lookup"><span data-stu-id="01afe-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="01afe-118">Trasferisce all'istruzione `While col < lastcol`, ovvero l'iterazione successiva del ciclo `While` più interno che contiene il ciclo `For`.</span><span class="sxs-lookup"><span data-stu-id="01afe-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="01afe-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01afe-119">See also</span></span>

- [<span data-ttu-id="01afe-120">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="01afe-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="01afe-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="01afe-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="01afe-122">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="01afe-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="01afe-123">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="01afe-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
