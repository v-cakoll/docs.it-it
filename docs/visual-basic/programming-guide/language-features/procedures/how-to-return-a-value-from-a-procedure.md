---
title: 'Procedura: restituire un valore da una routine (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 601cd3adca0105eb829bb6156f94289b5c9f5f72
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="03411-102">Procedura: restituire un valore da una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03411-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="03411-103">Oggetto `Function` routine restituisce un valore al codice chiamante tramite l'esecuzione di un `Return` istruzione o l'individuazione un `Exit Function` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="03411-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="03411-104">Per restituire un valore utilizzando l'istruzione Return</span><span class="sxs-lookup"><span data-stu-id="03411-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="03411-105">Inserire un `Return` istruzione nel punto in cui viene completata l'attività della routine.</span><span class="sxs-lookup"><span data-stu-id="03411-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="03411-106">Seguire il `Return` (parola chiave) con un'espressione che restituisce il valore da restituire al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="03411-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="03411-107">È possibile avere più di una `Return` istruzione nella stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="03411-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="03411-108">Nell'esempio `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo e lo restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="03411-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     <span data-ttu-id="03411-109">[!code-vb[VbVbcnProcedures n.&1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03411-109">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="03411-110">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`, che memorizza il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="03411-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     <span data-ttu-id="03411-111">[!code-vb[6 VbVbcnProcedures](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="03411-111">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span></span>  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="03411-112">Per restituire un valore utilizzando Exit Function o End Function</span><span class="sxs-lookup"><span data-stu-id="03411-112">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="03411-113">In almeno un punto di `Function` procedura, assegnare un valore al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03411-113">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="03411-114">Quando si esegue un `Exit Function` o `End Function` istruzione [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] restituisce l'ultimo valore assegnato al nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03411-114">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="03411-115">È possibile avere più di una `Exit Function` istruzione nella procedura stessa, è possibile combinare `Return` e `Exit Function` istruzioni nella procedura stessa.</span><span class="sxs-lookup"><span data-stu-id="03411-115">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="03411-116">È possibile avere solo una `End Function` istruzione in un `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="03411-116">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="03411-117">Per ulteriori informazioni e un esempio, vedere "Valore restituito" in [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03411-117">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03411-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03411-118">See Also</span></span>  
 <span data-ttu-id="03411-119">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="03411-119">[Procedures](./index.md) </span></span>  
<span data-ttu-id="03411-120"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="03411-120"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="03411-121"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="03411-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="03411-122"> [Routine di operatore](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="03411-122"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="03411-123"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="03411-123"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="03411-124"> [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="03411-124"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="03411-125"> [Return (istruzione)](../../../../visual-basic/language-reference/statements/return-statement.md) </span><span class="sxs-lookup"><span data-stu-id="03411-125"> [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md) </span></span>  
<span data-ttu-id="03411-126"> [Procedura: creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="03411-126"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="03411-127"> [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="03411-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
