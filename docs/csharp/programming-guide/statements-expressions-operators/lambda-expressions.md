---
title: Espressioni lambda - Guida per programmatori C#
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125733"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="808e2-102">Espressioni lambda (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="808e2-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="808e2-103">Un'*espressione lambda* è un blocco di codice costituito da espressioni o da istruzioni che viene trattato come oggetto.</span><span class="sxs-lookup"><span data-stu-id="808e2-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="808e2-104">Tale blocco può essere passato come argomento ai metodi e può anche essere restituito dalle chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="808e2-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="808e2-105">Le espressioni lambda sono spesso usate per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="808e2-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="808e2-106">Passaggio del codice da eseguire a metodi asincroni, ad esempio <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="808e2-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="808e2-107">Scrittura di [espressioni di query LINQ](../../linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="808e2-108">Creazione di [alberi delle espressioni](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="808e2-109">Le espressioni lambda sono codice che può essere rappresentato come delegato o come albero delle espressioni che viene compilato in un delegato.</span><span class="sxs-lookup"><span data-stu-id="808e2-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="808e2-110">Il tipo di delegato specifico di un'espressione lambda dipende dai parametri dell'espressione e dal valore restituito.</span><span class="sxs-lookup"><span data-stu-id="808e2-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="808e2-111">Le espressioni lambda che non restituiscono un valore corrispondano a un delegato `Action` specifico, che dipende dal relativo numero di parametri.</span><span class="sxs-lookup"><span data-stu-id="808e2-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="808e2-112">Le espressioni lambda che restituiscono un valore corrispondano a un delegato `Func` specifico, che dipende dal relativo numero di parametri.</span><span class="sxs-lookup"><span data-stu-id="808e2-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="808e2-113">Se ad esempio un'espressione lambda con due parametri non restituisce un valore, corrisponde a un delegato <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="808e2-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="808e2-114">Se un'espressione lambda ha un parametro e restituisce un valore, corrisponde a un delegato <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="808e2-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="808e2-115">Un'espressione lambda usa `=>`, vale a dire l'[operatore di dichiarazione lambda](../../language-reference/operators/lambda-operator.md), per separare l'elenco di parametri dell'espressione lambda dal codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="808e2-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="808e2-116">Per creare un'espressione lambda, specificare gli eventuali parametri di input a sinistra dell'operatore lambda e inserire il blocco di espressioni o di istruzioni dall'altra parte.</span><span class="sxs-lookup"><span data-stu-id="808e2-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="808e2-117">Ad esempio, l'espressione lambda `x => x * x` a riga singola specifica un parametro denominato `x` e restituisce il valore di `x` al quadrato.</span><span class="sxs-lookup"><span data-stu-id="808e2-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="808e2-118">È possibile assegnare questa espressione a un tipo di delegato, come illustrato nell'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="808e2-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="808e2-119">È anche possibile assegnare un'espressione lambda a un tipo di albero delle espressioni:</span><span class="sxs-lookup"><span data-stu-id="808e2-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="808e2-120">Oppure è possibile passarla direttamente come argomento del metodo:</span><span class="sxs-lookup"><span data-stu-id="808e2-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="808e2-121">Quando si usa la sintassi basata sul metodo per chiamare il metodo <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> nella classe <xref:System.Linq.Enumerable?displayProperty=nameWithType>, come in LINQ to Objects e LINQ to XML, il parametro è un tipo delegato <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="808e2-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="808e2-122">Un'espressione lambda è il modo più pratico per creare tale delegato.</span><span class="sxs-lookup"><span data-stu-id="808e2-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="808e2-123">Quando si chiama il metodo <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> nella classe <xref:System.Linq.Queryable?displayProperty=nameWithType>, come in LINQ to SQL, il tipo di parametro è un tipo di albero delle espressioni [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="808e2-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="808e2-124">Un'espressione lambda rappresenta quindi un modo rapido per costruire tale albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="808e2-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="808e2-125">Mediante le espressioni lambda, le chiamate `Select` risultano simili anche se in realtà il tipo di oggetto creato dall'espressione lambda è diverso.</span><span class="sxs-lookup"><span data-stu-id="808e2-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="808e2-126">Tutte le restrizioni che si applicano ai [metodi anonimi](anonymous-methods.md) si applicano anche alle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="808e2-127">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="808e2-127">Expression lambdas</span></span>

<span data-ttu-id="808e2-128">Un'espressione lambda con un'espressione a destra dell'operatore `=>` è denominata *espressione lambda*.</span><span class="sxs-lookup"><span data-stu-id="808e2-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="808e2-129">Queste espressioni vengono usate spesso nella costruzione di [alberi delle espressioni](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="808e2-130">Un'espressione lambda dell'espressione restituisce il risultato dell'espressione e ha il formato di base seguente:</span><span class="sxs-lookup"><span data-stu-id="808e2-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="808e2-131">Le parentesi sono facoltative solo se l'espressione lambda ha un parametro di input; in caso contrario sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="808e2-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="808e2-132">Specificare zero parametri di input con parentesi vuote:</span><span class="sxs-lookup"><span data-stu-id="808e2-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="808e2-133">Due o più parametri di input vengono separati da virgole e racchiusi tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="808e2-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="808e2-134">Talvolta è impossibile che il compilatore deduca i tipi di input.</span><span class="sxs-lookup"><span data-stu-id="808e2-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="808e2-135">È possibile specificare i tipi in modo esplicito come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="808e2-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="808e2-136">I parametri di input devono essere tutti di tipo esplicito o tutti di tipo implicito. In caso contrario, si verifica un errore del compilatore [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="808e2-137">Il corpo di un'espressione lambda può essere costituito da una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="808e2-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="808e2-138">Se tuttavia si creano alberi delle espressioni valutati al di fuori del contesto di Common Language Runtime di .NET Framework, ad esempio in SQL Server, non è consigliabile usare chiamate al metodo nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="808e2-139">I metodi non avranno alcun significato all'esterno del contesto di .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="808e2-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="808e2-140">Espressioni lambda dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="808e2-140">Statement lambdas</span></span>

<span data-ttu-id="808e2-141">Un'espressione lambda dell'istruzione è simile a un'espressione lambda dell'espressione con la differenza che l'istruzione o le istruzioni sono racchiuse tra parentesi graffe:</span><span class="sxs-lookup"><span data-stu-id="808e2-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="808e2-142">Il corpo di un'espressione lambda dell'istruzione può essere costituito da un numero qualsiasi di istruzioni, sebbene in pratica generalmente non ce ne siano più di due o tre.</span><span class="sxs-lookup"><span data-stu-id="808e2-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="808e2-143">Le espressioni lambda dell'istruzione, come i metodi anonimi, non possono essere utilizzate per creare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="808e2-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="808e2-144">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="808e2-144">Async lambdas</span></span>

<span data-ttu-id="808e2-145">È facile creare istruzioni ed espressioni lambda che includono l'elaborazione asincrona utilizzando le parole chiave [async](../../language-reference/keywords/async.md) e [await](../../language-reference/keywords/await.md) .</span><span class="sxs-lookup"><span data-stu-id="808e2-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="808e2-146">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="808e2-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="808e2-147">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona.</span><span class="sxs-lookup"><span data-stu-id="808e2-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="808e2-148">Per aggiungere il gestore, aggiungere un modificatore `async` prima dell'elenco di parametri lambda, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="808e2-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

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

<span data-ttu-id="808e2-149">Per altre informazioni su come creare e usare i metodi asincroni, vedere [Programmazione asincrona con async e await](../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="808e2-150">Espressioni lambda e tuple</span><span class="sxs-lookup"><span data-stu-id="808e2-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="808e2-151">A partire da C# 7.0, il linguaggio C# offre supporto predefinito per le [tuple](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="808e2-152">È possibile specificare una tupla come argomento di un'espressione lambda e l'espressione lambda può restituire una tupla.</span><span class="sxs-lookup"><span data-stu-id="808e2-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="808e2-153">In alcuni casi, il compilatore C# usa l'inferenza del tipo per determinare i tipi di componenti della tupla.</span><span class="sxs-lookup"><span data-stu-id="808e2-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="808e2-154">Per definire una tupla, è necessario racchiudere tra parentesi un elenco di componenti delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="808e2-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="808e2-155">L'esempio riportato sotto usa una tupla con tre componenti per passare una sequenza di numeri a un'espressione lambda, la quale raddoppia ogni valore e restituisce una tupla con tre componenti che contiene il risultato delle moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="808e2-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="808e2-156">In genere, i campi di una tupla sono denominati `Item1`, `Item2` e così via. È possibile tuttavia definire una tupla usando i componenti denominati, come illustra l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="808e2-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="808e2-157">Per altre informazioni sulle tuple in C#, vedere [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="808e2-158">Espressioni lambda con operatori query standard</span><span class="sxs-lookup"><span data-stu-id="808e2-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="808e2-159">LINQ to Objects, tra altre implementazioni, ha un parametro di input il cui tipo appartiene alla famiglia <xref:System.Func%601> di delegati generici.</span><span class="sxs-lookup"><span data-stu-id="808e2-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="808e2-160">Questi delegati usano parametri di tipo per definire il numero e il tipo di parametri di input e il tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="808e2-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="808e2-161">I delegati`Func` sono molto utili per incapsulare le espressioni definite dall'utente applicate a ogni elemento in un set di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="808e2-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="808e2-162">Considerare ad esempio il tipo delegato <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="808e2-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="808e2-163">È possibile creare un'istanza `Func<int, bool>` del delegato, dove `int` è un parametro di input e `bool` è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="808e2-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="808e2-164">Il valore restituito è sempre specificato nell'ultimo parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="808e2-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="808e2-165">`Func<int, string, bool>`, ad esempio, definisce un delegato con due parametri di input, `int` e `string`, e un tipo restituito `bool`.</span><span class="sxs-lookup"><span data-stu-id="808e2-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="808e2-166">Quando viene richiamato, il delegato `Func` seguente restituisce il valore booleano indicante se il parametro di input è uguale a cinque:</span><span class="sxs-lookup"><span data-stu-id="808e2-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="808e2-167">È anche possibile specificare un'espressione lambda quando il tipo di argomento è <xref:System.Linq.Expressions.Expression%601>, ad esempio negli operatori query standard definiti nel tipo <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="808e2-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="808e2-168">Quando si specifica un argomento <xref:System.Linq.Expressions.Expression%601>, l'espressione lambda viene compilata per un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="808e2-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="808e2-169">L'esempio seguente usa l'operatore query standard <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="808e2-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="808e2-170">Il compilatore è in grado di dedurre il tipo del parametro di input oppure è possibile specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="808e2-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="808e2-171">Questa espressione lambda particolare conta i numeri interi (`n`) che divisi per due danno il resto di 1.</span><span class="sxs-lookup"><span data-stu-id="808e2-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="808e2-172">L'esempio seguente crea una sequenza contenente tutti gli elementi presenti nella matrice `numbers` che si trovano a sinistra di 9, vale a dire il primo numero della sequenza che non soddisfa la condizione:</span><span class="sxs-lookup"><span data-stu-id="808e2-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="808e2-173">In questo esempio viene illustrato come specificare più parametri di input racchiudendoli tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="808e2-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="808e2-174">Il metodo restituisce tutti gli elementi presenti nella matrice `numbers` finché non viene rilevato un numero il cui valore è inferiore alla relativa posizione all'interno della matrice:</span><span class="sxs-lookup"><span data-stu-id="808e2-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="808e2-175">Inferenza del tipo nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="808e2-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="808e2-176">Quando si scrivono espressioni lambda, spesso non occorre specificare un tipo per i parametri di input, perché il compilatore può dedurlo in base al corpo dell'espressione lambda, ai tipi di parametro e ad altri fattori, come descritto nelle specifiche del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="808e2-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="808e2-177">Per la maggior parte degli operatori di query standard, il primo input è il tipo degli elementi nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="808e2-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="808e2-178">Pertanto, se si esegue una query su un oggetto `IEnumerable<Customer>`, si deduce che la variabile di input sia un oggetto `Customer`, ovvero che si dispone dell'accesso ai relativi metodi e proprietà:</span><span class="sxs-lookup"><span data-stu-id="808e2-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="808e2-179">Di seguito sono riportate le regole generali per l'inferenza del tipo nelle espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="808e2-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="808e2-180">L'espressione lambda deve contenere lo stesso numero di parametri del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="808e2-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="808e2-181">Ogni parametro di input nell'espressione lambda deve essere convertibile in modo implicito nel parametro del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="808e2-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="808e2-182">Il valore restituito dell'espressione lambda, se presente, deve essere convertibile in modo implicito nel tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="808e2-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="808e2-183">Si noti che le espressioni lambda non hanno un tipo perché Common Type System non ha alcun concetto intrinseco di "espressione lambda".</span><span class="sxs-lookup"><span data-stu-id="808e2-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="808e2-184">In alcuni casi, tuttavia, può essere utile fare riferimento in modo informale al "tipo" di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="808e2-185">In questi casi, per tipo si intende il tipo delegato o il tipo <xref:System.Linq.Expressions.Expression> in cui viene convertita l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="808e2-186">Ambito delle variabili nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="808e2-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="808e2-187">Le espressioni lambda possono fare riferimento alle *variabili esterne* (vedere [Metodi anonimi](anonymous-methods.md)) presenti nell'ambito del metodo che definisce l'espressione lambda oppure nell'ambito del tipo che contiene l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="808e2-188">Le variabili acquisite in questo modo vengono archiviate per poter essere utilizzate nell'espressione lambda anche se le variabili diventano esterne all'ambito e vengono sottoposte a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="808e2-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="808e2-189">Una variabile esterna deve essere assegnata prima di poter essere utilizzata in un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="808e2-190">Nell'esempio seguente vengono illustrate queste regole:</span><span class="sxs-lookup"><span data-stu-id="808e2-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="808e2-191">Le regole seguenti si applicano all'ambito delle variabili nelle espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="808e2-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="808e2-192">Una variabile acquisita non sarà sottoposta a Garbage Collection finché il delegato a cui fa riferimento non diventa idoneo per il Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="808e2-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="808e2-193">Le variabili introdotte in un'espressione lambda non sono visibili nel metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="808e2-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="808e2-194">Un'espressione lambda non può acquisire direttamente un parametro [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md) dal metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="808e2-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="808e2-195">Un'istruzione [return](../../language-reference/keywords/return.md) in un'espressione lambda non causa la restituzione del metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="808e2-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="808e2-196">Un'espressione lambda non può contenere un'istruzione [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) o [continue](../../language-reference/keywords/continue.md) se la destinazione di tale istruzione di salto è esterna al blocco dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="808e2-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="808e2-197">È anche errato inserire all'esterno del blocco dell'espressione lambda un'istruzione di salto se la destinazione è interna al blocco.</span><span class="sxs-lookup"><span data-stu-id="808e2-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="808e2-198">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="808e2-198">C# language specification</span></span>

<span data-ttu-id="808e2-199">Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="808e2-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="808e2-200">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="808e2-200">Featured book chapter</span></span>

<span data-ttu-id="808e2-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni Lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Tutto su C# 3.0, terza edizione: più di 250 soluzioni per i programmatori C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="808e2-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="808e2-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="808e2-202">See also</span></span>

- [<span data-ttu-id="808e2-203">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="808e2-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="808e2-204">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="808e2-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="808e2-205">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="808e2-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="808e2-206">Alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="808e2-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="808e2-207">Confronto tra funzioni locali ed espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="808e2-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="808e2-208">Espressioni lambda tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="808e2-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="808e2-209">Esempi C# di Visual Studio 2008 (vedere i file di query di esempio LINQ e il programma XQuery)</span><span class="sxs-lookup"><span data-stu-id="808e2-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="808e2-210">Recursive lambda expressions (Espressioni lambda ricorsive)</span><span class="sxs-lookup"><span data-stu-id="808e2-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
