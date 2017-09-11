---
title: Le espressioni lambda (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e4624e5f20beeebf85656c893043030566200557
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="4e259-102">Espressioni lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e259-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="4e259-103">Oggetto *espressione lambda* è una funzione o subroutine senza nome, che può essere utilizzato ovunque sia valido un delegato.</span><span class="sxs-lookup"><span data-stu-id="4e259-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="4e259-104">Le espressioni lambda possono essere funzioni o subroutine e possono essere a riga singola o multiriga.</span><span class="sxs-lookup"><span data-stu-id="4e259-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="4e259-105">È possibile passare valori dall'ambito corrente in un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4e259-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e259-106">Il `RemoveHandler` istruzione è un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4e259-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="4e259-107">Non è possibile passare un'espressione lambda in per il parametro del delegato `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="4e259-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="4e259-108">Per creare espressioni lambda, utilizzare il `Function` o `Sub` (parola chiave), come se si crea una subroutine o una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="4e259-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="4e259-109">Tuttavia, le espressioni lambda sono inclusi in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="4e259-110">Nell'esempio seguente è un'espressione lambda che incrementa il proprio argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="4e259-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="4e259-111">L'esempio mostra sia la sintassi delle espressioni lambda a riga singola e a più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 <span data-ttu-id="4e259-112">[!code-vb[VbVbalrLambdas&#14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-112">[!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span></span>  
  
 <span data-ttu-id="4e259-113">Nell'esempio seguente è un'espressione lambda che scrive un valore nella console.</span><span class="sxs-lookup"><span data-stu-id="4e259-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="4e259-114">L'esempio mostra sia la sintassi delle espressioni lambda a riga singola e a più righe di una subroutine.</span><span class="sxs-lookup"><span data-stu-id="4e259-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 <span data-ttu-id="4e259-115">[!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-115">[!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span></span>  
  
 <span data-ttu-id="4e259-116">Si noti che, negli esempi precedenti le espressioni lambda vengono assegnate un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="4e259-116">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="4e259-117">Quando si fa riferimento alla variabile, richiamare l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4e259-117">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="4e259-118">È anche possibile dichiarare e richiamare un'espressione lambda nello stesso momento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4e259-118">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 <span data-ttu-id="4e259-119">[!code-vb[VbVbalrLambdas n.&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-119">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span></span>  
  
 <span data-ttu-id="4e259-120">Un'espressione lambda può essere restituita come valore di una chiamata di funzione (come illustrato nell'esempio di [contesto](#context) sezione più avanti in questo argomento), o passato come argomento a un parametro che accetta un tipo delegato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4e259-120">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 <span data-ttu-id="4e259-121">[!code-vb[VbVbalrLambdas n.&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-121">[!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="4e259-122">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="4e259-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="4e259-123">La sintassi di un'espressione lambda è simile a quello di una subroutine o una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="4e259-123">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="4e259-124">Le differenze sono come segue:</span><span class="sxs-lookup"><span data-stu-id="4e259-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="4e259-125">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="4e259-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="4e259-126">Espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="4e259-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="4e259-127">Le funzioni lambda a riga singola non utilizzano un `As` clausola per definire il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="4e259-127">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="4e259-128">Al contrario, il tipo viene dedotto dal valore che restituisce il corpo dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4e259-128">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="4e259-129">Ad esempio, se il corpo dell'espressione lambda è `cust.City = "London"`, il tipo restituito `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4e259-129">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="4e259-130">Nelle funzioni lambda su più righe, è possibile specificare un tipo restituito tramite un `As` clausola, oppure omettere il `As` clausola in modo che il tipo restituito viene dedotto.</span><span class="sxs-lookup"><span data-stu-id="4e259-130">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="4e259-131">Quando il `As` clausola viene omessa per una funzione lambda su più righe, il tipo restituito viene considerato il tipo dominante da tutti i `Return` istruzioni nella funzione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="4e259-131">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="4e259-132">Il *tipo dominante* è un tipo univoco che possono ampliarsi tutti gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="4e259-132">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="4e259-133">Se non è possibile determinare il tipo univoco, il tipo dominante è il tipo univoco possono restringersi tutti gli altri tipi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="4e259-133">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="4e259-134">Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`.</span><span class="sxs-lookup"><span data-stu-id="4e259-134">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="4e259-135">In questo caso, se `Option Strict` è impostato su `On`, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4e259-135">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="4e259-136">Ad esempio, se le espressioni fornite per la `Return` istruzione contengono valori di tipo `Integer`, `Long`, e `Double`, la matrice risultante è di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="4e259-136">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="4e259-137">Entrambi `Integer` e `Long` ampliarsi `Double` e solo `Double`.</span><span class="sxs-lookup"><span data-stu-id="4e259-137">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="4e259-138">`Double` è pertanto il tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="4e259-138">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="4e259-139">Per ulteriori informazioni, vedere [conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="4e259-139">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="4e259-140">Il corpo di una funzione a riga singola deve essere un'espressione che restituisce un valore, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-140">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="4e259-141">Non esiste alcun `Return` istruzione per le funzioni a riga singola.</span><span class="sxs-lookup"><span data-stu-id="4e259-141">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="4e259-142">Il valore restituito dalla funzione a riga singola è il valore dell'espressione nel corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-142">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="4e259-143">Il corpo di una subroutine a riga singola deve essere a riga singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-143">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="4e259-144">Funzioni a riga singola e le subroutine non includono un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e259-144">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="4e259-145">È possibile specificare il tipo di dati di un parametro di espressione lambda con il `As` parola chiave o il tipo di dati del parametro può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="4e259-145">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="4e259-146">Tutti i parametri devono avere specificato deve essere dedotto, tipi di dati o tutti.</span><span class="sxs-lookup"><span data-stu-id="4e259-146">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="4e259-147">`Optional`e `Paramarray` i parametri non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4e259-147">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="4e259-148">Parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4e259-148">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="4e259-149">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="4e259-149">Async Lambdas</span></span>  
 <span data-ttu-id="4e259-150">È possibile creare con facilità le espressioni lambda e le istruzioni che includono l'elaborazione asincrona utilizzando il [Async](../../../../visual-basic/language-reference/modifiers/async.md) e [operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md) parole chiave.</span><span class="sxs-lookup"><span data-stu-id="4e259-150">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="4e259-151">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="4e259-151">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="4e259-152">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona in un [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4e259-152">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4e259-153">Per aggiungere il gestore, aggiungere un modificatore `Async` prima dell'elenco di parametri lambda, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4e259-153">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="4e259-154">Per ulteriori informazioni su come creare e utilizzare i metodi asincroni, vedere [la programmazione asincrona con Async e Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="4e259-154">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="4e259-155"><a name="context"></a>Contesto</span><span class="sxs-lookup"><span data-stu-id="4e259-155"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="4e259-156">Un'espressione lambda condivide il contesto con l'ambito entro il quale è definito.</span><span class="sxs-lookup"><span data-stu-id="4e259-156">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="4e259-157">Include gli stessi diritti di accesso di qualsiasi codice scritto nell'ambito che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4e259-157">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="4e259-158">Ciò include l'accesso a variabili membro, funzioni e subroutine, `Me`e i parametri e variabili locali all'interno dell'ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="4e259-158">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="4e259-159">Accesso alle variabili locali e i parametri nell'ambito che lo contiene può estendersi oltre la durata di tale ambito.</span><span class="sxs-lookup"><span data-stu-id="4e259-159">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="4e259-160">Come un delegato che fa riferimento a un'espressione lambda non è disponibile a garbage collection, l'accesso alle variabili nell'ambiente originale viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="4e259-160">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="4e259-161">Nell'esempio seguente, variabile `target` locale `makeTheGame`, il metodo in cui l'espressione lambda `playTheGame` è definito.</span><span class="sxs-lookup"><span data-stu-id="4e259-161">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="4e259-162">Si noti che l'espressione lambda restituita, assegnata a `takeAGuess` in `Main`, può ancora accedere alla variabile locale `target`.</span><span class="sxs-lookup"><span data-stu-id="4e259-162">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 <span data-ttu-id="4e259-163">[!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-163">[!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span></span>  
  
 <span data-ttu-id="4e259-164">Nell'esempio seguente viene illustrato l'ampia gamma di diritti di accesso dell'espressione lambda annidata.</span><span class="sxs-lookup"><span data-stu-id="4e259-164">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="4e259-165">Quando viene eseguita l'espressione lambda restituita da `Main` come `aDel`, accede a questi elementi:</span><span class="sxs-lookup"><span data-stu-id="4e259-165">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="4e259-166">Un campo della classe in cui è definito:`aField`</span><span class="sxs-lookup"><span data-stu-id="4e259-166">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="4e259-167">Una proprietà della classe in cui è definito:`aProp`</span><span class="sxs-lookup"><span data-stu-id="4e259-167">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="4e259-168">Un parametro di metodo `functionWithNestedLambda`, in cui è definito:`level1`</span><span class="sxs-lookup"><span data-stu-id="4e259-168">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="4e259-169">Una variabile locale di `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="4e259-169">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="4e259-170">Un parametro dell'espressione lambda in cui è annidato:`level2`</span><span class="sxs-lookup"><span data-stu-id="4e259-170">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 <span data-ttu-id="4e259-171">[!code-vb[9 VbVbalrLambdas](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-171">[!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span></span>  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="4e259-172">La conversione in un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="4e259-172">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="4e259-173">Un'espressione lambda può essere convertita in modo implicito in un tipo delegato compatibile.</span><span class="sxs-lookup"><span data-stu-id="4e259-173">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="4e259-174">Per informazioni sui requisiti generali per la compatibilità, vedere [conversione di tipo Relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="4e259-174">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="4e259-175">Ad esempio, il codice seguente viene illustrata un'espressione lambda che converte in modo implicito in `Func(Of Integer, Boolean)` o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4e259-175">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="4e259-176">[!code-vb[VbVbalrLambdas&#16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-176">[!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span></span>  
  
 <span data-ttu-id="4e259-177">Esempio di codice seguente viene illustrata un'espressione lambda che converte in modo implicito in `Sub(Of Double, String, Double)` o una firma del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4e259-177">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="4e259-178">[!code-vb[VbVbalrLambdas&#23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-178">[!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span></span>  
  
 <span data-ttu-id="4e259-179">Quando si assegnano espressioni lambda ai delegati o passati come argomenti alle procedure, è possibile specificare i nomi di parametro ma omettere i tipi di dati, consentire i tipi di essere eseguite dal delegato.</span><span class="sxs-lookup"><span data-stu-id="4e259-179">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4e259-180">Esempi</span><span class="sxs-lookup"><span data-stu-id="4e259-180">Examples</span></span>  
  
-   <span data-ttu-id="4e259-181">Nell'esempio seguente viene definita un'espressione lambda che restituisce `True` se l'argomento nullable ha un valore assegnato e `False` se il valore è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4e259-181">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     <span data-ttu-id="4e259-182">[!code-vb[VbVbalrLambdas n.&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-182">[!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span></span>  
  
-   <span data-ttu-id="4e259-183">Nell'esempio seguente viene definita un'espressione lambda che restituisce l'indice dell'ultimo elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="4e259-183">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     <span data-ttu-id="4e259-184">[!code-vb[VbVbalrLambdas n.&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e259-184">[!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e259-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e259-185">See Also</span></span>  
 <span data-ttu-id="4e259-186">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-186">[Procedures](./index.md) </span></span>  
<span data-ttu-id="4e259-187"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-187"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="4e259-188"> [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-188"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="4e259-189"> [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-189"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="4e259-190"> [Sub (istruzione)](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-190"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="4e259-191"> [Tipi di valore nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-191"> [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="4e259-192"> [Procedura: passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-192"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="4e259-193"> [Procedura: creare un'espressione Lambda](./how-to-create-a-lambda-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4e259-193"> [How to: Create a Lambda Expression](./how-to-create-a-lambda-expression.md) </span></span>  
<span data-ttu-id="4e259-194"> [Conversione di tipo relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="4e259-194"> [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

