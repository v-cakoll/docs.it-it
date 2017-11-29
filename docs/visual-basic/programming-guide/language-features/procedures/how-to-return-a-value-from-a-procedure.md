---
title: 'Procedura: restituire un valore da una routine (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce7aa0942be413986cb010963753447ea18cdf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="35bf6-102">Procedura: restituire un valore da una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35bf6-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="35bf6-103">Oggetto `Function` routine restituisce un valore al codice chiamante tramite l'esecuzione di un `Return` istruzione o l'individuazione un `Exit Function` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="35bf6-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="35bf6-104">Per restituire un valore utilizzando l'istruzione Return</span><span class="sxs-lookup"><span data-stu-id="35bf6-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="35bf6-105">Inserire un `Return` istruzione nel punto in cui viene completata l'attività della routine.</span><span class="sxs-lookup"><span data-stu-id="35bf6-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="35bf6-106">Seguire il `Return` (parola chiave) con un'espressione che restituisce il valore da restituire al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="35bf6-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="35bf6-107">Una routine può includere più di un'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="35bf6-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="35bf6-108">Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo e lo restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="35bf6-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="35bf6-109">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`, che archivia il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="35bf6-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="35bf6-110">Per restituire un valore utilizzando Exit Function o End Function</span><span class="sxs-lookup"><span data-stu-id="35bf6-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="35bf6-111">In almeno un punto di `Function` procedure, assegnare un valore al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="35bf6-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="35bf6-112">Quando si esegue un `Exit Function` o `End Function` istruzione [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] restituisce l'ultimo valore assegnato al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="35bf6-112">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="35bf6-113">Una routine può includere più di un'istruzione `Exit Function` ed è possibile combinare istruzioni `Return` e `Exit Function` nella stessa routine.</span><span class="sxs-lookup"><span data-stu-id="35bf6-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="35bf6-114">Si può avere un solo `End Function` istruzione in un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="35bf6-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="35bf6-115">Per ulteriori informazioni e un esempio, vedere "Valore restituito" in [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35bf6-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35bf6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35bf6-116">See Also</span></span>  
 [<span data-ttu-id="35bf6-117">Routine</span><span class="sxs-lookup"><span data-stu-id="35bf6-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="35bf6-118">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="35bf6-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="35bf6-119">Routine Property</span><span class="sxs-lookup"><span data-stu-id="35bf6-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="35bf6-120">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="35bf6-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="35bf6-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="35bf6-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="35bf6-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="35bf6-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="35bf6-123">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="35bf6-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="35bf6-124">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="35bf6-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="35bf6-125">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="35bf6-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
