---
title: 'Procedura: creare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349713"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="0617d-102">Procedura: creare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0617d-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="0617d-103">Usare una procedura `Function` per restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="0617d-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="0617d-104">Per creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="0617d-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="0617d-105">Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Function` seguita da un'istruzione `End Function`.</span><span class="sxs-lookup"><span data-stu-id="0617d-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="0617d-106">Nell'istruzione `Function` seguire la parola chiave `Function` con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="0617d-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="0617d-107">Seguire le parentesi con una clausola `As` per specificare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="0617d-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="0617d-108">Inserire le istruzioni di codice della stored procedure tra le istruzioni `Function` e `End Function`.</span><span class="sxs-lookup"><span data-stu-id="0617d-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="0617d-109">Utilizzare un'istruzione `Return` per restituire il valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="0617d-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="0617d-110">La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="0617d-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="0617d-111">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="0617d-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0617d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0617d-112">See also</span></span>

- [<span data-ttu-id="0617d-113">Routine</span><span class="sxs-lookup"><span data-stu-id="0617d-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0617d-114">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="0617d-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="0617d-115">Routine Property</span><span class="sxs-lookup"><span data-stu-id="0617d-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0617d-116">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0617d-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0617d-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="0617d-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0617d-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="0617d-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="0617d-119">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="0617d-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="0617d-120">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="0617d-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
