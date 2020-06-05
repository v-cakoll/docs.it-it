---
title: 'Procedura: chiamare una routine di operatore'
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
ms.openlocfilehash: fa2bc5417b8b917ff48502a5bd0a4daa21fab67e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388569"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="80062-102">Procedura: chiamare una routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80062-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="80062-103">Una routine di operatore viene chiamata utilizzando il simbolo dell'operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="80062-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="80062-104">Nel caso di un operatore di conversione, si chiama la [funzione CType](../../../language-reference/functions/ctype-function.md) per convertire un valore da un tipo di dati a un altro.</span><span class="sxs-lookup"><span data-stu-id="80062-104">In the case of a conversion operator, you call the [CType Function](../../../language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="80062-105">Le routine dell'operatore non vengono chiamate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="80062-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="80062-106">È sufficiente utilizzare l'operatore o la `CType` funzione, in un'istruzione di assegnazione o in un'espressione, nello stesso modo in cui si utilizza normalmente un operatore.</span><span class="sxs-lookup"><span data-stu-id="80062-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="80062-107">Visual Basic esegue la chiamata alla routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="80062-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="80062-108">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="80062-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="80062-109">Per chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="80062-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="80062-110">Usare il simbolo dell'operatore in un'espressione nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="80062-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="80062-111">Assicurarsi che i tipi di dati degli operandi siano appropriati per l'operatore e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="80062-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="80062-112">L'operatore contribuisce al valore dell'espressione come previsto.</span><span class="sxs-lookup"><span data-stu-id="80062-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="80062-113">Per chiamare una procedura dell'operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="80062-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="80062-114">Da usare `CType` all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="80062-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="80062-115">Assicurarsi che i tipi di dati degli operandi siano appropriati per la conversione e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="80062-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="80062-116">`CType`chiama la routine dell'operatore di conversione e restituisce il valore convertito.</span><span class="sxs-lookup"><span data-stu-id="80062-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80062-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="80062-117">Example</span></span>  
 <span data-ttu-id="80062-118">Nell'esempio seguente vengono create due <xref:System.TimeSpan> strutture, aggiunte insieme e il risultato viene archiviato in una terza <xref:System.TimeSpan> struttura.</span><span class="sxs-lookup"><span data-stu-id="80062-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="80062-119">La <xref:System.TimeSpan> struttura definisce le routine di operatore per eseguire l'overload di diversi operatori standard.</span><span class="sxs-lookup"><span data-stu-id="80062-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="80062-120">Poiché esegue l' <xref:System.TimeSpan> Overload dell' `+` operatore standard, nell'esempio precedente viene chiamata una routine di operatore quando viene calcolato il valore di `combinedSpan` .</span><span class="sxs-lookup"><span data-stu-id="80062-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="80062-121">Per un esempio di chiamata a una routine dell'operatore di conversazione, vedere [procedura: usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="80062-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="80062-122">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="80062-122">Compile the code</span></span>  
 <span data-ttu-id="80062-123">Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="80062-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80062-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80062-124">See also</span></span>

- [<span data-ttu-id="80062-125">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="80062-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="80062-126">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="80062-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="80062-127">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="80062-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="80062-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="80062-128">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="80062-129">Widening</span><span class="sxs-lookup"><span data-stu-id="80062-129">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="80062-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="80062-130">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="80062-131">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="80062-131">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="80062-132">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="80062-132">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="80062-133">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="80062-133">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="80062-134">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="80062-134">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
