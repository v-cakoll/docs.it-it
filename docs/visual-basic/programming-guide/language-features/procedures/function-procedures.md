---
title: routine di Function
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: d7a0293e2ec520c2278f67156be56315d1def2b5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780086"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="8d3fd-102">Routine Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d3fd-102">Function procedures (Visual Basic)</span></span>

<span data-ttu-id="8d3fd-103">Una `Function` routine è una serie di istruzioni Visual Basic racchiuse tra le istruzioni `Function` e `End Function`.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="8d3fd-104">La procedura `Function` esegue un'attività e quindi restituisce il controllo al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="8d3fd-105">Quando restituisce il controllo, restituisce anche un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-105">When it returns control, it also returns a value to the calling code.</span></span>

<span data-ttu-id="8d3fd-106">Ogni volta che viene chiamata la stored procedure, le istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo l'istruzione `Function` e terminando con la prima istruzione `End Function`, `Exit Function`o `Return` rilevata.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>

<span data-ttu-id="8d3fd-107">È possibile definire una procedura di `Function` in un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="8d3fd-108">È `Public` per impostazione predefinita, il che significa che è possibile chiamarlo da qualsiasi punto dell'applicazione che abbia accesso al modulo, alla classe o alla struttura in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>

<span data-ttu-id="8d3fd-109">Una procedura `Function` può assumere argomenti, ad esempio costanti, variabili o espressioni, che vengono passati al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="8d3fd-110">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="8d3fd-110">Declaration syntax</span></span>

<span data-ttu-id="8d3fd-111">La sintassi per la dichiarazione di una procedura `Function` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="8d3fd-111">The syntax for declaring a `Function` procedure is as follows:</span></span>

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

<span data-ttu-id="8d3fd-112">I *modificatori* possono specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e all'ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="8d3fd-113">Per ulteriori informazioni, vedere [istruzione Function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d3fd-113">For more information, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

<span data-ttu-id="8d3fd-114">Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d3fd-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="8d3fd-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8d3fd-115">Data type</span></span>

<span data-ttu-id="8d3fd-116">Ogni `Function` routine ha un tipo di dati, proprio come ogni variabile.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="8d3fd-117">Questo tipo di dati viene specificato dalla clausola `As` nell'istruzione `Function` e determina il tipo di dati del valore restituito dalla funzione al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="8d3fd-118">Questa operazione viene illustrata nelle dichiarazioni di esempio seguenti.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-118">The following sample declarations illustrate this.</span></span>

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

<span data-ttu-id="8d3fd-119">Per ulteriori informazioni, vedere l'argomento relativo alle parti nell' [istruzione Function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d3fd-119">For more information, see "Parts" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

### <a name="returning-values"></a><span data-ttu-id="8d3fd-120">Restituzione di valori</span><span class="sxs-lookup"><span data-stu-id="8d3fd-120">Returning values</span></span>

<span data-ttu-id="8d3fd-121">Il valore restituito da una procedura `Function` al codice chiamante viene chiamato valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="8d3fd-122">La procedura restituisce questo valore in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3fd-122">The procedure returns this value in one of two ways:</span></span>

- <span data-ttu-id="8d3fd-123">Usa l'istruzione `Return` per specificare il valore restituito e restituisce immediatamente il controllo al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="8d3fd-124">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-124">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- <span data-ttu-id="8d3fd-125">Assegna un valore al relativo nome di funzione in una o più istruzioni della procedura.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="8d3fd-126">Il controllo non torna al programma chiamante finché non viene eseguita un'istruzione `Exit Function` o `End Function`.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="8d3fd-127">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-127">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

<span data-ttu-id="8d3fd-128">Il vantaggio derivante dall'assegnazione del valore restituito al nome della funzione è che il controllo non restituisce dalla procedura fino a quando non rileva un'istruzione `Exit Function` o `End Function`.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="8d3fd-129">In questo modo è possibile assegnare un valore preliminare e modificarlo in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>

<span data-ttu-id="8d3fd-130">Per ulteriori informazioni sulla restituzione di valori, vedere [istruzione Function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d3fd-130">For more information about returning values, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="8d3fd-131">Per informazioni sulla restituzione di matrici, vedere [matrici](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8d3fd-131">For information about returning arrays, see [Arrays](../arrays/index.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="8d3fd-132">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="8d3fd-132">Calling syntax</span></span>

<span data-ttu-id="8d3fd-133">Si richiama una procedura di `Function` includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="8d3fd-134">È necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="8d3fd-135">Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="8d3fd-136">Di seguito è riportata la sintassi per una chiamata a una procedura `Function`.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-136">The syntax for a call to a `Function` procedure is as follows.</span></span>

<span data-ttu-id="8d3fd-137">*lvalue*`=`*FunctionName* `[(` *argomento* `)]`</span><span class="sxs-lookup"><span data-stu-id="8d3fd-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>

<span data-ttu-id="8d3fd-138">`If ((` *functionname* `[(` l' *argomento* `)] / 3) <=`*espressione* `) Then`</span><span class="sxs-lookup"><span data-stu-id="8d3fd-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>

<span data-ttu-id="8d3fd-139">Quando si chiama una routine di `Function`, non è necessario usare il relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="8d3fd-140">In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="8d3fd-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> viene spesso chiamato in questo modo.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="8d3fd-142">Illustrazione della dichiarazione e della chiamata</span><span class="sxs-lookup"><span data-stu-id="8d3fd-142">Illustration of declaration and call</span></span>

<span data-ttu-id="8d3fd-143">La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

<span data-ttu-id="8d3fd-144">Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="8d3fd-144">The following example shows a typical call to `hypotenuse`.</span></span>

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a><span data-ttu-id="8d3fd-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d3fd-145">See also</span></span>

- [<span data-ttu-id="8d3fd-146">Routine</span><span class="sxs-lookup"><span data-stu-id="8d3fd-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="8d3fd-147">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="8d3fd-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="8d3fd-148">Routine Property</span><span class="sxs-lookup"><span data-stu-id="8d3fd-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="8d3fd-149">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="8d3fd-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="8d3fd-150">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="8d3fd-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="8d3fd-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="8d3fd-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8d3fd-152">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="8d3fd-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="8d3fd-153">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="8d3fd-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="8d3fd-154">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="8d3fd-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
