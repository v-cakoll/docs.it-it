---
title: 'Procedura: creare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 2655aba6ce37be831d8dd4202ffd484cfd3fd5ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388349"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="4ee3f-102">Procedura: creare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ee3f-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="4ee3f-103">Usare una `Function` procedura per restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="4ee3f-104">Per creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4ee3f-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="4ee3f-105">All'esterno di qualsiasi altra procedura, utilizzare un' `Function` istruzione, seguita da un' `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="4ee3f-106">Nell' `Function` istruzione seguire la `Function` parola chiave con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="4ee3f-107">Seguire le parentesi con una `As` clausola per specificare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="4ee3f-108">Inserire le istruzioni di codice della stored procedure tra le `Function` `End Function` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="4ee3f-109">Utilizzare un' `Return` istruzione per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="4ee3f-110">La `Function` procedura seguente calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="4ee3f-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="4ee3f-111">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="4ee3f-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4ee3f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ee3f-112">See also</span></span>

- [<span data-ttu-id="4ee3f-113">Procedure</span><span class="sxs-lookup"><span data-stu-id="4ee3f-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4ee3f-114">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="4ee3f-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="4ee3f-115">Routine Property</span><span class="sxs-lookup"><span data-stu-id="4ee3f-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="4ee3f-116">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="4ee3f-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4ee3f-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="4ee3f-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4ee3f-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="4ee3f-118">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="4ee3f-119">Procedura: restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="4ee3f-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="4ee3f-120">Procedura: chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="4ee3f-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
