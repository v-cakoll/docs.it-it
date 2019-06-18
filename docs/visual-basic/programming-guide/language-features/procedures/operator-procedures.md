---
title: Routine di operatore (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: d62c3480db56b5cbf22c1f3f6ff59ab220a48b09
ms.sourcegitcommit: 5e05f983e63d5bbd8c0b246d02c6e4f23d2fc1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2019
ms.locfileid: "67152042"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="d6f0c-102">Routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6f0c-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="d6f0c-103">Una routine di operatore è una serie di istruzioni di Visual Basic che definiscono il comportamento di un operatore standard (ad esempio `*`, `<>`, o `And`) in una classe o struttura definita.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="d6f0c-104">Questo è l'acronimo *overload degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="d6f0c-105">Quando definire le routine di operatore</span><span class="sxs-lookup"><span data-stu-id="d6f0c-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="d6f0c-106">Dopo aver definito una classe o struttura, è possibile dichiarare variabili sia del tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="d6f0c-107">In alcuni casi tale variabile deve far parte di un'operazione come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="d6f0c-108">A tale scopo, deve essere un operando di un operatore.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="d6f0c-109">Visual Basic definisce gli operatori solo sui tipi di dati più importanti.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="d6f0c-110">È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="d6f0c-111">Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d6f0c-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="d6f0c-112">Tipi di routine di operatore</span><span class="sxs-lookup"><span data-stu-id="d6f0c-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="d6f0c-113">Una routine di operatore può essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6f0c-113">An operator procedure can be one of the following types:</span></span>  
  
- <span data-ttu-id="d6f0c-114">Una definizione di un operatore unario dove l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="d6f0c-115">Una definizione di un operatore binario in cui almeno uno degli argomenti è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="d6f0c-116">Una definizione di un operatore di conversione in cui l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="d6f0c-117">Una definizione di un operatore di conversione che restituisce il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="d6f0c-118">Gli operatori di conversione sono sempre unario e utilizzare sempre `CType` dell'operatore a cui si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="d6f0c-119">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="d6f0c-119">Declaration Syntax</span></span>  
 <span data-ttu-id="d6f0c-120">La sintassi per dichiarare una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="d6f0c-120">The syntax for declaring an operator procedure is as follows:</span></span>  
 
 ```vb 
 Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype  
  
 ' Statements of the operator procedure.
  
 End Operator
 ```
 
 <span data-ttu-id="d6f0c-121">Si utilizza il `Widening` o `Narrowing` parola chiave solo su un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-121">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="d6f0c-122">Il simbolo dell'operatore è sempre [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) per un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-122">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="d6f0c-123">Si dichiarano due operandi per definire un operatore binario, e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-123">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="d6f0c-124">Tutti gli operandi devono essere dichiarati `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-124">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="d6f0c-125">Si dichiara ogni operando simile a quello dichiarare i parametri per [Sub (routine)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d6f0c-125">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="d6f0c-126">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d6f0c-126">Data Type</span></span>  
 <span data-ttu-id="d6f0c-127">Poiché si sta definendo un operatore in una classe o struttura definita, almeno uno degli operandi deve essere del tipo di dati di tale classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-127">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="d6f0c-128">Per un operatore di conversione di tipi, l'operando o il tipo restituito deve essere del tipo di dati della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-128">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="d6f0c-129">Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d6f0c-129">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="d6f0c-130">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="d6f0c-130">Calling Syntax</span></span>  
 <span data-ttu-id="d6f0c-131">Una routine di operatore è richiamare in modo implicito usando il simbolo di operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-131">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="d6f0c-132">Gli operandi vengono forniti la stessa procedura valida per gli operatori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-132">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="d6f0c-133">La sintassi per una chiamata implicita a una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="d6f0c-133">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="d6f0c-134">`Dim testStruct As`  *nomestruttura*</span><span class="sxs-lookup"><span data-stu-id="d6f0c-134">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="d6f0c-135">`Dim testNewStruct As`  *nomestruttura*`= testStruct`*simbolooperatore*  `10`</span><span class="sxs-lookup"><span data-stu-id="d6f0c-135">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="d6f0c-136">Illustrazione di dichiarazione e di chiamata</span><span class="sxs-lookup"><span data-stu-id="d6f0c-136">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="d6f0c-137">La struttura seguente archivia un valore intero con segno a 128 bit come le parti costituenti alto e basso.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-137">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="d6f0c-138">Definisce i `+` operaa a add due `veryLong` i valori e generare una risultante `veryLong` valore.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-138">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="d6f0c-139">Nell'esempio seguente viene illustrata una tipica chiamata per il `+` operatore definito in `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="d6f0c-139">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="d6f0c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f0c-140">See also</span></span>

- [<span data-ttu-id="d6f0c-141">Routine</span><span class="sxs-lookup"><span data-stu-id="d6f0c-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d6f0c-142">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="d6f0c-142">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="d6f0c-143">Routine Function</span><span class="sxs-lookup"><span data-stu-id="d6f0c-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="d6f0c-144">Routine Property</span><span class="sxs-lookup"><span data-stu-id="d6f0c-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d6f0c-145">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="d6f0c-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d6f0c-146">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="d6f0c-146">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="d6f0c-147">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="d6f0c-147">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="d6f0c-148">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="d6f0c-148">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="d6f0c-149">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="d6f0c-149">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="d6f0c-150">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="d6f0c-150">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
