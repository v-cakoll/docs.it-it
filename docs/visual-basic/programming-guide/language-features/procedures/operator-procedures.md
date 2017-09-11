---
title: Routine di operatore (Visual Basic) | Documenti di Microsoft
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
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
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
ms.openlocfilehash: 3b2e8466ad355521dcec3cf7b2949037e569eb9a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="b6fb9-102">Routine di operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6fb9-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="b6fb9-103">Una routine di operatore è una serie di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] le istruzioni che definiscono il comportamento di un operatore standard (ad esempio `*`, `<>`, o `And`) su una classe o una struttura definita.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-103">An operator procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="b6fb9-104">Detta anche *l'overload degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="b6fb9-105">Quando definire una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b6fb9-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="b6fb9-106">Dopo aver definito una classe o struttura, è possibile dichiarare variabili di tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="b6fb9-107">A volte tale variabile deve far parte di un'operazione come parte di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="b6fb9-108">A tale scopo, deve essere un operando di un operatore.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-108">To do this, it must be an operand of an operator.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b6fb9-109">Definisce gli operatori solo sui tipi di dati più importanti.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-109"> defines operators only on its fundamental data types.</span></span> <span data-ttu-id="b6fb9-110">È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono di tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="b6fb9-111">Per ulteriori informazioni, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6fb9-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="b6fb9-112">Tipi di routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b6fb9-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="b6fb9-113">Una routine di operatore può essere uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="b6fb9-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="b6fb9-114">Definizione di un operatore unario in cui l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="b6fb9-115">Una definizione di un operatore binario in cui almeno uno degli argomenti è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="b6fb9-116">Definizione di un operatore di conversione in cui l'argomento è del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="b6fb9-117">Definizione di un operatore di conversione che restituisce il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="b6fb9-118">Operatori di conversione sono sempre unari e utilizzare sempre `CType` come l'operatore che si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="b6fb9-119">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="b6fb9-119">Declaration Syntax</span></span>  
 <span data-ttu-id="b6fb9-120">La sintassi per dichiarare una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="b6fb9-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="b6fb9-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="b6fb9-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="b6fb9-122">Utilizzare il `Widening` o `Narrowing` parola chiave solo su un operatore di conversione del tipo.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="b6fb9-123">Il simbolo dell'operatore è sempre [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) per un operatore di conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="b6fb9-124">Dichiarare due operandi per definire un operatore binario, e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione del tipo.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="b6fb9-125">Tutti gli operandi devono essere dichiarati `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="b6fb9-126">Dichiarare ogni operando esattamente alla dichiarazione dei parametri per [Sub (routine)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b6fb9-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="b6fb9-127">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b6fb9-127">Data Type</span></span>  
 <span data-ttu-id="b6fb9-128">Poiché si sta definendo un operatore su una classe o una struttura definita, almeno uno degli operandi deve essere del tipo di dati di tale classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="b6fb9-129">Per un operatore di conversione di tipo, l'operando o il tipo restituito deve essere del tipo di dati della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="b6fb9-130">Per ulteriori informazioni, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6fb9-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="b6fb9-131">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="b6fb9-131">Calling Syntax</span></span>  
 <span data-ttu-id="b6fb9-132">Richiamare una routine di operatore in modo implicito utilizzando il simbolo di operatore in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="b6fb9-133">Gli operandi vengono forniti il così come avviene per gli operatori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="b6fb9-134">La sintassi per una chiamata implicita a una routine di operatore è come segue:</span><span class="sxs-lookup"><span data-stu-id="b6fb9-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="b6fb9-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="b6fb9-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="b6fb9-136">`Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol    *  `10`</span><span class="sxs-lookup"><span data-stu-id="b6fb9-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="b6fb9-137">Illustrazione di dichiarazione e chiamata</span><span class="sxs-lookup"><span data-stu-id="b6fb9-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="b6fb9-138">La seguente struttura archivia un valore intero con segno a 128 bit come le parti costitutive in alto e basso.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="b6fb9-139">Definisce il `+` operatore per aggiungere due `veryLong` valori e generare una risultante `veryLong` valore.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 <span data-ttu-id="b6fb9-140">[!code-vb[VbVbcnProcedures&#23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b6fb9-140">[!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="b6fb9-141">Nell'esempio seguente viene illustrata una tipica chiamata per il `+` operatore definito in `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="b6fb9-141">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 <span data-ttu-id="b6fb9-142">[!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b6fb9-142">[!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="b6fb9-143">Per ulteriori informazioni ed esempi, vedere [overload degli operatori in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="b6fb9-143">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fb9-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fb9-144">See Also</span></span>  
 <span data-ttu-id="b6fb9-145">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-145">[Procedures](./index.md) </span></span>  
<span data-ttu-id="b6fb9-146"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-146"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="b6fb9-147"> [Routine di funzione](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-147"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="b6fb9-148"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-148"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="b6fb9-149"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-149"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="b6fb9-150"> [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-150"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="b6fb9-151"> [Procedura: definire un operatore](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-151"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="b6fb9-152"> [Procedura: definire un operatore di conversione](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-152"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="b6fb9-153"> [Procedura: chiamare una routine di operatore](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="b6fb9-153"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="b6fb9-154"> [Procedura: Usare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)</span><span class="sxs-lookup"><span data-stu-id="b6fb9-154"> [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md)</span></span>
