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
ms.openlocfilehash: 80c9a77494be95365899c6a25435fcfc5d2a7293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791976"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="b271a-102">Routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b271a-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="b271a-103">Una routine di operatore è una serie di istruzioni di Visual Basic che definiscono il comportamento di un operatore standard (ad esempio `*`, `<>`, o `And`) in una classe o struttura definita.</span><span class="sxs-lookup"><span data-stu-id="b271a-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="b271a-104">Questo è l'acronimo *overload degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="b271a-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="b271a-105">Quando definire le routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b271a-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="b271a-106">Dopo aver definito una classe o struttura, è possibile dichiarare variabili sia del tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="b271a-107">In alcuni casi tale variabile deve far parte di un'operazione come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="b271a-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="b271a-108">A tale scopo, deve essere un operando di un operatore.</span><span class="sxs-lookup"><span data-stu-id="b271a-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="b271a-109">Visual Basic definisce gli operatori solo sui tipi di dati più importanti.</span><span class="sxs-lookup"><span data-stu-id="b271a-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="b271a-110">È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="b271a-111">Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b271a-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="b271a-112">Tipi di routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b271a-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="b271a-113">Una routine di operatore può essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b271a-113">An operator procedure can be one of the following types:</span></span>  
  
- <span data-ttu-id="b271a-114">Una definizione di un operatore unario dove l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="b271a-115">Una definizione di un operatore binario in cui almeno uno degli argomenti è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="b271a-116">Una definizione di un operatore di conversione in cui l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="b271a-117">Una definizione di un operatore di conversione che restituisce il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="b271a-118">Gli operatori di conversione sono sempre unario e utilizzare sempre `CType` dell'operatore a cui si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="b271a-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="b271a-119">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="b271a-119">Declaration Syntax</span></span>  
 <span data-ttu-id="b271a-120">La sintassi per dichiarare una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="b271a-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="b271a-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *simbolooperatore* `(` *operand1*`[,`*operand2* `]) As` *datatype*</span><span class="sxs-lookup"><span data-stu-id="b271a-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="b271a-122">Si utilizza il `Widening` o `Narrowing` parola chiave solo su un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="b271a-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="b271a-123">Il simbolo dell'operatore è sempre [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) per un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="b271a-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="b271a-124">Si dichiarano due operandi per definire un operatore binario, e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="b271a-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="b271a-125">Tutti gli operandi devono essere dichiarati `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="b271a-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="b271a-126">Si dichiara ogni operando simile a quello dichiarare i parametri per [Sub (routine)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b271a-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="b271a-127">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b271a-127">Data Type</span></span>  
 <span data-ttu-id="b271a-128">Poiché si sta definendo un operatore in una classe o struttura definita, almeno uno degli operandi deve essere del tipo di dati di tale classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="b271a-129">Per un operatore di conversione di tipi, l'operando o il tipo restituito deve essere del tipo di dati della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b271a-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="b271a-130">Per altre informazioni, vedere [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b271a-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="b271a-131">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="b271a-131">Calling Syntax</span></span>  
 <span data-ttu-id="b271a-132">Una routine di operatore è richiamare in modo implicito usando il simbolo di operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="b271a-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="b271a-133">Gli operandi vengono forniti la stessa procedura valida per gli operatori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b271a-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="b271a-134">La sintassi per una chiamata implicita a una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="b271a-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="b271a-135">`Dim testStruct As`  *nomestruttura*</span><span class="sxs-lookup"><span data-stu-id="b271a-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="b271a-136">`Dim testNewStruct As`  *nomestruttura*`= testStruct`*simbolooperatore*  `10`</span><span class="sxs-lookup"><span data-stu-id="b271a-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="b271a-137">Illustrazione di dichiarazione e di chiamata</span><span class="sxs-lookup"><span data-stu-id="b271a-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="b271a-138">La struttura seguente archivia un valore intero con segno a 128 bit come le parti costituenti alto e basso.</span><span class="sxs-lookup"><span data-stu-id="b271a-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="b271a-139">Definisce i `+` operaa a add due `veryLong` i valori e generare una risultante `veryLong` valore.</span><span class="sxs-lookup"><span data-stu-id="b271a-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="b271a-140">Nell'esempio seguente viene illustrata una tipica chiamata per il `+` operatore definito in `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="b271a-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="b271a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b271a-141">See also</span></span>

- [<span data-ttu-id="b271a-142">Routine</span><span class="sxs-lookup"><span data-stu-id="b271a-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b271a-143">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="b271a-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b271a-144">Routine Function</span><span class="sxs-lookup"><span data-stu-id="b271a-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="b271a-145">Routine Property</span><span class="sxs-lookup"><span data-stu-id="b271a-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b271a-146">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="b271a-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b271a-147">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="b271a-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="b271a-148">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="b271a-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="b271a-149">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="b271a-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="b271a-150">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b271a-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="b271a-151">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="b271a-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
