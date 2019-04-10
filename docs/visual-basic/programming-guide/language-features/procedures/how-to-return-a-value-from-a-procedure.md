---
title: 'Procedura: Restituire un valore da una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 8b53df1634d2b9971bc44c968a17db81cac3924f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307886"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="b6f01-102">Procedura: Restituire un valore da una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f01-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="b6f01-103">Oggetto `Function` routine restituisce un valore al codice chiamante tramite l'esecuzione di un `Return` istruzione o l'individuazione un' `Exit Function` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b6f01-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="b6f01-104">Per restituire un valore utilizzando l'istruzione Return</span><span class="sxs-lookup"><span data-stu-id="b6f01-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="b6f01-105">Inserire un `Return` istruzione in corrispondenza del punto in cui il completamento di attività della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b6f01-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="b6f01-106">Seguire il `Return` (parola chiave) con un'espressione che restituisce il valore di cui si desidera venga restituito al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="b6f01-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="b6f01-107">Una routine può includere più di un'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="b6f01-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="b6f01-108">Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo e lo restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="b6f01-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="b6f01-109">Nell'esempio seguente viene illustrata una tipica chiamata alla `hypotenuse`, che archivia il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="b6f01-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="b6f01-110">Per restituire un valore di utilizzo di Exit Function o funzione End</span><span class="sxs-lookup"><span data-stu-id="b6f01-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="b6f01-111">In almeno un punto nel `Function` routine, assegnare un valore al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b6f01-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="b6f01-112">Quando si esegue un' `Exit Function` o `End Function` istruzione Visual Basic restituisce l'ultimo valore assegnato al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b6f01-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="b6f01-113">Una routine può includere più di un'istruzione `Exit Function` ed è possibile combinare istruzioni `Return` e `Exit Function` nella stessa routine.</span><span class="sxs-lookup"><span data-stu-id="b6f01-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="b6f01-114">Si può avere un solo `End Function` istruzione in un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="b6f01-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="b6f01-115">Per altre informazioni e un esempio, vedere "Valore di restituire" nella [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6f01-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f01-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6f01-116">See also</span></span>

- [<span data-ttu-id="b6f01-117">Procedure</span><span class="sxs-lookup"><span data-stu-id="b6f01-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b6f01-118">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="b6f01-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b6f01-119">Routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="b6f01-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b6f01-120">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b6f01-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b6f01-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="b6f01-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b6f01-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="b6f01-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="b6f01-123">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="b6f01-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="b6f01-124">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="b6f01-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="b6f01-125">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="b6f01-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
