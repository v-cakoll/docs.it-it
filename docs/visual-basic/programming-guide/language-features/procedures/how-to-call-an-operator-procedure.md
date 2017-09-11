---
title: 'Procedura: chiamare una routine di operatore (Visual Basic) | Documenti di Microsoft'
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
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
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
ms.openlocfilehash: cd85a14a6f5534e90497268134f4b2b0cc292249
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="1609c-102">Procedura: chiamare una routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1609c-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="1609c-103">Chiamare una routine di operatore utilizzando il simbolo di operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="1609c-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="1609c-104">Nel caso di un operatore di conversione, si chiama il [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per convertire un valore da un tipo a altro.</span><span class="sxs-lookup"><span data-stu-id="1609c-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="1609c-105">Non è necessario chiamare routine di operatore in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="1609c-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="1609c-106">È sufficiente utilizzare l'operatore o `CType` funzione in un'istruzione di assegnazione o un'espressione, diverso da quello in cui si utilizza normalmente un operatore.</span><span class="sxs-lookup"><span data-stu-id="1609c-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1609c-107">effettua la chiamata alla routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="1609c-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="1609c-108">Definisce un operatore su una classe o struttura viene anche chiamato *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="1609c-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="1609c-109">Per chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="1609c-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="1609c-110">Utilizzare il simbolo di operatore in un'espressione in modo normale.</span><span class="sxs-lookup"><span data-stu-id="1609c-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="1609c-111">Verificare che i tipi di dati degli operandi siano appropriati per l'operatore e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="1609c-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="1609c-112">L'operatore contribuisce al valore dell'espressione come previsto.</span><span class="sxs-lookup"><span data-stu-id="1609c-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="1609c-113">Per chiamare una routine di operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="1609c-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="1609c-114">Utilizzare `CType` all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="1609c-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="1609c-115">Verificare che i tipi di dati degli operandi siano appropriati per la conversione e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="1609c-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="1609c-116">`CType`chiama la routine di operatore di conversione e restituisce il valore convertito.</span><span class="sxs-lookup"><span data-stu-id="1609c-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1609c-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="1609c-117">Example</span></span>  
 <span data-ttu-id="1609c-118">Nell'esempio seguente vengono create due <xref:System.TimeSpan>strutture, li somma e archivia il risultato in un terzo <xref:System.TimeSpan>struttura.</xref:System.TimeSpan> </xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="1609c-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="1609c-119">Il <xref:System.TimeSpan>struttura definisce le routine di operatore per eseguire l'overload di diversi operatori standard.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="1609c-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 <span data-ttu-id="1609c-120">[!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1609c-120">[!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="1609c-121">Poiché <xref:System.TimeSpan>overload standard `+` operatore, nell'esempio precedente chiama una routine di operatore quando si calcola il valore di `combinedSpan`.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="1609c-121">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="1609c-122">Per un esempio di chiamata una routine di operatore di conversione, vedere [procedura: utilizzare una classe che definisce operatori](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1609c-122">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1609c-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1609c-123">Compiling the Code</span></span>  
 <span data-ttu-id="1609c-124">Assicurarsi che la classe o struttura in uso definisce l'operatore da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1609c-124">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1609c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1609c-125">See Also</span></span>  
 <span data-ttu-id="1609c-126">[Routine di operatore](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-126">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="1609c-127"> [Procedura: definire un operatore](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-127"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="1609c-128"> [Procedura: definire un operatore di conversione](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-128"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="1609c-129"> [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-129"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="1609c-130"> [Ampliamento](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="1609c-131"> [Restrizione](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-131"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="1609c-132"> [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-132"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="1609c-133"> [Procedura: dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-133"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="1609c-134"> [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="1609c-134"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="1609c-135"> [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="1609c-135"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
