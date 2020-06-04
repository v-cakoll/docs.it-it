---
title: Alberi delle espressioni
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: 5d30b2e2e66aa322e6d43b5fbf4a4baf3435b2a6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410967"
---
# <a name="expression-trees-visual-basic"></a><span data-ttu-id="47a2c-102">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a2c-102">Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="47a2c-103">Gli alberi delle espressioni rappresentano codice in una struttura dei dati simile a un albero, dove ogni nodo è un'espressione, ad esempio una chiamata al metodo o un'operazione binaria come `x < y`.</span><span class="sxs-lookup"><span data-stu-id="47a2c-103">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="47a2c-104">È possibile compilare ed eseguire codice rappresentato dagli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="47a2c-104">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="47a2c-105">In questo modo è possibile modificare dinamicamente codice eseguibile, eseguire query LINQ in vari database e creare query dinamiche.</span><span class="sxs-lookup"><span data-stu-id="47a2c-105">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="47a2c-106">Per altre informazioni sugli alberi delle espressioni in LINQ, vedere [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](how-to-use-expression-trees-to-build-dynamic-queries.md) (Procedura: Usare alberi delle espressioni per creare query dinamiche (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="47a2c-106">For more information about expression trees in LINQ, see [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>  
  
 <span data-ttu-id="47a2c-107">Gli alberi delle espressioni sono anche usati in Dynamic Language Runtime (DLR) per fornire interoperabilità tra linguaggi dinamici e .NET Framework e per consentire ai writer dei compilatori di creare alberi delle espressioni invece di codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="47a2c-107">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and the .NET Framework and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="47a2c-108">Per altre informazioni su DLR, vedere [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md) (Panoramica su Dynamic Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="47a2c-108">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="47a2c-109">È possibile creare un albero delle espressioni tramite il compilatore di C# o di Visual Basic in base a un'espressione lambda anonima o creare tali alberi di espressioni manualmente tramite il nome spazio <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="47a2c-109">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="47a2c-110">Creazione di alberi delle espressioni da espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="47a2c-110">Creating Expression Trees from Lambda Expressions</span></span>  
 <span data-ttu-id="47a2c-111">Quando un'espressione lambda viene assegnata a una variabile di tipo <xref:System.Linq.Expressions.Expression%601>, il compilatore genera codice per compilare un albero delle espressioni che rappresenta l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="47a2c-111">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="47a2c-112">Il compilatore di Visual Basic può generare alberi delle espressioni solo da espressioni lambda, o lambda su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="47a2c-112">The Visual Basic compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="47a2c-113">Non possono analizzare espressioni lambda dell'istruzione (o le espressioni lambda a più righe).</span><span class="sxs-lookup"><span data-stu-id="47a2c-113">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="47a2c-114">Per altre informazioni sulle espressioni lambda in Visual Basic, vedere [Espressioni lambda](../../language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="47a2c-114">For more information about lambda expressions in Visual Basic, see [Lambda Expressions](../../language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="47a2c-115">Gli esempi di codice seguenti illustrano in che modo il compilatore di Visual Basic crea un albero delle espressioni che rappresenta l'espressione lambda `Function(num) num < 5`.</span><span class="sxs-lookup"><span data-stu-id="47a2c-115">The following code examples demonstrate how to have the Visual Basic compiler create an expression tree that represents the lambda expression `Function(num) num < 5`.</span></span>  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="47a2c-116">Creazione di alberi delle espressioni tramite l'API</span><span class="sxs-lookup"><span data-stu-id="47a2c-116">Creating Expression Trees by Using the API</span></span>  
 <span data-ttu-id="47a2c-117">Per creare alberi delle espressioni tramite l'API, usare la classe <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="47a2c-117">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="47a2c-118">Questa classe contiene metodi factory statici che creano nodi degli alberi delle espressioni di tipi specifici, ad esempio <xref:System.Linq.Expressions.ParameterExpression>, che rappresenta una variabile o un parametro, o <xref:System.Linq.Expressions.MethodCallExpression>, che rappresenta una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="47a2c-118">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="47a2c-119">Anche <xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> e gli altri tipi specifici delle espressioni sono definiti nello spazio dei nomi <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="47a2c-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="47a2c-120">Questi tipi derivano dal tipo astratto <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="47a2c-120">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="47a2c-121">L'esempio di codice seguente illustra come creare un albero delle espressioni che rappresenti l'espressione lambda `Function(num) num < 5` usando l'API.</span><span class="sxs-lookup"><span data-stu-id="47a2c-121">The following code example demonstrates how to create an expression tree that represents the lambda expression `Function(num) num < 5` by using the API.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 <span data-ttu-id="47a2c-122">In .NET Framework 4 o nelle versioni successive l'API degli alberi delle espressioni supporta anche assegnazioni ed espressioni del flusso di controllo quali cicli, blocchi condizionali e blocchi `try-catch`.</span><span class="sxs-lookup"><span data-stu-id="47a2c-122">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="47a2c-123">Tramite l'API è possibile creare alberi delle espressioni più complessi rispetto a quelli che è possibile creare da espressioni lambda tramite il compilatore di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47a2c-123">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the Visual Basic compiler.</span></span> <span data-ttu-id="47a2c-124">L'esempio seguente illustra come creare un albero delle espressioni che calcola il fattoriale di un numero.</span><span class="sxs-lookup"><span data-stu-id="47a2c-124">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

<span data-ttu-id="47a2c-125">Per altre informazioni, vedere l'articolo [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Generazione di metodi dinamici con alberi delle espressioni in Visual Studio 2010), valido anche per le versioni successive di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47a2c-125">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="47a2c-126">Analisi degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="47a2c-126">Parsing Expression Trees</span></span>  
 <span data-ttu-id="47a2c-127">L'esempio di codice seguente illustra come scomporre nei vari componenti l'albero delle espressioni che rappresenta l'espressione lambda `Function(num) num < 5`.</span><span class="sxs-lookup"><span data-stu-id="47a2c-127">The following code example demonstrates how the expression tree that represents the lambda expression `Function(num) num < 5` can be decomposed into its parts.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="47a2c-128">Non modificabilità degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="47a2c-128">Immutability of Expression Trees</span></span>  
 <span data-ttu-id="47a2c-129">Gli alberi delle espressioni devono essere non modificabili.</span><span class="sxs-lookup"><span data-stu-id="47a2c-129">Expression trees should be immutable.</span></span> <span data-ttu-id="47a2c-130">Ciò significa che per modificare un albero delle espressioni è necessario costruirne uno nuovo copiando quello esistente e sostituendone i nodi.</span><span class="sxs-lookup"><span data-stu-id="47a2c-130">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="47a2c-131">È possibile usare un visitatore dell'albero delle espressioni per attraversare l'albero delle espressioni esistente.</span><span class="sxs-lookup"><span data-stu-id="47a2c-131">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="47a2c-132">Per altre informazioni, vedere [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md) (Procedura: Modificare alberi delle espressioni (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="47a2c-132">For more information, see [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md).</span></span>  
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="47a2c-133">Compilazione degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="47a2c-133">Compiling Expression Trees</span></span>  
 <span data-ttu-id="47a2c-134">Il tipo <xref:System.Linq.Expressions.Expression%601> fornisce il metodo <xref:System.Linq.Expressions.Expression%601.Compile%2A> che compila il codice rappresentato da un albero delle espressioni in un delegato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="47a2c-134">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="47a2c-135">L'esempio di codice seguente illustra come compilare un albero delle espressioni ed eseguire il codice risultante.</span><span class="sxs-lookup"><span data-stu-id="47a2c-135">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 <span data-ttu-id="47a2c-136">Per altre informazioni, vedere [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Procedura: Eseguire alberi delle espressioni (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="47a2c-136">For more information, see [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a2c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47a2c-137">See also</span></span>

- <xref:System.Linq.Expressions>
- <span data-ttu-id="47a2c-138">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Procedura: Eseguire alberi delle espressioni (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="47a2c-138">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md)</span></span>
- <span data-ttu-id="47a2c-139">[How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md) (Procedura: Modificare alberi delle espressioni (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="47a2c-139">[How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md)</span></span>
- [<span data-ttu-id="47a2c-140">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="47a2c-140">Lambda Expressions</span></span>](../../language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="47a2c-141">Panoramica di Dynamic Language Runtime</span><span class="sxs-lookup"><span data-stu-id="47a2c-141">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="47a2c-142">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a2c-142">Programming Concepts (Visual Basic)</span></span>](../index.md)
