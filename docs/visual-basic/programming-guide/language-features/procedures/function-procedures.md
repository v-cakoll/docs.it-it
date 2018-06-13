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
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655535"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="2fd26-102">Routine Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fd26-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="2fd26-103">Un `Function` stored procedure è una serie di istruzioni di Visual Basic racchiuse tra il `Function` e `End Function` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="2fd26-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="2fd26-104">Il `Function` routine esegue un'attività e quindi restituisce il controllo al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2fd26-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="2fd26-105">Quando restituisce il controllo, restituisce inoltre un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2fd26-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="2fd26-106">Ogni volta che la routine viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Function` istruzione e terminando con il primo `End Function`, `Exit Function`, o `Return` rilevata istruzione.</span><span class="sxs-lookup"><span data-stu-id="2fd26-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="2fd26-107">È possibile definire un `Function` procedura in un modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="2fd26-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="2fd26-108">È `Public` per impostazione predefinita, il che significa è possibile chiamare da qualsiasi posizione nell'applicazione che ha accesso al modulo, classe o struttura in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="2fd26-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="2fd26-109">Oggetto `Function` procedure può accettare argomenti, ad esempio costanti, variabili o espressioni, che vengono passate al metodo dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2fd26-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="2fd26-110">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="2fd26-110">Declaration Syntax</span></span>  
 <span data-ttu-id="2fd26-111">La sintassi per dichiarare un `Function` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2fd26-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="2fd26-112">Il *modificatori* può specificare il livello di accesso e le informazioni su overload, override, condivisione e shadowing.</span><span class="sxs-lookup"><span data-stu-id="2fd26-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="2fd26-113">Per ulteriori informazioni, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2fd26-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="2fd26-114">Ciascun parametro viene dichiarato esattamente come avviene per [Sub (routine)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2fd26-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="2fd26-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2fd26-115">Data Type</span></span>  
 <span data-ttu-id="2fd26-116">Ogni `Function` routine ha un tipo di dati, solo ogni variabile.</span><span class="sxs-lookup"><span data-stu-id="2fd26-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="2fd26-117">Questo tipo di dati è specificato mediante il `As` clausola il `Function` istruzione e determina il tipo di dati del valore restituito dalla funzione al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2fd26-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="2fd26-118">Le dichiarazioni di esempio seguente viene illustrato questo.</span><span class="sxs-lookup"><span data-stu-id="2fd26-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="2fd26-119">Per ulteriori informazioni, vedere "Parti" in [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2fd26-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="2fd26-120">Restituzione di valori</span><span class="sxs-lookup"><span data-stu-id="2fd26-120">Returning Values</span></span>  
 <span data-ttu-id="2fd26-121">Il valore di un `Function` procedure invia back al codice chiamante viene chiamato il relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2fd26-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="2fd26-122">La procedura restituisce questo valore in uno dei due modi:</span><span class="sxs-lookup"><span data-stu-id="2fd26-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="2fd26-123">Usa il `Return` istruzione per specificare il valore restituito e restituisce il controllo immediatamente al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="2fd26-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="2fd26-124">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2fd26-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="2fd26-125">Assegna un valore per il proprio nome di funzione in una o più istruzioni della procedura.</span><span class="sxs-lookup"><span data-stu-id="2fd26-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="2fd26-126">Il controllo viene restituito al programma chiamante finché un `Exit Function` o `End Function` viene eseguita un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="2fd26-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="2fd26-127">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2fd26-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="2fd26-128">Il vantaggio dell'assegnazione del valore restituito per il nome della funzione è che il controllo viene restituito dalla routine finché incontra un `Exit Function` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2fd26-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="2fd26-129">Ciò consente di assegnare un valore preliminare e modificarlo in un secondo momento se necessario.</span><span class="sxs-lookup"><span data-stu-id="2fd26-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="2fd26-130">Per ulteriori informazioni sulla restituzione di valori, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2fd26-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="2fd26-131">Per informazioni sulla restituzione di matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="2fd26-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="2fd26-132">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="2fd26-132">Calling Syntax</span></span>  
 <span data-ttu-id="2fd26-133">Si richiama un `Function` procedura includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2fd26-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="2fd26-134">È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="2fd26-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="2fd26-135">Se non vengono forniti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="2fd26-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="2fd26-136">La sintassi per una chiamata a un `Function` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2fd26-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="2fd26-137">*lvalue*`=`*functionname* `[(` *argumentlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="2fd26-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="2fd26-138">`If ((` *nomefunzione* `[(` *argumentlist* `)] / 3) <=` *espressione*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="2fd26-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="2fd26-139">Quando si chiama un `Function` routine, non è necessario utilizzare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2fd26-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="2fd26-140">In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2fd26-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="2fd26-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> è spesso definito in questo modo.</span><span class="sxs-lookup"><span data-stu-id="2fd26-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="2fd26-142">Illustrazione di dichiarazione e chiamata</span><span class="sxs-lookup"><span data-stu-id="2fd26-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="2fd26-143">Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo, in base ai valori per i due lati.</span><span class="sxs-lookup"><span data-stu-id="2fd26-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="2fd26-144">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="2fd26-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2fd26-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fd26-145">See Also</span></span>  
 [<span data-ttu-id="2fd26-146">Routine</span><span class="sxs-lookup"><span data-stu-id="2fd26-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="2fd26-147">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="2fd26-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="2fd26-148">Routine Property</span><span class="sxs-lookup"><span data-stu-id="2fd26-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="2fd26-149">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="2fd26-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="2fd26-150">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="2fd26-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="2fd26-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="2fd26-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="2fd26-152">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="2fd26-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="2fd26-153">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="2fd26-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="2fd26-154">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="2fd26-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
