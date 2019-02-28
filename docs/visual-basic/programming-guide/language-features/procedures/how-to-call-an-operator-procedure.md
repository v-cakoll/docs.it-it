---
title: 'Procedura: Chiamare una routine di operatore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: ab9dd9e3f9abdd8379a59ed458c47d5ec8b4f2ad
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978969"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="439bb-102">Procedura: Chiamare una routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="439bb-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="439bb-103">Si chiama una routine di operatore usando il simbolo di operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="439bb-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="439bb-104">Nel caso di un operatore di conversione, si chiama il [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo a altro.</span><span class="sxs-lookup"><span data-stu-id="439bb-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="439bb-105">Routine di operatore non viene chiamato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="439bb-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="439bb-106">È sufficiente usare l'operatore, o `CType` funzione in un'istruzione di assegnazione o un'espressione, simile a quello in cui si utilizza normalmente un operatore.</span><span class="sxs-lookup"><span data-stu-id="439bb-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="439bb-107">Visual Basic effettua la chiamata alla routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="439bb-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="439bb-108">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="439bb-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="439bb-109">Per chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="439bb-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="439bb-110">Usare il simbolo dell'operatore in un'espressione nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="439bb-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="439bb-111">Assicurarsi che i tipi di dati gli operandi sono appropriati per l'operatore e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="439bb-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="439bb-112">L'operatore contribuisce al valore dell'espressione come previsto.</span><span class="sxs-lookup"><span data-stu-id="439bb-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="439bb-113">Per chiamare una routine di operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="439bb-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="439bb-114">Usare `CType` all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="439bb-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="439bb-115">Assicurarsi che i tipi di dati gli operandi sono appropriati per la conversione e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="439bb-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="439bb-116">`CType` chiama la routine di operatore di conversione e restituisce il valore convertito.</span><span class="sxs-lookup"><span data-stu-id="439bb-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="439bb-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="439bb-117">Example</span></span>  
 <span data-ttu-id="439bb-118">L'esempio seguente crea due <xref:System.TimeSpan> strutture, li somma e archivia il risultato in una terza <xref:System.TimeSpan> struttura.</span><span class="sxs-lookup"><span data-stu-id="439bb-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="439bb-119">Il <xref:System.TimeSpan> struttura definisce le routine di operatore per eseguire l'overload di diversi operatori standard.</span><span class="sxs-lookup"><span data-stu-id="439bb-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="439bb-120">In quanto <xref:System.TimeSpan> overloads standard `+` operatore, nell'esempio precedente chiama una routine di operatore quando si calcola il valore di `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="439bb-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="439bb-121">Per un esempio di chiamata una routine di operatore di conversione, vedere [come: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="439bb-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="439bb-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="439bb-122">Compiling the Code</span></span>  
 <span data-ttu-id="439bb-123">Assicurarsi che la classe o struttura che si usa definisce l'operatore da usare.</span><span class="sxs-lookup"><span data-stu-id="439bb-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="439bb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="439bb-124">See also</span></span>
- [<span data-ttu-id="439bb-125">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="439bb-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="439bb-126">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="439bb-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="439bb-127">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="439bb-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="439bb-128">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="439bb-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="439bb-129">Widening</span><span class="sxs-lookup"><span data-stu-id="439bb-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="439bb-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="439bb-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="439bb-131">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="439bb-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="439bb-132">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="439bb-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="439bb-133">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="439bb-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="439bb-134">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="439bb-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
