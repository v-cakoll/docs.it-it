---
title: 'Procedura: Creare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: ce0010762374baf5b19ab2e64f50e12fefda2dee
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966965"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="46a5e-102">Procedura: Creare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46a5e-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="46a5e-103">Si utilizza un `Function` procedure per restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="46a5e-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="46a5e-104">Per creare una stored procedure che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="46a5e-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="46a5e-105">Di fuori di qualsiasi altra routine, usare una `Function` istruzione, seguito da un `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="46a5e-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="46a5e-106">Nel `Function` istruzione, seguire la `Function` parola chiave con il nome della routine e quindi l'elenco dei parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="46a5e-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="46a5e-107">Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="46a5e-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="46a5e-108">È possibile inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="46a5e-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="46a5e-109">Usare un `Return` istruzione per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="46a5e-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="46a5e-110">Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="46a5e-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="46a5e-111">Nell'esempio seguente viene illustrata una tipica chiamata alla `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="46a5e-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="46a5e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46a5e-112">See also</span></span>
- [<span data-ttu-id="46a5e-113">Routine</span><span class="sxs-lookup"><span data-stu-id="46a5e-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="46a5e-114">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="46a5e-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="46a5e-115">Routine Property</span><span class="sxs-lookup"><span data-stu-id="46a5e-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="46a5e-116">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="46a5e-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="46a5e-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="46a5e-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="46a5e-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="46a5e-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="46a5e-119">Procedura: Restituisce il valore da una routine</span><span class="sxs-lookup"><span data-stu-id="46a5e-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="46a5e-120">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="46a5e-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
