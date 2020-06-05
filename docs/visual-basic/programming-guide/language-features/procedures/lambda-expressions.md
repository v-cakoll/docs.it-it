---
title: Espressioni lambda
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 54a9c0cf275a67c77748c32771c3c5dcbdb916d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406703"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="9faa6-102">Espressioni lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9faa6-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="9faa6-103">Un' *espressione lambda* è una funzione o una subroutine senza nome che può essere usata ovunque sia valido un delegato.</span><span class="sxs-lookup"><span data-stu-id="9faa6-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="9faa6-104">Le espressioni lambda possono essere funzioni o subroutine e possono essere a riga singola o a più righe.</span><span class="sxs-lookup"><span data-stu-id="9faa6-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="9faa6-105">È possibile passare valori dall'ambito corrente a un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="9faa6-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="9faa6-106">L' `RemoveHandler` istruzione è un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9faa6-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="9faa6-107">Non è possibile passare un'espressione lambda in per il parametro delegate di `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="9faa6-108">Le espressioni lambda vengono create usando la `Function` `Sub` parola chiave o, proprio come si crea una funzione o una subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="9faa6-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="9faa6-109">Tuttavia, le espressioni lambda sono incluse in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9faa6-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="9faa6-110">L'esempio seguente è un'espressione lambda che incrementa il relativo argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="9faa6-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="9faa6-111">Nell'esempio viene illustrata la sintassi delle espressioni lambda a riga singola e a più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="9faa6-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="9faa6-112">L'esempio seguente è un'espressione lambda che scrive un valore nella console.</span><span class="sxs-lookup"><span data-stu-id="9faa6-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="9faa6-113">Nell'esempio viene illustrata la sintassi delle espressioni lambda a riga singola e a più righe per una subroutine.</span><span class="sxs-lookup"><span data-stu-id="9faa6-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="9faa6-114">Si noti che negli esempi precedenti le espressioni lambda sono assegnate a un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="9faa6-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="9faa6-115">Ogni volta che si fa riferimento alla variabile, viene richiamata l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="9faa6-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="9faa6-116">È anche possibile dichiarare e richiamare un'espressione lambda allo stesso tempo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9faa6-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="9faa6-117">Un'espressione lambda può essere restituita come valore di una chiamata di funzione, come illustrato nell'esempio nella sezione del [contesto](#context) più avanti in questo argomento, oppure passata come argomento a un parametro che accetta un tipo di delegato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9faa6-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="9faa6-118">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="9faa6-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="9faa6-119">La sintassi di un'espressione lambda è simile a quella di una funzione o subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="9faa6-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="9faa6-120">Le differenze sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="9faa6-120">The differences are as follows:</span></span>

- <span data-ttu-id="9faa6-121">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="9faa6-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="9faa6-122">Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="9faa6-123">Le funzioni lambda a riga singola non utilizzano una `As` clausola per definire il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="9faa6-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="9faa6-124">Al contrario, il tipo viene dedotto dal valore a cui viene restituito il corpo dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="9faa6-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="9faa6-125">Se, ad esempio, il corpo dell'espressione lambda è `cust.City = "London"` , il tipo restituito sarà `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="9faa6-126">Nelle funzioni lambda a più righe è possibile specificare un tipo restituito utilizzando una `As` clausola oppure omettere la `As` clausola in modo da dedurre il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="9faa6-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="9faa6-127">Quando la `As` clausola viene omessa per una funzione lambda a più righe, il tipo restituito viene dedotto come tipo dominante da tutte le `Return` istruzioni nella funzione lambda a più righe.</span><span class="sxs-lookup"><span data-stu-id="9faa6-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="9faa6-128">Il *tipo dominante* è un tipo univoco a cui tutti gli altri tipi possono ampliarsi.</span><span class="sxs-lookup"><span data-stu-id="9faa6-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="9faa6-129">Se non è possibile determinare questo tipo univoco, il tipo dominante è il tipo univoco a cui tutti gli altri tipi nella matrice possono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="9faa6-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="9faa6-130">Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`.</span><span class="sxs-lookup"><span data-stu-id="9faa6-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="9faa6-131">In questo caso, se `Option Strict` è impostato su `On` , si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9faa6-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="9faa6-132">Se, ad esempio, le espressioni fornite all' `Return` istruzione contengono valori di tipo `Integer` , `Long` e `Double` , la matrice risultante è di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="9faa6-133">Sia `Integer` che `Long` si ampliano `Double` solo e `Double` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="9faa6-134">`Double` è pertanto il tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="9faa6-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="9faa6-135">Per altre informazioni, vedere [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="9faa6-135">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="9faa6-136">Il corpo di una funzione a riga singola deve essere un'espressione che restituisce un valore, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9faa6-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="9faa6-137">Non esiste alcuna `Return` istruzione per le funzioni a riga singola.</span><span class="sxs-lookup"><span data-stu-id="9faa6-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="9faa6-138">Il valore restituito dalla funzione a riga singola è il valore dell'espressione nel corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="9faa6-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="9faa6-139">Il corpo di una subroutine a riga singola deve essere un'istruzione a riga singola.</span><span class="sxs-lookup"><span data-stu-id="9faa6-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="9faa6-140">Le funzioni e le subroutine a riga singola non includono un' `End Function` istruzione o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="9faa6-141">È possibile specificare il tipo di dati di un parametro di espressione lambda usando la `As` parola chiave oppure il tipo di dati del parametro può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="9faa6-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="9faa6-142">È necessario dedurre tutti i parametri con i tipi di dati specificati.</span><span class="sxs-lookup"><span data-stu-id="9faa6-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="9faa6-143">`Optional``Paramarray`i parametri e non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="9faa6-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="9faa6-144">I parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="9faa6-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="9faa6-145">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="9faa6-145">Async Lambdas</span></span>

<span data-ttu-id="9faa6-146">È possibile creare facilmente espressioni lambda e istruzioni che incorporano l'elaborazione asincrona utilizzando le parole chiave dell'operatore [Async](../../../language-reference/modifiers/async.md) e [await](../../../language-reference/operators/await-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="9faa6-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../language-reference/modifiers/async.md) and [Await Operator](../../../language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="9faa6-147">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="9faa6-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```vb
Public Class Form1

    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        ' ExampleMethodAsync returns a Task.
        Await ExampleMethodAsync()
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

<span data-ttu-id="9faa6-148">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona in un' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9faa6-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="9faa6-149">Per aggiungere il gestore, aggiungere un modificatore `Async` prima dell'elenco di parametri lambda, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9faa6-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

```vb
Public Class Form1

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        AddHandler Button1.Click,
            Async Sub(sender1, e1)
                ' ExampleMethodAsync returns a Task.
                Await ExampleMethodAsync()
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."
            End Sub
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

<span data-ttu-id="9faa6-150">Per altre informazioni su come creare e usare i metodi asincroni, vedere [programmazione asincrona con Async e await](../../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="9faa6-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="9faa6-151">Context</span><span class="sxs-lookup"><span data-stu-id="9faa6-151">Context</span></span>

<span data-ttu-id="9faa6-152">Un'espressione lambda condivide il contesto con l'ambito in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="9faa6-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="9faa6-153">Dispone degli stessi diritti di accesso di qualsiasi codice scritto nell'ambito che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9faa6-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="9faa6-154">Questo include l'accesso a variabili membro, funzioni e Subs, `Me` e parametri e variabili locali nell'ambito che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9faa6-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="9faa6-155">L'accesso a variabili e parametri locali nell'ambito contenitore può estendersi oltre la durata di tale ambito.</span><span class="sxs-lookup"><span data-stu-id="9faa6-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="9faa6-156">Fino a quando un delegato che fa riferimento a un'espressione lambda non è disponibile per Garbage Collection, viene mantenuto l'accesso alle variabili nell'ambiente originale.</span><span class="sxs-lookup"><span data-stu-id="9faa6-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="9faa6-157">Nell'esempio seguente la variabile `target` è locale in `makeTheGame` , il metodo in cui è definita l'espressione lambda `playTheGame` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="9faa6-158">Si noti che l'espressione lambda restituita, assegnata a `takeAGuess` in `Main` , ha ancora accesso alla variabile locale `target` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="9faa6-159">Nell'esempio seguente viene illustrata l'ampia gamma di diritti di accesso dell'espressione lambda nidificata.</span><span class="sxs-lookup"><span data-stu-id="9faa6-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="9faa6-160">Quando l'espressione lambda restituita viene eseguita da `Main` come `aDel` , accede a questi elementi:</span><span class="sxs-lookup"><span data-stu-id="9faa6-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="9faa6-161">Un campo della classe in cui è definito:`aField`</span><span class="sxs-lookup"><span data-stu-id="9faa6-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="9faa6-162">Proprietà della classe in cui è definita:`aProp`</span><span class="sxs-lookup"><span data-stu-id="9faa6-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="9faa6-163">Parametro del metodo `functionWithNestedLambda` , in cui è definito:`level1`</span><span class="sxs-lookup"><span data-stu-id="9faa6-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="9faa6-164">Variabile locale di `functionWithNestedLambda` :`localVar`</span><span class="sxs-lookup"><span data-stu-id="9faa6-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="9faa6-165">Parametro dell'espressione lambda in cui è annidato:`level2`</span><span class="sxs-lookup"><span data-stu-id="9faa6-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="9faa6-166">Conversione in un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="9faa6-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="9faa6-167">Un'espressione lambda può essere convertita in modo implicito in un tipo delegato compatibile.</span><span class="sxs-lookup"><span data-stu-id="9faa6-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="9faa6-168">Per informazioni sui requisiti generali per la compatibilità, vedere [conversione di un delegato rilassato](../delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="9faa6-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="9faa6-169">Nell'esempio di codice seguente, ad esempio, viene illustrata un'espressione lambda che converte in modo implicito in `Func(Of Integer, Boolean)` o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9faa6-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="9faa6-170">Nell'esempio di codice seguente viene illustrata un'espressione lambda che converte in modo implicito in `Sub(Of Double, String, Double)` o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9faa6-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="9faa6-171">Quando si assegnano espressioni lambda a delegati o vengono passati come argomenti a procedure, è possibile specificare i nomi dei parametri ma omettere i relativi tipi di dati, consentendo ai tipi di essere ricavati dal delegato.</span><span class="sxs-lookup"><span data-stu-id="9faa6-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="9faa6-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="9faa6-172">Examples</span></span>

- <span data-ttu-id="9faa6-173">Nell'esempio seguente viene definita un'espressione lambda che restituisce `True` se l'argomento di tipo valore nullable ha un valore assegnato e `False` se il relativo valore è `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="9faa6-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="9faa6-174">Nell'esempio seguente viene definita un'espressione lambda che restituisce l'indice dell'ultimo elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="9faa6-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="9faa6-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9faa6-175">See also</span></span>

- [<span data-ttu-id="9faa6-176">Procedure</span><span class="sxs-lookup"><span data-stu-id="9faa6-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9faa6-177">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9faa6-177">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
- [<span data-ttu-id="9faa6-178">Delegati</span><span class="sxs-lookup"><span data-stu-id="9faa6-178">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="9faa6-179">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="9faa6-179">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="9faa6-180">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="9faa6-180">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9faa6-181">Tipi di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="9faa6-181">Nullable Value Types</span></span>](../data-types/nullable-value-types.md)
- [<span data-ttu-id="9faa6-182">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9faa6-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="9faa6-183">Procedura: creare un'espressione lambda</span><span class="sxs-lookup"><span data-stu-id="9faa6-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="9faa6-184">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="9faa6-184">Relaxed Delegate Conversion</span></span>](../delegates/relaxed-delegate-conversion.md)
