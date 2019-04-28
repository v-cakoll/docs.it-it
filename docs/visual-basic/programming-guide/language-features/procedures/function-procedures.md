---
title: Routine Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 568489d6034316e895cd999801241fa995aadefa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864403"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="125e0-102">Routine Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="125e0-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="125e0-103">Oggetto `Function` routine è una serie di istruzioni di Visual Basic racchiuse tra il `Function` e `End Function` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="125e0-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="125e0-104">Il `Function` routine esegue un'attività e quindi restituisce il controllo al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="125e0-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="125e0-105">Quando restituisce il controllo, restituisce anche un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="125e0-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="125e0-106">Ogni volta che la procedura viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Function` istruzione e terminando con il primo `End Function`, `Exit Function`, o `Return` rilevata istruzione.</span><span class="sxs-lookup"><span data-stu-id="125e0-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="125e0-107">È possibile definire un `Function` procedure in un modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="125e0-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="125e0-108">Si tratta di `Public` per impostazione predefinita, il che significa è possibile chiamare da qualsiasi posizione nell'applicazione che dispone dell'accesso per il modulo, classe o struttura in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="125e0-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="125e0-109">Oggetto `Function` procedure può accettare argomenti, ad esempio le costanti, variabili o espressioni che vengono passate al metodo dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="125e0-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="125e0-110">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="125e0-110">Declaration Syntax</span></span>  
 <span data-ttu-id="125e0-111">La sintassi per dichiarare un `Function` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="125e0-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="125e0-112">Il *modificatori* può specificare il livello di accesso e le informazioni riguardanti l'overload, si esegue l'override, la condivisione e lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="125e0-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="125e0-113">Per altre informazioni, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="125e0-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="125e0-114">Ogni parametro è dichiarare la stessa procedura valida per [Sub (routine)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="125e0-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="125e0-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="125e0-115">Data Type</span></span>  
 <span data-ttu-id="125e0-116">Ogni `Function` routine ha un tipo di dati, viene semplicemente tutte le variabili.</span><span class="sxs-lookup"><span data-stu-id="125e0-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="125e0-117">Questo tipo di dati è specificato mediante il `As` clausola nel `Function` istruzione che determina il tipo di dati del valore che la funzione restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="125e0-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="125e0-118">Le dichiarazioni di esempio seguenti illustrano questo.</span><span class="sxs-lookup"><span data-stu-id="125e0-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="125e0-119">Per altre informazioni, vedere "Part" nella [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="125e0-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="125e0-120">Restituzione di valori</span><span class="sxs-lookup"><span data-stu-id="125e0-120">Returning Values</span></span>  
 <span data-ttu-id="125e0-121">Il valore un `Function` procedure invia informazioni al codice chiamante viene chiamato il relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="125e0-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="125e0-122">La procedura restituisce questo valore in uno dei due modi:</span><span class="sxs-lookup"><span data-stu-id="125e0-122">The procedure returns this value in one of two ways:</span></span>  
  
- <span data-ttu-id="125e0-123">Usa il `Return` istruzione per specificare il valore restituito e restituisce il controllo immediatamente a nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="125e0-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="125e0-124">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="125e0-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- <span data-ttu-id="125e0-125">Assegna un valore per il proprio nome di funzione in una o più istruzioni della procedura.</span><span class="sxs-lookup"><span data-stu-id="125e0-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="125e0-126">Il controllo viene restituito al programma chiamante fino a un `Exit Function` o `End Function` viene eseguita un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="125e0-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="125e0-127">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="125e0-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="125e0-128">Il vantaggio di assegnazione del valore restituito per il nome della funzione è che il controllo viene restituito dalla procedura finché non viene rilevata un' `Exit Function` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="125e0-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="125e0-129">In questo modo è possibile assegnare un valore preliminare e modificarlo in un secondo momento se necessario.</span><span class="sxs-lookup"><span data-stu-id="125e0-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="125e0-130">Per altre informazioni sulla restituzione di valori, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="125e0-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="125e0-131">Per informazioni sulla restituzione di matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="125e0-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="125e0-132">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="125e0-132">Calling Syntax</span></span>  
 <span data-ttu-id="125e0-133">Si richiama un `Function` procedura includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="125e0-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="125e0-134">È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="125e0-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="125e0-135">Se viene fornito alcun argomento, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="125e0-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="125e0-136">La sintassi per una chiamata a un `Function` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="125e0-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="125e0-137">*lvalue*`=`*nomefunzione* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="125e0-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="125e0-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="125e0-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="125e0-139">Quando si chiama un `Function` procedura, non è necessario usare il relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="125e0-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="125e0-140">In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="125e0-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="125e0-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> è spesso definito in questo modo.</span><span class="sxs-lookup"><span data-stu-id="125e0-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="125e0-142">Illustrazione di dichiarazione e di chiamata</span><span class="sxs-lookup"><span data-stu-id="125e0-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="125e0-143">Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="125e0-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="125e0-144">Nell'esempio seguente viene illustrata una tipica chiamata alla `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="125e0-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="125e0-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="125e0-145">See also</span></span>

- [<span data-ttu-id="125e0-146">Routine</span><span class="sxs-lookup"><span data-stu-id="125e0-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="125e0-147">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="125e0-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="125e0-148">Routine Property</span><span class="sxs-lookup"><span data-stu-id="125e0-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="125e0-149">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="125e0-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="125e0-150">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="125e0-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="125e0-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="125e0-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="125e0-152">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="125e0-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="125e0-153">Procedura: Restituisce il valore da una routine</span><span class="sxs-lookup"><span data-stu-id="125e0-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="125e0-154">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="125e0-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
