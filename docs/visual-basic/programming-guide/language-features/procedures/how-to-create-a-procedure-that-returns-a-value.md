---
title: 'Procedura: creare una routine che restituisce un valore (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 787eddc1fd1cdb9dd6b655a8556b75044b2a49dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="4713a-102">Procedura: creare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4713a-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="4713a-103">Si utilizza un `Function` procedure per restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4713a-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="4713a-104">Per creare una stored procedure che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4713a-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="4713a-105">All'esterno di qualsiasi altra routine, utilizzare un `Function` istruzione, seguito da un `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4713a-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="4713a-106">Nel `Function` istruzione, seguire la `Function` (parola chiave) con il nome della routine e, quindi l'elenco di parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4713a-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="4713a-107">Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4713a-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="4713a-108">Inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4713a-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="4713a-109">Utilizzare un `Return` istruzione per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4713a-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="4713a-110">Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo, in base ai valori per i due lati.</span><span class="sxs-lookup"><span data-stu-id="4713a-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="4713a-111">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="4713a-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4713a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4713a-112">See Also</span></span>  
 [<span data-ttu-id="4713a-113">Routine</span><span class="sxs-lookup"><span data-stu-id="4713a-113">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4713a-114">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="4713a-114">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="4713a-115">Routine Property</span><span class="sxs-lookup"><span data-stu-id="4713a-115">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="4713a-116">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="4713a-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="4713a-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="4713a-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4713a-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="4713a-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="4713a-119">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="4713a-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="4713a-120">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4713a-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
