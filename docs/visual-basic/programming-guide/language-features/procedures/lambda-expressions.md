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
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249669"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="d1203-102">Espressioni lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1203-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="d1203-103">*Un'espressione lambda* è una funzione o una subroutine senza un nome che può essere utilizzata ovunque sia valido un delegato.</span><span class="sxs-lookup"><span data-stu-id="d1203-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="d1203-104">Le espressioni lambda possono essere funzioni o subroutine e possono essere a riga singola o su più righe.</span><span class="sxs-lookup"><span data-stu-id="d1203-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="d1203-105">È possibile passare valori dall'ambito corrente a un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="d1203-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="d1203-106">L'istruzione è un'eccezione. `RemoveHandler`</span><span class="sxs-lookup"><span data-stu-id="d1203-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="d1203-107">Non è possibile passare un'espressione `RemoveHandler`lambda per il parametro delegato di .</span><span class="sxs-lookup"><span data-stu-id="d1203-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="d1203-108">Le espressioni lambda vengono `Function` `Sub` create utilizzando la parola chiave o , così come si crea una funzione o una subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="d1203-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="d1203-109">Tuttavia, le espressioni lambda sono incluse in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d1203-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="d1203-110">L'esempio seguente è un'espressione lambda che incrementa il relativo argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="d1203-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="d1203-111">L'esempio mostra sia la sintassi dell'espressione lambda a riga singola che a più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="d1203-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="d1203-112">L'esempio seguente è un'espressione lambda che scrive un valore nella console.</span><span class="sxs-lookup"><span data-stu-id="d1203-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="d1203-113">Nell'esempio viene illustrata la sintassi delle espressioni lambda a riga singola e su più righe per una subroutine.</span><span class="sxs-lookup"><span data-stu-id="d1203-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="d1203-114">Si noti che negli esempi precedenti le espressioni lambda vengono assegnate a un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="d1203-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="d1203-115">Ogni volta che si fa riferimento alla variabile, si richiama l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="d1203-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="d1203-116">È anche possibile dichiarare e richiamare un'espressione lambda contemporaneamente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d1203-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="d1203-117">Un'espressione lambda può essere restituita come valore di una chiamata di funzione (come illustrato nell'esempio nella sezione [Contesto](#context) più avanti in questo argomento) o passata come argomento a un parametro che accetta un tipo delegato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d1203-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="d1203-118">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="d1203-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="d1203-119">La sintassi di un'espressione lambda è simile a quella di una funzione o di una subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="d1203-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="d1203-120">Le differenze sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1203-120">The differences are as follows:</span></span>

- <span data-ttu-id="d1203-121">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="d1203-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="d1203-122">Le espressioni lambda non possono `Overloads` `Overrides`avere modificatori, ad esempio o .</span><span class="sxs-lookup"><span data-stu-id="d1203-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="d1203-123">Le funzioni lambda a riga `As` singola non usano una clausola per designare il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="d1203-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="d1203-124">Al contrario, il tipo viene dedotto dal valore che restituisce il corpo dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="d1203-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="d1203-125">Ad esempio, se il corpo `cust.City = "London"`dell'espressione lambda `Boolean`è , il tipo restituito è .</span><span class="sxs-lookup"><span data-stu-id="d1203-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="d1203-126">Nelle funzioni lambda su più righe è possibile specificare un tipo restituito usando una `As` clausola oppure omettere la `As` clausola in modo che il tipo restituito venga dedotto.</span><span class="sxs-lookup"><span data-stu-id="d1203-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="d1203-127">Quando `As` la clausola viene omessa per una funzione lambda su più righe, il `Return` tipo restituito viene dedotto come tipo dominante da tutte le istruzioni nella funzione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="d1203-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="d1203-128">Il *tipo dominante* è un tipo univoco in cui tutti gli altri tipi possono ampliarsi.</span><span class="sxs-lookup"><span data-stu-id="d1203-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="d1203-129">Se non è possibile determinare questo tipo univoco, il tipo dominante è il tipo univoco a cui tutti gli altri tipi nella matrice possono restringersi.</span><span class="sxs-lookup"><span data-stu-id="d1203-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="d1203-130">Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`.</span><span class="sxs-lookup"><span data-stu-id="d1203-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="d1203-131">In questo caso, `Option Strict` se `On`è impostato su , si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d1203-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="d1203-132">Se ad esempio le espressioni `Return` fornite all'istruzione `Integer` `Long`contengono `Double`valori di tipo `Double`, , e , la matrice risultante è di tipo .</span><span class="sxs-lookup"><span data-stu-id="d1203-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="d1203-133">Sia `Integer` `Long` e `Double` ampliare `Double`a e solo .</span><span class="sxs-lookup"><span data-stu-id="d1203-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="d1203-134">`Double` è pertanto il tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="d1203-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="d1203-135">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="d1203-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="d1203-136">Il corpo di una funzione a riga singola deve essere un'espressione che restituisce un valore, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d1203-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="d1203-137">Non esiste `Return` alcuna istruzione per le funzioni a riga singola.</span><span class="sxs-lookup"><span data-stu-id="d1203-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="d1203-138">Il valore restituito dalla funzione a riga singola è il valore dell'espressione nel corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="d1203-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="d1203-139">Il corpo di una subroutine a riga singola deve essere un'istruzione a riga singola.</span><span class="sxs-lookup"><span data-stu-id="d1203-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="d1203-140">Le funzioni e le subroutine a `End Function` `End Sub` riga singola non includono un'istruzione o .</span><span class="sxs-lookup"><span data-stu-id="d1203-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="d1203-141">È possibile specificare il tipo di dati `As` di un parametro dell'espressione lambda usando la parola chiave oppure il tipo di dati del parametro può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="d1203-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="d1203-142">Tutti i parametri devono avere tipi di dati specificati o tutti devono essere dedotti.</span><span class="sxs-lookup"><span data-stu-id="d1203-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="d1203-143">`Optional`e `Paramarray` parametri non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="d1203-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="d1203-144">I parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="d1203-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="d1203-145">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="d1203-145">Async Lambdas</span></span>

<span data-ttu-id="d1203-146">È possibile creare facilmente espressioni lambda e istruzioni che incorporano l'elaborazione asincrona usando le parole chiave Async e [Await Operator.You](../../../../visual-basic/language-reference/operators/await-operator.md) can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and Await Operator keywords.</span><span class="sxs-lookup"><span data-stu-id="d1203-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="d1203-147">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="d1203-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="d1203-148">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona in [un'istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d1203-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="d1203-149">Per aggiungere il gestore, aggiungere un modificatore `Async` prima dell'elenco di parametri lambda, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d1203-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="d1203-150">Per ulteriori informazioni su come creare e utilizzare metodi asincroni, vedere [Programmazione asincrona con Async e Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1203-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="d1203-151">Context</span><span class="sxs-lookup"><span data-stu-id="d1203-151">Context</span></span>

<span data-ttu-id="d1203-152">Un'espressione lambda condivide il contesto con l'ambito all'interno del quale è definita.</span><span class="sxs-lookup"><span data-stu-id="d1203-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="d1203-153">Ha gli stessi diritti di accesso di qualsiasi codice scritto nell'ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="d1203-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="d1203-154">Ciò include l'accesso a variabili `Me`membro, funzioni e sub, e parametri e variabili locali nell'ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="d1203-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="d1203-155">L'accesso alle variabili locali e ai parametri nell'ambito contenitore può estendersi oltre la durata di tale ambito.</span><span class="sxs-lookup"><span data-stu-id="d1203-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="d1203-156">Finché un delegato che fa riferimento a un'espressione lambda non è disponibile per la procedura di Garbage Collection, l'accesso alle variabili nell'ambiente originale viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="d1203-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="d1203-157">Nell'esempio seguente, `target` variabile `makeTheGame`è locale a , `playTheGame` il metodo in cui è definita l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="d1203-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="d1203-158">Si noti che l'espressione `takeAGuess` `Main`lambda restituita, assegnata `target`a in , ha ancora accesso alla variabile locale .</span><span class="sxs-lookup"><span data-stu-id="d1203-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="d1203-159">Nell'esempio seguente viene illustrata l'ampia gamma di diritti di accesso dell'espressione lambda annidata.</span><span class="sxs-lookup"><span data-stu-id="d1203-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="d1203-160">Quando l'espressione lambda restituita `Main` `aDel`viene eseguita da come , accede a questi elementi:</span><span class="sxs-lookup"><span data-stu-id="d1203-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="d1203-161">Campo della classe in cui è definito:`aField`</span><span class="sxs-lookup"><span data-stu-id="d1203-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="d1203-162">Proprietà della classe in cui è definita:`aProp`</span><span class="sxs-lookup"><span data-stu-id="d1203-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="d1203-163">Parametro del `functionWithNestedLambda`metodo , in cui è definito:`level1`</span><span class="sxs-lookup"><span data-stu-id="d1203-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="d1203-164">Una variabile `functionWithNestedLambda`locale di :`localVar`</span><span class="sxs-lookup"><span data-stu-id="d1203-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="d1203-165">Parametro dell'espressione lambda in cui è annidato:`level2`</span><span class="sxs-lookup"><span data-stu-id="d1203-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="d1203-166">Conversione in un tipo delegatoConverting to a Delegate Type</span><span class="sxs-lookup"><span data-stu-id="d1203-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="d1203-167">Un'espressione lambda può essere convertita in modo implicito in un tipo delegato compatibile.</span><span class="sxs-lookup"><span data-stu-id="d1203-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="d1203-168">Per informazioni sui requisiti generali per la compatibilità, vedere [Conversione di delegati Relaxed](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="d1203-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="d1203-169">Ad esempio, nell'esempio di codice seguente viene `Func(Of Integer, Boolean)` illustrata un'espressione lambda che converte in modo implicito o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d1203-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="d1203-170">Nell'esempio di codice seguente viene illustrata `Sub(Of Double, String, Double)` un'espressione lambda che converte in modo implicito o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d1203-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="d1203-171">Quando si assegnano espressioni lambda ai delegati o le si passa come argomenti alle routine, è possibile specificare i nomi dei parametri ma omettere i relativi tipi di dati, consentendo ai tipi di essere ricavati dal delegato.</span><span class="sxs-lookup"><span data-stu-id="d1203-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="d1203-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="d1203-172">Examples</span></span>

- <span data-ttu-id="d1203-173">Nell'esempio seguente viene definita `True` un'espressione lambda che restituisce se `False` all'argomento `Nothing`di tipo valore nullable è assegnato un valore e se il relativo valore è .</span><span class="sxs-lookup"><span data-stu-id="d1203-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="d1203-174">Nell'esempio seguente viene definita un'espressione lambda che restituisce l'indice dell'ultimo elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="d1203-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="d1203-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1203-175">See also</span></span>

- [<span data-ttu-id="d1203-176">Procedure</span><span class="sxs-lookup"><span data-stu-id="d1203-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d1203-177">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1203-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d1203-178">Delegati</span><span class="sxs-lookup"><span data-stu-id="d1203-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="d1203-179">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="d1203-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d1203-180">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="d1203-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d1203-181">Tipi di valore nullableNullable Value Types</span><span class="sxs-lookup"><span data-stu-id="d1203-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d1203-182">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1203-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="d1203-183">Procedura: creare un'espressione lambda</span><span class="sxs-lookup"><span data-stu-id="d1203-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="d1203-184">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="d1203-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
