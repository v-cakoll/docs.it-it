---
title: 'Procedura: chiamare una routine di operatore (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21545f2488bfabd0abc9c6e316d21bbc4d5aeb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="17fea-102">Procedura: chiamare una routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17fea-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="17fea-103">Utilizzare il simbolo dell'operatore in un'espressione per chiamare una routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="17fea-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="17fea-104">Nel caso di un operatore di conversione, si chiama il [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="17fea-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="17fea-105">Routine di operatore non si chiama in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="17fea-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="17fea-106">È sufficiente utilizzare l'operatore, o `CType` funzione in un'istruzione di assegnazione o un'espressione, esattamente come si utilizza in genere un operatore.</span><span class="sxs-lookup"><span data-stu-id="17fea-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="17fea-107">Visual Basic effettua la chiamata di routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="17fea-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="17fea-108">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="17fea-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="17fea-109">Per chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="17fea-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="17fea-110">Utilizzare il simbolo dell'operatore in un'espressione in modo normale.</span><span class="sxs-lookup"><span data-stu-id="17fea-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="17fea-111">Verificare che i tipi di dati gli operandi siano appropriati per l'operatore e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="17fea-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="17fea-112">L'operatore contribuisce al valore dell'espressione, come previsto.</span><span class="sxs-lookup"><span data-stu-id="17fea-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="17fea-113">Per chiamare una routine di operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="17fea-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="17fea-114">Utilizzare `CType` all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="17fea-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="17fea-115">Verificare che i tipi di dati gli operandi siano appropriati per la conversione e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="17fea-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="17fea-116">`CType` chiama la routine di operatore di conversione e restituisce il valore convertito.</span><span class="sxs-lookup"><span data-stu-id="17fea-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17fea-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="17fea-117">Example</span></span>  
 <span data-ttu-id="17fea-118">L'esempio seguente crea due <xref:System.TimeSpan> strutture, li somma e archivia il risultato in un terzo <xref:System.TimeSpan> struttura.</span><span class="sxs-lookup"><span data-stu-id="17fea-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="17fea-119">Il <xref:System.TimeSpan> struttura definisce le routine di operatore per eseguire l'overload diversi operatori standard.</span><span class="sxs-lookup"><span data-stu-id="17fea-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="17fea-120">Poiché <xref:System.TimeSpan> overload standard `+` operatore, nell'esempio precedente chiama una routine di operatore quando si calcola il valore di `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="17fea-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="17fea-121">Per un esempio di chiamata una routine di operatore di conversione, vedere [procedura: utilizzare una classe che definisce operatori](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="17fea-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="17fea-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="17fea-122">Compiling the Code</span></span>  
 <span data-ttu-id="17fea-123">Assicurarsi che la classe o struttura in uso definisce l'operatore a cui che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="17fea-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fea-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17fea-124">See Also</span></span>  
 [<span data-ttu-id="17fea-125">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="17fea-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="17fea-126">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="17fea-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="17fea-127">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="17fea-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="17fea-128">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="17fea-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="17fea-129">Widening</span><span class="sxs-lookup"><span data-stu-id="17fea-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="17fea-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="17fea-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="17fea-131">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="17fea-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="17fea-132">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="17fea-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="17fea-133">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="17fea-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="17fea-134">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="17fea-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
