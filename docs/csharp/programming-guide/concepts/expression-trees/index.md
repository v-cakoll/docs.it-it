---
title: Alberi delle espressioni (C#)
ms.date: 07/20/2015
ms.assetid: 7d0ac21a-6d90-4e2e-8903-528cb78615b7
ms.openlocfilehash: 7744954d3a3f552d5765e6e7085950f08a5adf55
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720928"
---
# <a name="expression-trees-c"></a><span data-ttu-id="9c044-102">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="9c044-102">Expression Trees (C#)</span></span>
<span data-ttu-id="9c044-103">Gli alberi delle espressioni rappresentano codice in una struttura dei dati simile a un albero, dove ogni nodo è un'espressione, ad esempio una chiamata al metodo o un'operazione binaria come `x < y`.</span><span class="sxs-lookup"><span data-stu-id="9c044-103">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="9c044-104">È possibile compilare ed eseguire codice rappresentato dagli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="9c044-104">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="9c044-105">In questo modo è possibile modificare dinamicamente codice eseguibile, eseguire query LINQ in vari database e creare query dinamiche.</span><span class="sxs-lookup"><span data-stu-id="9c044-105">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="9c044-106">Per altre informazioni sulle strutture ad albero in LINQ, vedere [Procedura: Usare alberi delle espressioni per la compilazione di query dinamiche (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9c044-106">For more information about expression trees in LINQ, see [How to: Use Expression Trees to Build Dynamic Queries (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>  
  
 <span data-ttu-id="9c044-107">Gli alberi delle espressioni sono anche usati in Dynamic Language Runtime (DLR) per fornire interoperabilità tra linguaggi dinamici e .NET Framework e per consentire ai writer dei compilatori di creare alberi delle espressioni invece di codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="9c044-107">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and the .NET Framework and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="9c044-108">Per altre informazioni su DLR, vedere [Dynamic Language Runtime Overview](../../../../../docs/framework/reflection-and-codedom/dynamic-language-runtime-overview.md) (Panoramica su Dynamic Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="9c044-108">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../../docs/framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="9c044-109">È possibile creare un albero delle espressioni tramite il compilatore di C# o di Visual Basic in base a un'espressione lambda anonima o creare tali alberi di espressioni manualmente tramite il nome spazio <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="9c044-109">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="9c044-110">Creazione di alberi di espressioni da espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="9c044-110">Creating Expression Trees from Lambda Expressions</span></span>  
 <span data-ttu-id="9c044-111">Quando un'espressione lambda viene assegnata a una variabile di tipo <xref:System.Linq.Expressions.Expression%601>, il compilatore genera codice per compilare un albero delle espressioni che rappresenta l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="9c044-111">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="9c044-112">Il compilatore di C# può generare alberi delle espressioni solo da espressioni lambda, o lambda su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="9c044-112">The C# compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="9c044-113">Non possono analizzare espressioni lambda dell'istruzione (o le espressioni lambda a più righe).</span><span class="sxs-lookup"><span data-stu-id="9c044-113">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="9c044-114">Per altre informazioni sulle espressioni lambda in C#, vedere [Espressioni lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9c044-114">For more information about lambda expressions in C#, see [Lambda Expressions](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="9c044-115">Gli esempi di codice seguenti illustrano in che modo il compilatore di C# crea un albero delle espressioni che rappresenta l'espressione lambda `num => num < 5`.</span><span class="sxs-lookup"><span data-stu-id="9c044-115">The following code examples demonstrate how to have the C# compiler create an expression tree that represents the lambda expression `num => num < 5`.</span></span>  
  
```csharp  
Expression<Func<int, bool>> lambda = num => num < 5;  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="9c044-116">Creazione di alberi delle espressioni tramite l'API</span><span class="sxs-lookup"><span data-stu-id="9c044-116">Creating Expression Trees by Using the API</span></span>  
 <span data-ttu-id="9c044-117">Per creare alberi delle espressioni tramite l'API, usare la classe <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="9c044-117">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="9c044-118">Questa classe contiene metodi factory statici che creano nodi degli alberi delle espressioni di tipi specifici, ad esempio <xref:System.Linq.Expressions.ParameterExpression>, che rappresenta una variabile o un parametro, o <xref:System.Linq.Expressions.MethodCallExpression>, che rappresenta una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="9c044-118">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="9c044-119">Anche <xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> e gli altri tipi specifici delle espressioni sono definiti nello spazio dei nomi <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="9c044-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="9c044-120">Questi tipi derivano dal tipo astratto <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="9c044-120">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="9c044-121">L'esempio di codice seguente illustra come creare un albero delle espressioni che rappresenti l'espressione lambda `num => num < 5` usando l'API.</span><span class="sxs-lookup"><span data-stu-id="9c044-121">The following code example demonstrates how to create an expression tree that represents the lambda expression `num => num < 5` by using the API.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Manually build the expression tree for   
// the lambda expression num => num < 5.  
ParameterExpression numParam = Expression.Parameter(typeof(int), "num");  
ConstantExpression five = Expression.Constant(5, typeof(int));  
BinaryExpression numLessThanFive = Expression.LessThan(numParam, five);  
Expression<Func<int, bool>> lambda1 =  
    Expression.Lambda<Func<int, bool>>(  
        numLessThanFive,  
        new ParameterExpression[] { numParam });  
```  
  
 <span data-ttu-id="9c044-122">In .NET Framework 4 o nelle versioni successive l'API degli alberi delle espressioni supporta anche assegnazioni ed espressioni del flusso di controllo quali cicli, blocchi condizionali e blocchi `try-catch`.</span><span class="sxs-lookup"><span data-stu-id="9c044-122">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="9c044-123">Tramite l'API è possibile creare alberi delle espressioni più complessi rispetto a quelli che è possibile creare da espressioni lambda con il compilatore di C#.</span><span class="sxs-lookup"><span data-stu-id="9c044-123">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the C# compiler.</span></span> <span data-ttu-id="9c044-124">L'esempio seguente illustra come creare un albero delle espressioni che calcola il fattoriale di un numero.</span><span class="sxs-lookup"><span data-stu-id="9c044-124">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```csharp  
// Creating a parameter expression.  
ParameterExpression value = Expression.Parameter(typeof(int), "value");  
  
// Creating an expression to hold a local variable.   
ParameterExpression result = Expression.Parameter(typeof(int), "result");  
  
// Creating a label to jump to from a loop.  
LabelTarget label = Expression.Label(typeof(int));  
  
// Creating a method body.  
BlockExpression block = Expression.Block(  
    // Adding a local variable.  
    new[] { result },  
    // Assigning a constant to a local variable: result = 1  
    Expression.Assign(result, Expression.Constant(1)),  
    // Adding a loop.  
        Expression.Loop(  
    // Adding a conditional block into the loop.  
           Expression.IfThenElse(  
    // Condition: value > 1  
               Expression.GreaterThan(value, Expression.Constant(1)),  
    // If true: result *= value --  
               Expression.MultiplyAssign(result,  
                   Expression.PostDecrementAssign(value)),  
    // If false, exit the loop and go to the label.  
               Expression.Break(label, result)  
           ),  
    // Label to jump to.  
       label  
    )  
);  
  
// Compile and execute an expression tree.  
int factorial = Expression.Lambda<Func<int, int>>(block, value).Compile()(5);  
  
Console.WriteLine(factorial);  
// Prints 120.  
```

<span data-ttu-id="9c044-125">Per altre informazioni, vedere l'articolo [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://blogs.msdn.microsoft.com/csharpfaq/2009/09/14/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Generazione di metodi dinamici con alberi delle espressioni in Visual Studio 2010), valido anche per le versioni successive di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9c044-125">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://blogs.msdn.microsoft.com/csharpfaq/2009/09/14/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="9c044-126">Analisi degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="9c044-126">Parsing Expression Trees</span></span>  
 <span data-ttu-id="9c044-127">L'esempio di codice seguente illustra come scomporre nei vari componenti l'albero delle espressioni che rappresenta l'espressione lambda `num => num < 5`.</span><span class="sxs-lookup"><span data-stu-id="9c044-127">The following code example demonstrates how the expression tree that represents the lambda expression `num => num < 5` can be decomposed into its parts.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Create an expression tree.  
Expression<Func<int, bool>> exprTree = num => num < 5;  
  
// Decompose the expression tree.  
ParameterExpression param = (ParameterExpression)exprTree.Parameters[0];  
BinaryExpression operation = (BinaryExpression)exprTree.Body;  
ParameterExpression left = (ParameterExpression)operation.Left;  
ConstantExpression right = (ConstantExpression)operation.Right;  
  
Console.WriteLine("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value);  
  
// This code produces the following output:  
  
// Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="9c044-128">Non modificabilità degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="9c044-128">Immutability of Expression Trees</span></span>  
 <span data-ttu-id="9c044-129">Gli alberi delle espressioni devono essere non modificabili.</span><span class="sxs-lookup"><span data-stu-id="9c044-129">Expression trees should be immutable.</span></span> <span data-ttu-id="9c044-130">Ciò significa che per modificare un albero delle espressioni è necessario costruirne uno nuovo copiando quello esistente e sostituendone i nodi.</span><span class="sxs-lookup"><span data-stu-id="9c044-130">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="9c044-131">È possibile usare un visitatore dell'albero delle espressioni per attraversare l'albero delle espressioni esistente.</span><span class="sxs-lookup"><span data-stu-id="9c044-131">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="9c044-132">Per altre informazioni, vedere [Procedura: Modificare alberi delle espressioni (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="9c044-132">For more information, see [How to: Modify Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).</span></span>  
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="9c044-133">Compilazione degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="9c044-133">Compiling Expression Trees</span></span>  
 <span data-ttu-id="9c044-134">Il tipo <xref:System.Linq.Expressions.Expression%601> fornisce il metodo <xref:System.Linq.Expressions.Expression%601.Compile%2A> che compila il codice rappresentato da un albero delle espressioni in un delegato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="9c044-134">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="9c044-135">L'esempio di codice seguente illustra come compilare un albero delle espressioni ed eseguire il codice risultante.</span><span class="sxs-lookup"><span data-stu-id="9c044-135">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```csharp  
// Creating an expression tree.  
Expression<Func<int, bool>> expr = num => num < 5;  
  
// Compiling the expression tree into a delegate.  
Func<int, bool> result = expr.Compile();  
  
// Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4));  
  
// Prints True.  
  
// You can also use simplified syntax  
// to compile and run an expression tree.  
// The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4));  
  
// Also prints True.  
```  
  
 <span data-ttu-id="9c044-136">Per altre informazioni, vedere [Procedura: Eseguire alberi delle espressioni (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="9c044-136">For more information, see [How to: Execute Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c044-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c044-137">See also</span></span>

- <xref:System.Linq.Expressions>
- [<span data-ttu-id="9c044-138">Procedura: Eseguire alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="9c044-138">How to: Execute Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [<span data-ttu-id="9c044-139">Procedura: Modificare alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="9c044-139">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
- [<span data-ttu-id="9c044-140">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="9c044-140">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- <span data-ttu-id="9c044-141">[Dynamic Language Runtime Overview](../../../../../docs/framework/reflection-and-codedom/dynamic-language-runtime-overview.md) (Panoramica su Dynamic Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="9c044-141">[Dynamic Language Runtime Overview](../../../../../docs/framework/reflection-and-codedom/dynamic-language-runtime-overview.md)</span></span>
- [<span data-ttu-id="9c044-142">Nozioni di base sulla programmazione (C#)</span><span class="sxs-lookup"><span data-stu-id="9c044-142">Programming Concepts (C#)</span></span>](../../../../csharp/programming-guide/concepts/index.md)
