---
title: Espressioni lambda - Guida per programmatori C#
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: c549b9fcc91401aed846afd39e656b60e16afb74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937597"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="12494-102">Espressioni lambda (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="12494-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="12494-103">Un'*espressione lambda* è un'espressione in uno dei due formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="12494-103">A *lambda expression* is an expression of any of the following two forms:</span></span>

- <span data-ttu-id="12494-104">[Espressione lambda con espressione](#expression-lambdas), che contiene un'espressione come corpo:</span><span class="sxs-lookup"><span data-stu-id="12494-104">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="12494-105">[Espressione lambda con istruzioni](#statement-lambdas), che contiene un blocco di istruzioni come corpo:</span><span class="sxs-lookup"><span data-stu-id="12494-105">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="12494-106">Usare l'[operatore di dichiarazione lambda `=>`](../../language-reference/operators/lambda-operator.md) per separare l'elenco di parametri dell'espressione lambda dal corpo.</span><span class="sxs-lookup"><span data-stu-id="12494-106">Use the [lambda declaration operator `=>`](../../language-reference/operators/lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="12494-107">Per creare un'espressione lambda, è necessario specificare gli eventuali parametri di input a sinistra dell'operatore lambda e un'espressione o un blocco di istruzioni sull'altro lato.</span><span class="sxs-lookup"><span data-stu-id="12494-107">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="12494-108">Qualsiasi espressione lambda può essere convertita in tipo [delegato](../../language-reference/builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="12494-108">Any lambda expression can be converted to a [delegate](../../language-reference/builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="12494-109">Il tipo delegato in cui è possibile convertire un'espressione lambda è definito dai tipi dei relativi parametri e del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="12494-109">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="12494-110">Se un'espressione lambda non restituisce alcun valore, può essere convertita in uno dei tipi delegati `Action`, altrimenti può essere convertita in uno dei tipi delegati `Func`.</span><span class="sxs-lookup"><span data-stu-id="12494-110">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="12494-111">Ad esempio, un'espressione lambda che include due parametri e non restituisce alcun valore può essere convertita in delegato <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="12494-111">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="12494-112">Un'espressione lambda che include un parametro e restituisce un valore può essere convertita in delegato <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="12494-112">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="12494-113">Nell'esempio seguente l'espressione lambda `x => x * x`, che specifica un parametro denominato `x` e restituisce il valore `x` al quadrato, viene assegnata a una variabile di un tipo delegato:</span><span class="sxs-lookup"><span data-stu-id="12494-113">In the following example, the lambda expression `x => x * x`, which specifies a parameter that’s named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="12494-114">Un'espressione lambda può essere convertita anche in tipo [albero delle espressioni](../concepts/expression-trees/index.md), come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="12494-114">Expression lambdas also can be converted to the [expression tree](../concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="12494-115">È possibile usare espressioni lambda in qualsiasi codice che richiede istanze di tipi delegati o alberi delle espressioni, ad esempio come argomento per il metodo <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> per passare il codice da eseguire in background.</span><span class="sxs-lookup"><span data-stu-id="12494-115">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="12494-116">È anche possibile usare le espressioni lambda quando si scrive [LINQ in C](../../linq/index.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="12494-116">You also can use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="12494-117">Quando si usa la sintassi basata su metodo per chiamare il metodo <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> nella classe <xref:System.Linq.Enumerable?displayProperty=nameWithType>, ad esempio in LINQ to Objects e LINQ to XML, il parametro è un tipo delegato <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12494-117">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="12494-118">Quando si <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> chiama il <xref:System.Linq.Queryable?displayProperty=nameWithType> metodo nella classe , ad esempio in LINQ [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>)to SQLLINQ to SQL, il tipo di parametro è un tipo di struttura ad albero dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="12494-118">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="12494-119">In entrambi i casi è possibile usare la stessa espressione lambda per specificare il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="12494-119">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="12494-120">Questo approccio fa sì che le due chiamate `Select` risultino simili anche se in realtà il tipo degli oggetti creati dalle espressioni lambda è diverso.</span><span class="sxs-lookup"><span data-stu-id="12494-120">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="12494-121">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="12494-121">Expression lambdas</span></span>

<span data-ttu-id="12494-122">Un'espressione lambda con un'espressione a destra dell'operatore `=>` è denominata *espressione lambda*.</span><span class="sxs-lookup"><span data-stu-id="12494-122">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="12494-123">Le espressioni lambda [dell'espressione](../concepts/expression-trees/index.md)vengono ampiamente utilizzate nella costruzione di alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="12494-123">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="12494-124">Un'espressione lambda dell'espressione restituisce il risultato dell'espressione e ha il formato di base seguente:</span><span class="sxs-lookup"><span data-stu-id="12494-124">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="12494-125">Le parentesi sono facoltative solo se l'espressione lambda ha un parametro di input; in caso contrario sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="12494-125">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="12494-126">Specificare zero parametri di input con parentesi vuote:</span><span class="sxs-lookup"><span data-stu-id="12494-126">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="12494-127">Due o più parametri di input vengono separati da virgole e racchiusi tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="12494-127">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="12494-128">Talvolta è impossibile che il compilatore deduca i tipi di input.</span><span class="sxs-lookup"><span data-stu-id="12494-128">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="12494-129">È possibile specificare i tipi in modo esplicito come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="12494-129">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="12494-130">I parametri di input devono essere tutti di tipo esplicito o tutti di tipo implicito. In caso contrario, si verifica un errore del compilatore [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="12494-130">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="12494-131">Il corpo di un'espressione lambda può essere costituito da una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="12494-131">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="12494-132">Se tuttavia si creano alberi delle espressioni valutati al di fuori del contesto di Common Language Runtime di .NET Framework, ad esempio in SQL Server, non è consigliabile usare chiamate al metodo nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-132">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="12494-133">I metodi non avranno alcun significato all'esterno del contesto di .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="12494-133">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="12494-134">Espressioni lambda dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="12494-134">Statement lambdas</span></span>

<span data-ttu-id="12494-135">Un'espressione lambda dell'istruzione è simile a un'espressione lambda dell'espressione con la differenza che l'istruzione o le istruzioni sono racchiuse tra parentesi graffe:</span><span class="sxs-lookup"><span data-stu-id="12494-135">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="12494-136">Il corpo di un'espressione lambda dell'istruzione può essere costituito da un numero qualsiasi di istruzioni, sebbene in pratica generalmente non ce ne siano più di due o tre.</span><span class="sxs-lookup"><span data-stu-id="12494-136">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="12494-137">Non è possibile usare le espressioni lambda dell'istruzione per creare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="12494-137">Statement lambdas cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="12494-138">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="12494-138">Async lambdas</span></span>

<span data-ttu-id="12494-139">È facile creare istruzioni ed espressioni lambda che includono l'elaborazione asincrona utilizzando le parole chiave [async](../../language-reference/keywords/async.md) e [await](../../language-reference/operators/await.md) .</span><span class="sxs-lookup"><span data-stu-id="12494-139">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/operators/await.md) keywords.</span></span> <span data-ttu-id="12494-140">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="12494-140">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="12494-141">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona.</span><span class="sxs-lookup"><span data-stu-id="12494-141">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="12494-142">Per aggiungere il gestore, aggiungere un modificatore `async` prima dell'elenco di parametri lambda, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="12494-142">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="12494-143">Per ulteriori informazioni su come creare e utilizzare metodi asincroni, vedere [Programmazione asincrona con async e await](../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="12494-143">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="12494-144">Espressioni lambda e tuple</span><span class="sxs-lookup"><span data-stu-id="12494-144">Lambda expressions and tuples</span></span>

<span data-ttu-id="12494-145">A partire dalla versione 7.0 di C, il linguaggio C'è dotato di supporto incorporato per [le tuple.](../../tuples.md)</span><span class="sxs-lookup"><span data-stu-id="12494-145">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="12494-146">È possibile specificare una tupla come argomento di un'espressione lambda e l'espressione lambda può restituire una tupla.</span><span class="sxs-lookup"><span data-stu-id="12494-146">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="12494-147">In alcuni casi, il compilatore C# usa l'inferenza del tipo per determinare i tipi di componenti della tupla.</span><span class="sxs-lookup"><span data-stu-id="12494-147">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="12494-148">Per definire una tupla, è necessario racchiudere tra parentesi un elenco di componenti delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="12494-148">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="12494-149">L'esempio riportato sotto usa una tupla con tre componenti per passare una sequenza di numeri a un'espressione lambda, la quale raddoppia ogni valore e restituisce una tupla con tre componenti che contiene il risultato delle moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="12494-149">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="12494-150">In genere, i campi di `Item1` `Item2`una tupla sono denominati , e così via. È tuttavia possibile definire una tupla con componenti denominati, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="12494-150">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="12494-151">Per altre informazioni sulle tuple in C#, vedere [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="12494-151">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="12494-152">Espressioni lambda con operatori query standard</span><span class="sxs-lookup"><span data-stu-id="12494-152">Lambdas with the standard query operators</span></span>

<span data-ttu-id="12494-153">LINQ to Objects, tra altre implementazioni, ha un parametro di input il cui tipo appartiene alla famiglia <xref:System.Func%601> di delegati generici.</span><span class="sxs-lookup"><span data-stu-id="12494-153">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="12494-154">Questi delegati usano parametri di tipo per definire il numero e il tipo di parametri di input e il tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="12494-154">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="12494-155">I delegati`Func` sono molto utili per incapsulare le espressioni definite dall'utente applicate a ogni elemento in un set di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="12494-155">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="12494-156">Considerare ad esempio il tipo delegato <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="12494-156">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="12494-157">È possibile creare un'istanza `Func<int, bool>` del delegato, dove `int` è un parametro di input e `bool` è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="12494-157">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="12494-158">Il valore restituito è sempre specificato nell'ultimo parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="12494-158">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="12494-159">`Func<int, string, bool>`, ad esempio, definisce un delegato con due parametri di input, `int` e `string`, e un tipo restituito `bool`.</span><span class="sxs-lookup"><span data-stu-id="12494-159">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="12494-160">Quando viene richiamato, il delegato `Func` seguente restituisce il valore booleano indicante se il parametro di input è uguale a cinque:</span><span class="sxs-lookup"><span data-stu-id="12494-160">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="12494-161">È anche possibile specificare un'espressione lambda quando il tipo di argomento è <xref:System.Linq.Expressions.Expression%601>, ad esempio negli operatori query standard definiti nel tipo <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="12494-161">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="12494-162">Quando si specifica un argomento <xref:System.Linq.Expressions.Expression%601>, l'espressione lambda viene compilata per un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="12494-162">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="12494-163">L'esempio seguente usa l'operatore query standard <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="12494-163">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="12494-164">Il compilatore è in grado di dedurre il tipo del parametro di input oppure è possibile specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12494-164">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="12494-165">Questa espressione lambda particolare conta i numeri interi (`n`) che divisi per due danno il resto di 1.</span><span class="sxs-lookup"><span data-stu-id="12494-165">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="12494-166">L'esempio seguente crea una sequenza contenente tutti gli elementi presenti nella matrice `numbers` che si trovano a sinistra di 9, vale a dire il primo numero della sequenza che non soddisfa la condizione:</span><span class="sxs-lookup"><span data-stu-id="12494-166">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="12494-167">In questo esempio viene illustrato come specificare più parametri di input racchiudendoli tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="12494-167">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="12494-168">Il metodo restituisce tutti gli elementi presenti nella matrice `numbers` finché non viene rilevato un numero il cui valore è inferiore alla relativa posizione all'interno della matrice:</span><span class="sxs-lookup"><span data-stu-id="12494-168">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="12494-169">Inferenza del tipo nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="12494-169">Type inference in lambda expressions</span></span>

<span data-ttu-id="12494-170">Quando si scrivono espressioni lambda, spesso non occorre specificare un tipo per i parametri di input, perché il compilatore può dedurlo in base al corpo dell'espressione lambda, ai tipi di parametro e ad altri fattori, come descritto nelle specifiche del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="12494-170">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="12494-171">Per la maggior parte degli operatori di query standard, il primo input è il tipo degli elementi nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="12494-171">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="12494-172">Pertanto, se si esegue una query su un oggetto `IEnumerable<Customer>`, si deduce che la variabile di input sia un oggetto `Customer`, ovvero che si dispone dell'accesso ai relativi metodi e proprietà:</span><span class="sxs-lookup"><span data-stu-id="12494-172">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="12494-173">Di seguito sono riportate le regole generali per l'inferenza del tipo nelle espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="12494-173">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="12494-174">L'espressione lambda deve contenere lo stesso numero di parametri del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="12494-174">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="12494-175">Ogni parametro di input nell'espressione lambda deve essere convertibile in modo implicito nel parametro del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="12494-175">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="12494-176">Il valore restituito dell'espressione lambda, se presente, deve essere convertibile in modo implicito nel tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="12494-176">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="12494-177">Si noti che le espressioni lambda non hanno un tipo perché Common Type System non ha alcun concetto intrinseco di "espressione lambda".</span><span class="sxs-lookup"><span data-stu-id="12494-177">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="12494-178">In alcuni casi, tuttavia, può essere utile fare riferimento in modo informale al "tipo" di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-178">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="12494-179">In questi casi, per tipo si intende il tipo delegato o il tipo <xref:System.Linq.Expressions.Expression> in cui viene convertita l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-179">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="12494-180">Acquisire variabili esterne e ambito delle variabili nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="12494-180">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="12494-181">Le espressioni lambda possono fare riferimento a *variabili esterne*.</span><span class="sxs-lookup"><span data-stu-id="12494-181">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="12494-182">Si tratta delle variabili incluse nell'ambito del metodo che definisce l'espressione lambda oppure nell'ambito del tipo che contiene l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-182">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="12494-183">Le variabili acquisite in questo modo vengono archiviate per poter essere utilizzate nell'espressione lambda anche se le variabili diventano esterne all'ambito e vengono sottoposte a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="12494-183">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="12494-184">Una variabile esterna deve essere assegnata prima di poter essere utilizzata in un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-184">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="12494-185">Nell'esempio seguente vengono illustrate queste regole:</span><span class="sxs-lookup"><span data-stu-id="12494-185">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="12494-186">Le regole seguenti si applicano all'ambito delle variabili nelle espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="12494-186">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="12494-187">Una variabile acquisita non sarà sottoposta a Garbage Collection finché il delegato a cui fa riferimento non diventa idoneo per il Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="12494-187">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="12494-188">Le variabili introdotte in un'espressione lambda non sono visibili nel metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="12494-188">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="12494-189">Un'espressione lambda non può acquisire direttamente un parametro [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md) dal metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="12494-189">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="12494-190">Un'istruzione [return](../../language-reference/keywords/return.md) in un'espressione lambda non causa la restituzione del metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="12494-190">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="12494-191">Un'espressione lambda non può contenere un'istruzione [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) o [continue](../../language-reference/keywords/continue.md) se la destinazione di tale istruzione di salto è esterna al blocco dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="12494-191">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="12494-192">È anche errato inserire all'esterno del blocco dell'espressione lambda un'istruzione di salto se la destinazione è interna al blocco.</span><span class="sxs-lookup"><span data-stu-id="12494-192">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12494-193">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="12494-193">C# language specification</span></span>

<span data-ttu-id="12494-194">Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="12494-194">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="12494-195">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="12494-195">Featured book chapter</span></span>

<span data-ttu-id="12494-196">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="12494-196">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12494-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12494-197">See also</span></span>

- [<span data-ttu-id="12494-198">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="12494-198">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="12494-199">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="12494-199">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="12494-200">Alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="12494-200">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="12494-201">Funzioni locali rispetto alle espressioni lambdaLocal functions compared to lambda expressions</span><span class="sxs-lookup"><span data-stu-id="12494-201">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="12494-202">Espressioni lambda tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="12494-202">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="12494-203">Esempi C# di Visual Studio 2008 (vedere i file di query di esempio LINQ e il programma XQuery)</span><span class="sxs-lookup"><span data-stu-id="12494-203">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="12494-204">Recursive lambda expressions (Espressioni lambda ricorsive)</span><span class="sxs-lookup"><span data-stu-id="12494-204">Recursive lambda expressions</span></span>](https://docs.microsoft.com/archive/blogs/madst/recursive-lambda-expressions)
